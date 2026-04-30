# Læringsplan – Juice Shop for norske skoleelever

Denne planen kobler kompetansemål fra norsk læreplan (LK20) til konkrete oppgaver i OWASP Juice Shop. Oppgavene er organisert etter klassetrinn og vanskelighetsgrad (⭐–⭐⭐⭐⭐⭐⭐).

🔗-ikonet ved hver oppgave åpner OWASP-dokumentasjonen for det aktuelle sikkerhetsemnet i et nytt vindu.

---

## Trinn 1 – Ungdomsskole (8.–10. klasse)

### Relevante læreplaner

| Fag | Lenke |
|-----|-------|
| Matematikk (MAT01-05) | [udir.no/lk20/mat01-05](https://www.udir.no/lk20/mat01-05) |
| Valgfaget Programmering (PRG01-02) | [udir.no/lk20/prg01-02](https://www.udir.no/lk20/prg01-02) |

### Hva elevene skal ha lært

Fra **matematikk** (algoritmisk tenkning):
- Utforske hvordan algoritmer kan skapes, testes og forbedres ved hjelp av programmering
- Bruke programmering til å utforske og løse problemer

Fra **valgfaget programmering**:
- Gjøre rede for hvordan datamaskiner og dataprogram fungerer
- Bruke grunnleggende prinsipper: variabler, løkker, vilkår og funksjoner
- Planlegge og skape et digitalt produkt
- Feilsøke og forstå kode

### Anbefalte oppgaver ⭐ (1 stjerne)

Disse oppgavene krever kun nysgjerrighet og grunnleggende forståelse av nettsider.

| Oppgave | Kategori | Beskrivelse | Les mer |
|---------|----------|-------------|---------|
| Score Board | Diverse | Finn den skjulte poengtavlen – øv på å utforske en nettside | |
| Privacy Policy | Diverse | Les personvernerklæringen – forstå hva du samtykker til | |
| Error Handling | Sikkerhetsfeil | Få frem en feilmelding – forstå hvordan feil ser ut | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Error_Handling_Cheat_Sheet.html) |
| Zero Stars | Validering | Send inn en anmeldelse med null stjerner | |
| Repetitive Registration | Validering | Registrer en bruker uten å gjenta passordet riktig | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html) |
| Missing Encoding | Validering | Hent et bilde som er kodet feil i URL-en | |
| Exposed Metrics | Observerbarhet | Finn endepunktet for overvåkingsdata | |
| Bully Chatbot | Diverse | Få støtte-chatboten til å gi deg en kupongkode | |
| Mass Dispel | Diverse | Lukk flere varsler på én gang | |
| Outdated Allowlist | Uvalidert omdirigering | La nettsiden omdirigere deg til en gammel kryptoadresse | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html) |
| DOM XSS | XSS | Utfør et enkelt DOM XSS-angrep (observer hva som skjer) | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html) |
| Bonus Payload | XSS | Bruk bonusnyttelasten i DOM XSS-utfordringen (krever DOM XSS løst først) | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html) |

---

## Trinn 2 – VGS1 (Vg1/Vg2) – Informasjonsteknologi 1

### Relevante læreplaner

| Fag | Lenke |
|-----|-------|
| Informasjonsteknologi 1 (INF01-03) | [udir.no/lk20/inf01-03](https://www.udir.no/lk20/inf01-03) |

### Hva elevene skal ha lært

- Beskrive sentrale komponenter i datamaskiner og nettverk
- Gjøre rede for personvernregelverk (GDPR) og konsekvenser
- Drøfte innhenting, bruk og misbruk av data
- Lagre og hente data, presentere på nettsider
- Utvikle nettsider med markeringsspråk (HTML)
- Utvikle prosedyreorienterte programmer
- Beskrive ulike typer algoritmer

### Anbefalte oppgaver ⭐⭐ (2 stjerner)

Disse krever forståelse av HTTP, autentisering, og grunnleggende webutvikling.

| Oppgave | Kategori | Beskrivelse | Les mer |
|---------|----------|-------------|---------|
| Admin Section | Tilgangskontroll | Finn administrasjonsseksjonen uten å ha admin-rettigheter | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html) |
| Password Strength | Autentisering | Logg inn med admin uten å bruke SQL-injeksjon | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html) |
| Login Admin | Injeksjon | Logg inn som administrator via SQL-injeksjon | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html) |
| Login MC SafeSearch | Sensitiv data | Logg inn med brukerens opprinnelige passord | |
| View Basket | Tilgangskontroll | Se en annen brukers handlekurv | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html) |
| Five-Star Feedback | Tilgangskontroll | Slett all femstjerners tilbakemelding | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html) |
| Deprecated Interface | Feilkonfigurasjon | Bruk et B2B-grensesnitt som ikke ble stengt | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Web_Service_Security_Cheat_Sheet.html) |
| Empty User Registration | Validering | Registrer bruker med tom e-post og passord | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html) |
| Reflected XSS | XSS | Utfør et reflektert XSS-angrep | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html) |
| Weird Crypto | Kryptografi | Finn en usikker kryptoalgoritme i applikasjonen | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Vulnerability_Disclosure_Cheat_Sheet.html) |
| Security Policy | Diverse | Les og følg security.txt / ansvarlig avsløring | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Vulnerability_Disclosure_Cheat_Sheet.html) |
| NFT Takeover | Sensitiv data | Ta over lommeboken med det offisielle NFT-en | |
| Meta Geo Stalking | Sensitiv data | Finn svar på sikkerhetsspørsmål via bildemetadata | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet.html) |
| Visual Geo Stalking | Sensitiv data | Finn svar på sikkerhetsspørsmål via bildeinnhold | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet.html) |
| Password Hash Leak | Sensitiv data | Hent passordhash direkte fra REST API | [![](docs/open-in-new.svg)](https://owasp.org/API-Security/editions/2019/en/0xa3-excessive-data-exposure) |
| Exposed credentials | Sensitiv data | Finn hardkodede testbrukerdetaljer i klientkoden | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html) |

---

## Trinn 3 – VGS2 – Informasjonsteknologi 2 / VG2 IT

### Relevante læreplaner

| Fag | Lenke |
|-----|-------|
| Informasjonsteknologi 2 (INF02-03) | [udir.no/lk20/inf02-03](https://www.udir.no/lk20/inf02-03) |
| VG2 Informasjonsteknologi – yrkesfag (ITK02-01) | [udir.no/lk20/itk02-01](https://www.udir.no/lk20/itk02-01) |

### Hva elevene skal ha lært

Fra **IT2**:
- Gjøre rede for standarder for lagring, utveksling og sikring av data
- Vurdere og bruke strategier for feilsøking og testing
- Anvende objektorientert modellering
- Utforske og vurdere alternative løsninger for design og implementering

Fra **VG2 IT – Driftsstøtte**:
- Utforske trusler mot datasikkerhet og gjøre rede for dagens trusselbilde
- Gjennomføre risikoanalyse av nettverk og tjenester
- Planlegge og drifte IT-løsninger som ivaretar informasjonssikkerhet og GDPR
- Administrere brukere, tilganger og rettigheter
- Utforske relevante nettverksprotokoller og serverroller

Fra **VG2 IT – Utvikling**:
- Analysere digitale trusler, verdier og sårbarheter
- Utvikle applikasjoner med innebygget sikkerhet
- Designe og implementere IT-tjenester med innebygget personvern
- Modellere og opprette databaser

### Anbefalte oppgaver ⭐⭐⭐ (3 stjerner)

Krever forståelse av HTTP-forespørsler, autentisering, databaser og klientsidekode.

| Oppgave | Kategori | Beskrivelse | Les mer |
|---------|----------|-------------|---------|
| Database Schema | Injeksjon | Eksporter hele databaseskjemaet via SQL-injeksjon | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html) |
| Login Bender | Injeksjon | Logg inn med SQL-injeksjon via kjent e-postformat | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html) |
| Login Jim | Injeksjon | Logg inn med kjent Star Trek-referanse | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html) |
| GDPR Data Erasure | Autentisering | Logg inn med en slettet brukerkonto (GDPR-hull) | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/User_Privacy_Protection_Cheat_Sheet.html) |
| Client-side XSS Protection | XSS | Omgå klientsidebeskyttelse mot XSS | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html) |
| Admin Registration | Validering | Registrer en bruker med administratorrettigheter | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Mass_Assignment_Cheat_Sheet.html) |
| Forged Feedback | Tilgangskontroll | Send tilbakemelding i en annen brukers navn | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html) |
| Forged Review | Tilgangskontroll | Skriv produktanmeldelse som en annen bruker | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html) |
| CSRF | Tilgangskontroll | Endre brukernavn via Cross-Site Request Forgery | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html) |
| Manipulate Basket | Tilgangskontroll | Legg produkt i en annen brukers handlekurv | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html) |
| Reset Jim's Password | Autentisering | Tilbakestill passord ved å finne riktig hint | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet.html) |
| Bjoern's Favorite Pet | Autentisering | Tilbakestill Bjoerns passord via sikkerhetsspørsmål | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet.html) |
| Privacy Policy Inspection | Skjult sikkerhet | Bevis at du faktisk leste personvernerklæringen | |
| Product Tampering | Tilgangskontroll | Endre produktbeskrivelsens lenke via API | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/REST_Security_Cheat_Sheet.html) |
| Payback Time | Validering | Bestill et produkt som gir deg penger tilbake | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html) |
| Upload Size | Validering | Last opp en fil større enn tillatt | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html) |
| Upload Type | Validering | Last opp en fil med feil filtype | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html) |
| CAPTCHA Bypass | Anti-automasjon | Send inn 10 tilbakemeldinger på under 20 sekunder | |
| XXE Data Access | XXE | Les innhold fra serverfiler via XML External Entity | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html) |
| Deluxe Fraud | Validering | Få Deluxe-medlemskap uten å betale | |
| Security Advisory | Diverse | Finn kjent sårbarhet og rapporter den | |

---

## Trinn 4 – VGS3 / Fordypning

### Relevante læreplaner

| Fag | Lenke |
|-----|-------|
| Informasjonsteknologi 2 (INF02-03) | [udir.no/lk20/inf02-03](https://www.udir.no/lk20/inf02-03) |
| VG2 Informasjonsteknologi – yrkesfag (ITK02-01) | [udir.no/lk20/itk02-01](https://www.udir.no/lk20/itk02-01) |

### Hva elevene skal ha lært (fordypning)

- Utforske og vurdere muligheter, utfordringer og konsekvenser av IT
- Drøfte etiske dilemmaer knyttet til informasjonsteknologi
- Avansert feilsøking og testing av programkode
- Gjennomføre risikoanalyse og foreslå tiltak
- Forstå angrepsflater, autentiseringssvakheter og kryptografi

### Anbefalte oppgaver ⭐⭐⭐⭐ (4 stjerner)

Krever dybdeforståelse av HTTP-protokoller, JWT, databasespråk og klientarkitektur.

| Oppgave | Kategori | Beskrivelse | Les mer |
|---------|----------|-------------|---------|
| Christmas Special | Injeksjon | Bestill et tilbud fra 2014 via avansert SQL-injeksjon | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html) |
| User Credentials | Injeksjon | Hent alle brukernavn og passord via SQL-injeksjon | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html) |
| NoSQL DoS | Injeksjon | La serveren sove ved NoSQL-injeksjon | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet.html) |
| NoSQL Manipulation | Injeksjon | Oppdater flere produktanmeldelser samtidig | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet.html) |
| Server-side XSS Protection | XSS | Omgå serversidebeskyttelse mot XSS | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html) |
| HTTP-Header XSS | XSS | Utfør vedvarende XSS via HTTP-hode | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html) |
| CSP Bypass | XSS | Omgå Content Security Policy | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html) |
| GDPR Data Theft | Sensitiv data | Stjel andres persondata uten injeksjon | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/User_Privacy_Protection_Cheat_Sheet.html) |
| Easter Egg | Tilgangskontroll | Finn det skjulte easter egg | |
| Reset Bender's Password | Autentisering | Tilbakestill passord med sikkerhetsspørsmål | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet.html) |
| Login Bjoern | Autentisering | Logg inn uten å kjenne passordet eller bruke injeksjon | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html) |
| Forgotten Developer Backup | Sensitiv data | Finn glemte utviklerfiler | |
| Forgotten Sales Backup | Sensitiv data | Finn glemte salgsfiler | |
| Leaked Unsafe Product | Sensitiv data | Identifiser farlig fjernet produkt | |
| Misplaced Signature File | Observerbarhet | Finn en SIEM-signaturfil | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html) |
| Nested Easter Egg | Kryptografi | Bruk kryptoanalyse for å finne det ekte easter egget | |
| Steganography | Skjult sikkerhet | Finn en karakter skjult i bildemateriale | |
| Allowlist Bypass | Uvalidert omdirigering | Tving en omdirigering til forbudt side | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html) |
| Poison Null Byte | Validering | Omgå sikkerhetskontroll med null-byte | |
| Vulnerable Library | Sårbare komponenter | Identifiser sårbart bibliotek med eksakt versjon | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Vulnerability_Disclosure_Cheat_Sheet.html) |
| Legacy Typosquatting | Sårbare komponenter | Finn et typosquatting-angrep i eldre versjon | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Vulnerable_Dependency_Management_Cheat_Sheet.html) |
| Reset Uvogin's Password | Sensitiv data | Finn svar på sikkerhetsspørsmål via OSINT | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet.html) |
| Access Log | Observerbarhet | Skaff tilgang til serverloggfiler | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html) |
| Ephemeral Accountant | Injeksjon | Logg inn som ikke-eksisterende bruker via injeksjon | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html) |
| Expired Coupon | Validering | Løs inn en utløpt kupongkode | |
| Mint the Honey Pot | Validering | Mint et NFT via smart contract-manipulasjon | |
| Cross-Site Imaging | Feilkonfigurasjon | Bruk cross-domain bildeinnlasting mot applikasjonen | |

---

## ⭐⭐⭐⭐⭐–⭐⭐⭐⭐⭐⭐ Ekspertoppgaver (CTF / videreutdanning)

Disse er ment for elever med spesiell interesse for sikkerhet, eller som forberedelse til CTF-konkurranser. De krever kunnskap utover vanlig VGS-pensum.

| Oppgave | Stjerner | Kategori | Beskrivelse | Les mer |
|---------|----------|----------|-------------|---------|
| Reset Morty's Password | ⭐⭐⭐⭐⭐ | Anti-automasjon | Obfuskert svar på sikkerhetsspørsmål | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Forgot_Password_Cheat_Sheet.html) |
| Reset Bjoern's Password | ⭐⭐⭐⭐⭐ | Autentisering | Finn svar via avansert research | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet.html) |
| Two Factor Authentication | ⭐⭐⭐⭐⭐ | Autentisering | Knekk TOTP-kode for en bruker | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Multifactor_Authentication_Cheat_Sheet.html) |
| NoSQL Exfiltration | ⭐⭐⭐⭐⭐ | Injeksjon | Eksporter alle ordrer via NoSQL-injeksjon | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet.html) |
| Email Leak | ⭐⭐⭐⭐⭐ | Sensitiv data | Stjel data på tvers av domener | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/XS_Leaks_Cheat_Sheet.html) |
| Retrieve Blueprint | ⭐⭐⭐⭐⭐ | Sensitiv data | Last ned produksjonstegning | |
| Memory Bomb | ⭐⭐⭐⭐⭐ | Deserialisering | Utnytt sårbart filopplastingsendepunkt | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet.html) |
| Blocked RCE DoS | ⭐⭐⭐⭐⭐ | Deserialisering | Remote Code Execution (blokkert) | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet.html) |
| Unsigned JWT | ⭐⭐⭐⭐⭐ | Sårbare komponenter | Forge JWT uten signatur | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/JSON_Web_Token_for_Java_Cheat_Sheet.html) |
| Kill Chatbot | ⭐⭐⭐⭐⭐ | Sårbare komponenter | Deaktiver støttechatboten permanent | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Vulnerable_Dependency_Management_Cheat_Sheet.html) |
| Local File Read | ⭐⭐⭐⭐⭐ | Sårbare komponenter | Les vilkårlig fil fra webserver | |
| Leaked API Key | ⭐⭐⭐⭐⭐ | Sensitiv data | Finn lekket API-nøkkel | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html) |
| Supply Chain Attack | ⭐⭐⭐⭐⭐ | Sårbare komponenter | Finn sikkerhetsrisiko i avhengighetskjeden | |
| Frontend Typosquatting | ⭐⭐⭐⭐⭐ | Sårbare komponenter | Finn falsk pakke i frontendkoden | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Vulnerable_Dependency_Management_Cheat_Sheet.html) |
| XXE DoS | ⭐⭐⭐⭐⭐ | XXE | XML-basert tjenestenektangrep | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html) |
| Blockchain Hype | ⭐⭐⭐⭐⭐ | Skjult sikkerhet | Finn informasjon om token-salg før lansering | |
| Change Bender's Password | ⭐⭐⭐⭐⭐ | Autentisering | Endre passord uten injeksjon eller glemt passord | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html) |
| Leaked Access Logs | ⭐⭐⭐⭐⭐ | Observerbarhet | Finn lekket passord via søk på internett | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Credential_Stuffing_Prevention_Cheat_Sheet.html) |
| Login Support Team | ⭐⭐⭐⭐⭐⭐ | Feilkonfigurasjon | Logg inn som support-teamet | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html) |
| Forged Coupon | ⭐⭐⭐⭐⭐⭐ | Kryptografi | Forge kupongkode med 80%+ rabatt | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet.html) |
| Forged Signed JWT | ⭐⭐⭐⭐⭐⭐ | Sårbare komponenter | Forge RSA-signert JWT | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/JSON_Web_Token_for_Java_Cheat_Sheet.html) |
| Premium Paywall | ⭐⭐⭐⭐⭐⭐ | Kryptografi | Lås opp premiuminnhold | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Key_Management_Cheat_Sheet.html) |
| Successful RCE DoS | ⭐⭐⭐⭐⭐⭐ | Deserialisering | Remote Code Execution som blokkerer serveren | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet.html) |
| Wallet Depletion | ⭐⭐⭐⭐⭐⭐ | Diverse | Ta ut mer ETH enn du satte inn | |
| Arbitrary File Write | ⭐⭐⭐⭐⭐⭐ | Sårbare komponenter | Overskriv en fil på serveren | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Vulnerable_Dependency_Management_Cheat_Sheet.html) |
| SSRF | ⭐⭐⭐⭐⭐⭐ | Tilgangskontroll | Server-Side Request Forgery | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet.html) |
| SSTi | ⭐⭐⭐⭐⭐⭐ | Injeksjon | Server-Side Template Injection / RCE | |
| Multiple Likes | ⭐⭐⭐⭐⭐⭐ | Anti-automasjon | Like en anmeldelse tre ganger som samme bruker | |
| Imaginary Challenge | ⭐⭐⭐⭐⭐⭐ | Kryptografi | Løs utfordring #999 (eksisterer ikke) | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet.html) |
| Video XSS | ⭐⭐⭐⭐⭐⭐ | XSS | Injiser XSS i en promovideo | [![](docs/open-in-new.svg)](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html) |

---

## Sammendrag: Trinn → Antall oppgaver

| Klassetrinn | Vanskelighet | Antall oppgaver |
|-------------|-------------|-----------------|
| 8.–10. klasse | ⭐ | 12 |
| VGS1 (IT1) | ⭐⭐ | 16 |
| VGS2 (IT2 / VG2 IT) | ⭐⭐⭐ | 21 |
| VGS3 / Fordypning | ⭐⭐⭐⭐ | 27 |
| Ekspert / CTF | ⭐⭐⭐⭐⭐–⭐⭐⭐⭐⭐⭐ | 30 |
| **Totalt** | | **106** |

---

## OWASP-kategorier og læreverdi

| OWASP-kategori | Norsk navn | Første møte |
|----------------|-----------|-------------|
| Broken Access Control | Svak tilgangskontroll | VGS1 |
| Cryptographic Failures | Kryptografifeil | VGS1 |
| Injection (SQL/NoSQL) | Injeksjon | VGS1–VGS2 |
| Insecure Design | Usikker design | VGS2 |
| Security Misconfiguration | Feilkonfigurasjon | VGS1–VGS2 |
| Vulnerable Components | Sårbare komponenter | VGS2–VGS3 |
| Authentication Failures | Autentiseringsfeil | VGS1–VGS2 |
| XSS (Cross-Site Scripting) | Skriptinjeksjon | 8.–10. / VGS1 |
| Sensitive Data Exposure | Sensitiv datalekkasje | VGS1–VGS2 |
| XXE / Deserialization | Avanserte injeksjoner | Ekspert |
