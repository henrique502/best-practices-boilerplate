---
title: Security Best Practices
inclusion: always
---

# Security Best Practices

## Code Security
- Never hardcode secrets, API keys, or passwords in source code
- Use environment variables or a secrets manager (e.g., AWS Secrets Manager, HashiCorp Vault) for configuration
- Validate and sanitize all user inputs at the boundary (controllers, handlers)
- Use parameterized queries or ORM methods to prevent SQL injection — never concatenate user input into queries
- Implement proper authentication and authorization; prefer established libraries (e.g., Passport.js, NextAuth)
- Escape output to prevent XSS — use templating engines with auto-escaping enabled
- Avoid `eval()`, `Function()`, and dynamic code execution with untrusted data

## Dependency Management
- Keep dependencies updated; use tools like `npm audit`, Dependabot, or Renovate
- Pin exact versions in lock files (package-lock.json, pnpm-lock.yaml, poetry.lock)
- Review third-party packages before adding — check maintenance status, download count, and known vulnerabilities
- Remove unused dependencies to reduce attack surface
- Prefer well-known, actively maintained packages over obscure alternatives

## Data Protection
- Encrypt sensitive data at rest (AES-256) and in transit (TLS 1.2+)
- Use HTTPS for all communications — never allow HTTP in production
- Implement proper session management with secure, HttpOnly, SameSite cookies
- Use secure headers: HSTS, Content-Security-Policy, X-Content-Type-Options, X-Frame-Options
- Hash passwords with bcrypt, scrypt, or Argon2 — never use MD5 or SHA-1 for passwords
- Follow OWASP Top 10 guidelines as a minimum security baseline

## Infrastructure Security
- Apply least privilege principle for all IAM roles and service accounts
- Enable logging and monitoring (CloudWatch, Datadog, or equivalent)
- Use network segmentation — isolate databases and internal services from public access
- Implement proper backup strategies with tested restore procedures
- Conduct regular security audits and penetration testing

## Development Practices
- Use static code analysis tools (ESLint security plugins, SonarQube, Semgrep)
- Implement security testing in CI/CD pipelines (SAST, DAST, dependency scanning)
- Require code reviews with security focus before merging
- Never log sensitive data (passwords, tokens, PII) — use structured logging with redaction
- Use `.env.example` files to document required environment variables without exposing values
