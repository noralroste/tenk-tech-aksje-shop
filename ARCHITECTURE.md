# Applikasjonsarkitektur – OWASP Juice Shop

OWASP Juice Shop er en **bevisst sårbar nettbutikk** brukt til sikkerhetsopplæring, CTF-konkurranser og penetrasjonstesting. Den simulerer en ekte e-handelsapplikasjon med innebygde sikkerhetssvakheter fra OWASP Top Ten.

---

## Teknologioversikt

| Lag | Teknologi |
|-----|-----------|
| Frontend | Angular 20, Angular Material, RxJS |
| Backend | Node.js, Express 4, TypeScript |
| Database | SQLite3 via Sequelize ORM |
| Auth | JWT (RS256), express-jwt |
| Realtime | Socket.io |
| Web3 | Ethers.js / Web3.js |
| Testing | Jest, Cypress, Frisby |

---

## 1. Overordnet arkitektur

```mermaid
graph TB
    subgraph Klient["Klient (nettleser)"]
        Angular["Angular 20 SPA<br/>(Single Page App)"]
    end

    subgraph Server["Server (Node.js / Express)"]
        Express["Express middleware-kjede"]
        Routes["60+ route-handlere<br/>/rest/*, /api/*, /b2b/*"]
        Lib["lib/<br/>insecurity.ts · logger.ts · startup.ts"]
    end

    subgraph Data["Datalag"]
        Sequelize["Sequelize ORM<br/>(24 modeller)"]
        SQLite["SQLite<br/>juiceshop.sqlite"]
    end

    subgraph Eksternt["Eksternt"]
        SocketIO["Socket.io<br/>(sanntid)"]
        Blockchain["Ethereum<br/>(Web3/Ethers)"]
    end

    Angular -->|HTTP REST + JWT| Express
    Angular <-->|WebSocket| SocketIO
    Express --> Routes
    Routes --> Lib
    Routes --> Sequelize
    Sequelize --> SQLite
    Routes <--> SocketIO
    Routes <--> Blockchain
```

---

## 2. Oppstartssekvens

```mermaid
sequenceDiagram
    participant App as app.ts
    participant Server as server.ts
    participant DB as Sequelize / SQLite
    participant Routes as Route-handlere

    App->>App: validateDependencies()
    App->>Server: start()
    Server->>Server: validatePreconditions()
    Server->>Server: cleanupFtpFolder()
    Server->>Server: validateConfig()
    Server->>Server: Set up Express middleware<br/>(CORS, Helmet, bodyParser, i18n, Morgan)
    Server->>DB: sequelize.authenticate()
    DB-->>Server: Tilkobling OK
    Server->>DB: sync() – opprett tabeller
    DB-->>Server: Skjema klart
    Server->>DB: datacreator.ts – seed brukere, produkter, utfordringer
    Server->>Routes: Registrer alle route-handlere
    Server->>Server: Lytt på port 3000
    Server-->>App: Server klar
```

---

## 3. Autentiseringsflyt (innlogging)

```mermaid
flowchart TD
    A([Bruker fyller inn e-post + passord]) --> B[POST /rest/user/login]
    B --> C{SQL-spørring mot Users-tabell}
    C -->|Sårbar spørring:<br/>SELECT * WHERE email='...' AND password='...'| D[SQLite]
    D -->|Ingen treff| E[401 Uautorisert]
    D -->|Treff| F[Generer JWT med RS256]
    F --> G[Lagre token i authenticatedUsers-cache]
    G --> H[Hent eller opprett handlekurv]
    H --> I[Returner token + bid + umail]
    I --> J[Frontend lagrer token i localStorage]
    J --> K[RequestInterceptor legger til<br/>Authorization: Bearer ... på alle requests]

    style C fill:#ffcccc
    style E fill:#ffaaaa
```

> **Merk:** SQL-spørringen er bevisst sårbar for SQL-injeksjon – dette er en del av læringsopplegget.

---

## 4. Autorisasjonsarkitektur

```mermaid
flowchart LR
    subgraph Frontend
        LG[LoginGuard] --> Ruter
        AG[AdminGuard] --> Admin["/administration"]
        AccG[AccountingGuard] --> Acc["/accounting"]
        DelG[DeluxeGuard] --> Deluxe["/deluxe-user"]
    end

    subgraph Backend
        JWT[express-jwt<br/>token-validering]
        isAuth[security.isAuthorized]
        isAcc[security.isAccounting]
        denyAll[security.denyAll]
    end

    Ruter -->|HTTP + Bearer token| JWT
    JWT --> isAuth
    isAuth -->|Admin-rolle| isAcc
    isAuth -->|Blokkert rute| denyAll
```

**Roller:** `customer` · `deluxe` · `accounting` · `admin`

---

## 5. Handlekurv og kjøpsflyt

```mermaid
flowchart TD
    A([Bruker søker etter produkt]) --> B[GET /rest/products/search?q=]
    B --> C[Vis produktliste]
    C --> D[Bruker klikker 'Legg i handlekurv']
    D --> E[POST /api/BasketItems]
    E --> F[BasketItem opprettes i DB]
    F --> G[Oppdater handlekurv-ikon]

    G --> H[Bruker går til handlekurv]
    H --> I[GET /rest/basket/:id]
    I --> J[Vis varer + totalpris]

    J --> K[Bruker velger leveringsmåte]
    K --> L[POST /api/Deliverys]

    L --> M[Bruker velger betalingsmetode]
    M --> N{Betalingstype}
    N -->|Kort| O[POST /api/Cards]
    N -->|Krypto| P[Web3 wallet-transaksjon]
    N -->|Lommebok| Q[PUT /rest/wallet/balance]

    O & P & Q --> R[POST /rest/basket/:id/checkout]
    R --> S[Ordre lagret i DB]
    S --> T[Vis ordrebekreftelse]
    T --> U[Ordre tilgjengelig i ordrehistorikk]
```

---

## 6. Frontend-komponentstruktur

```mermaid
graph TD
    App[AppComponent] --> Nav[NavbarComponent]
    App --> Router{Angular Router}

    Router --> Search[SearchResultComponent]
    Router --> Product[ProductDetailsComponent]
    Router --> Basket[PurchaseBasketComponent]
    Router --> Login[LoginComponent]
    Router --> Register[RegisterComponent]
    Router --> Profile[UserDetailsComponent]
    Router --> Admin[AdministrationComponent]
    Router --> Score[ScoreBoardComponent]
    Router --> Chatbot[ChatbotComponent]
    Router --> Web3[WalletWeb3Component]
    Router --> PhotoWall[PhotoWallComponent]

    subgraph Services["Tjenester (Angular Injectables)"]
        UserSvc[UserService]
        ProductSvc[ProductService]
        BasketSvc[BasketService]
        ChallengeSvc[ChallengeService]
        ConfigSvc[ConfigurationService]
    end

    Search --> ProductSvc
    Basket --> BasketSvc
    Login --> UserSvc
    Score --> ChallengeSvc
    Nav --> ConfigSvc
```

---

## 7. Databasemodeller

```mermaid
erDiagram
    User ||--o{ Basket : "har"
    User ||--o{ Feedback : "gir"
    User ||--o{ Address : "har"
    User ||--o{ Card : "har"
    User ||--o{ Wallet : "har"
    User ||--o{ Memory : "deler"
    User }o--|| SecurityQuestion : "velger"

    Basket ||--o{ BasketItem : "inneholder"
    BasketItem }o--|| Product : "refererer til"

    Product ||--o{ Quantity : "har lager for"

    Challenge ||--o{ Hint : "har"

    User ||--o{ Complaint : "sender inn"
    User ||--o{ Recycle : "sender inn"
    User ||--o{ PrivacyRequest : "sender inn"
```

---

## 8. Utfordringssystem (CTF-mekanisme)

```mermaid
flowchart TD
    A[Bruker utfører sårbar handling] --> B{Serverside deteksjon}
    B -->|Utfordring løst| C[Challenge.solved = true i DB]
    C --> D[Socket.io sender notifikasjon]
    D --> E[Frontend viser suksessmelding]
    E --> F[Scoreboard oppdateres]

    G[Bruker åpner Scoreboard] --> H[GET /api/Challenges]
    H --> I[Vis kategorier og poeng]
    I --> J[Vis kodesnutt for løste utfordringer]
    J --> K[Bruker kan se sårbar vs. sikker kode]
```

---

## 9. API-strukturoversikt

| Prefiks | Beskrivelse | Autentisering |
|---------|-------------|---------------|
| `GET/POST /rest/user/*` | Innlogging, profil, 2FA | Åpen + JWT |
| `GET/POST /api/*` | CRUD for alle ressurser (Sequelize Finale) | JWT |
| `POST /b2b/v2/orders` | B2B API | JWT |
| `GET /ftp/*` | Filserver (bevisst eksponert) | Ingen |
| `GET /encryptionkeys/*` | Krypteringsnøkler (bevisst eksponert) | Ingen |
| `GET /support/logs` | Servelogger (bevisst eksponert) | Ingen |
| `WS /` | Socket.io WebSocket | Token |

---

## 10. Sikkerhetssårbarheter (bevisste)

Applikasjonen inneholder bevisste svakheter fra OWASP Top Ten:

| Kategori | Eksempel i koden |
|----------|-----------------|
| SQL-injeksjon | `routes/login.ts` – direkte strenginterpolasjon i SQL |
| XSS | Produktanmeldelser og brukernavn uten sanitering |
| Svak krypto | MD5 brukt til passord-hashing (`lib/insecurity.ts`) |
| Sensitiv dataeksponering | `/ftp`, `/encryptionkeys` tilgjengelig uten autentisering |
| Broken Access Control | Manglende autorisasjonskontroller på flere endepunkter |
| CSRF | Manglende token-validering på statusendringer |

> Disse er **aldri** utilsiktede feil – de er læringsmål for sikkerhetsstudenter.
