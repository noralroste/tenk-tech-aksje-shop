# Contributing with Claude AI Assistant

This guide helps contributors use Claude (AI assistant) effectively when working on OWASP Juice Shop while maintaining code quality and adhering to project standards.

> This document is supposed to be the primary source of context for **all** AI tools. Context files of tools other than Claude should refer to [this `CLAUDE.md` file](CLAUDE.md) for detailed guidelines. This is already the case for:
> * GitHub CoPilot ([`.github/copilot-instructions.md`](../.github/copilot-instructions.md))
> * Codeium ([`.codeium/instructions.md`](../.codeium/instructions.md))
> * Continue.dev ([`.continue/instructions.md`](../.continue/instructions.md))

## Before You Start

Claude can assist with various development tasks, but all contributions must still meet the requirements in [CONTRIBUTING.md](../CONTRIBUTING.md). The AI is a tool to enhance productivity, not a replacement for understanding the codebase and contribution guidelines.

## Recommended Use Cases

### ✅ Good Use Cases

- **Code Analysis**: Understanding existing code structure and patterns
- **Refactoring**: Improving code quality while maintaining functionality
- **Test Writing**: Creating unit, integration, and e2e tests
- **Bug Fixing**: Identifying and resolving issues
- **Documentation**: Writing clear comments and documentation

### ⚠️ Use with Caution

- **Challenge Development**: Consult with maintainers before creating new challenges - AI-generated challenges risk being duplicate, unsolvable, or dysfunctional
- **Security Vulnerabilities**: Ensure AI-suggested vulnerabilities are intentional and appropriate for the project
- **Dependencies**: Verify any suggested package updates for compatibility
- **Architecture Changes**: Discuss major structural changes with maintainers first

## Essential Guidelines

### 1. Clean Up AI-Generated Noise

**Required** per CONTRIBUTING.md rule #6: Remove unnecessary AI-generated content before submitting PRs.

Remove:
- Verbose comments explaining obvious code
- Generic placeholder comments
- Overly detailed docstrings for simple functions
- Repetitive explanations

Keep:
- Meaningful comments for complex logic
- Challenge hints and metadata
- Security-relevant documentation

### 2. Code Style Compliance

Always run ESLint before committing:
```bash
npm run lint
```

Claude should suggest code following [JS Standard Style](http://standardjs.com/), but always verify.

### 3. Testing Requirements

For any code changes Claude helps with:
- **Unit/Integration Tests**: New features and changes should have tests
- **E2E Tests**: Required for new/modified challenges
- **RSN (Refactoring Safety Net)**: Required when modifying existing code that is part of a coding challenge
- **Run Tests Locally**:
  ```bash
  npm test                    # Unit tests
  npm run frisby              # API integration tests
  npm start & npm run cypress:open  # E2E tests
  npm run rsn                 # Refactoring Safety Net (for code changes impacting coding challenge snippets)
  ```

### 4. Commit Sign-off

All commits must be signed off (DCO):
```bash
git commit -s -m "Your commit message"
```

### 5. Branch and PR Strategy

- Work on `develop` branch-based feature branches
- Keep PRs focused on a single scope
- Reference related issues in PR descriptions

## Development Workflow with Claude

### 1. Understanding the Codebase
```
Ask Claude to:
- Explain specific components or patterns
- Identify where to implement new features
- Trace code execution paths
```

### 2. Implementation
```
Ask Claude to:
- Generate initial implementation
- Suggest test cases
- Review for security implications
```

### 3. Quality Assurance
```
Before committing:
1. Remove AI-generated noise
2. Run npm run lint
3. Run relevant test suites
4. If you modified code that is part of a coding challenge, run npm run rsn
5. Manually verify functionality
6. Check for unintended changes
```

### 4. Documentation
```
Ask Claude to:
- Write clear commit messages
- Draft PR descriptions
- Document complex logic
```

## Anti-Patterns to Avoid

❌ **Don't**: Accept AI suggestions blindly without understanding them
✅ **Do**: Review and understand all AI-generated code

❌ **Don't**: Submit PRs with verbose AI-generated comments
✅ **Do**: Clean up and keep only meaningful comments

❌ **Don't**: Skip testing because AI "seems confident"
✅ **Do**: Always run the full test suite

❌ **Don't**: Use AI for contribution farming or trivial changes
✅ **Do**: Make meaningful contributions that add value

❌ **Don't**: Let AI modify translations directly
✅ **Do**: Use [Crowdin](https://crowdin.com/project/owasp-juice-shop) for translations

## Example: Fixing a Bug

```bash
# 1. Ask Claude to analyze the issue
"Help me understand why the basket total calculation is incorrect"

# 2. Locate the problematic code
"Show me where basket totals are calculated"

# 3. Implement the fix with Claude's help
"Fix the calculation to properly handle discount edge cases"

# 4. Generate tests
"Create unit tests to cover the discount calculation edge cases"

# 5. Quality checks
npm run lint
npm test
npm run rsn  # If the fix affects code used in a coding challenge

# 6. Clean up and commit with sign-off
git commit -s -m "Fix basket total calculation for discount edge cases"
```

## Quality Checklist

Before submitting a Claude-assisted PR:

- [ ] Code follows JS Standard Style (ESLint passes)
- [ ] AI-generated noise removed
- [ ] Tests added/updated and passing
- [ ] RSN check passing (if modified code relevant for a coding challenge)
- [ ] Manual testing completed
- [ ] Commits are signed off
- [ ] PR based on `develop` branch
- [ ] Single, focused scope
- [ ] All CI checks passing
- [ ] PR based on `develop` branch
- [ ] PR contains AI Tool Disclosure and Affirmation

## Refactoring Safety Net (RSN)

When modifying existing code that is part of a coding challenge, you must run the RSN to ensure code snippet and fix option files remain consistent:

```bash
npm run rsn
```

**What it does:**
- Checks for unexpected changes in coding challenge files
- Detects accidental differences in lines of code
- Lists any inconsistencies found

**When to run:**
- After refactoring code that is part of any coding challenge
- After changing original source files referenced in challenges
- Before committing changes that touch challenge-related code

**If RSN fails:**
- Review the listed differences
- If changes are intentionally part of the coding challenge, update the differences cache:
  ```bash
  npm run rsn:update
  ```
- If changes are unintentional, fix the affected files

Learn more: [Code Snippets Documentation](https://pwning.owasp-juice.shop/companion-guide/latest/part5/code-snippets.html)

## Getting Help

- Review the [detailed contribution guidelines](https://pwning.owasp-juice.shop/companion-guide/latest/part3/contribution.html)
- Check existing issues and PRs for examples
- Join the community on Slack or Gitter
- Ask questions via Slack or comment on the GitHub issue you are working on

## Remember

Claude is a powerful tool for productivity, but you are responsible for the quality and correctness of your contributions. Always review, test, and understand the code before submitting.

---

## Workshop Hosting

Workshop instances run on Render (free tier). **Free tier gives 750 hours/month total across all services.**
Running 5 instances continuously exhausts the quota in 6 days.

> ⛔ **ALWAYS suspend instances when the workshop is done. Never leave instances running unnecessarily.**
> If you deploy workshop instances, your first responsibility when done is to suspend them.

### Instances

| Group | URL |
|-------|-----|
| Gruppe 1 | https://aksje-shop-gruppe-1.onrender.com |
| Gruppe 2 | https://aksje-shop-gruppe-2.onrender.com |
| Gruppe 3 | https://aksje-shop-gruppe-3.onrender.com |
| Gruppe 4 | https://aksje-shop-gruppe-4.onrender.com |
| Gruppe 5 | https://aksje-shop-gruppe-5.onrender.com |

Note: Free tier instances auto-sleep after 15 minutes of inactivity (~1 min cold start on first request). Sleeping and suspended instances do not count toward the 750 hour/month limit — only actively running instances do.

### Deploy workshop

Trigger via GitHub Actions (requires GitHub access — no Render API key needed):

```bash
gh workflow run deploy-workshop.yml \
  --repo sb1u-tenk-tech/tenk-tech-aksje-shop \
  -f groups=3 \
  -f ttl_hours=8
```

Or via GitHub UI: Actions → "Deploy workshop instances" → Run workflow.

Instances are automatically suspended after `ttl_hours`. The cleanup workflow runs every 2 hours.

### Suspend immediately (when workshop is done)

```bash
gh workflow run cleanup-workshop.yml \
  --repo sb1u-tenk-tech/tenk-tech-aksje-shop \
  -f suspend_all=true
```

Or via GitHub UI: Actions → "Cleanup expired workshop instances" → Run workflow → check "Suspend all workshop instances immediately".

### When helping with workshop deployment

**ALWAYS ask before deploying — never deploy without explicit answers to both:**
1. How many groups? (1–5, default suggestion: 1)
2. TTL in hours? (1–24, default suggestion: 1) — deploying without a TTL is not allowed

Prefer short TTL values — instances can always be redeployed if the workshop runs longer.

After deploy: remind the user to suspend instances when the workshop is done.
After the workshop: proactively ask if instances should be suspended.
