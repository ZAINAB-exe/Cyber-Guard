# Completed Security Evidence Sample

This file can be used as ready evidence for the internship submission after the project is run locally.

## Week 4 Evidence

| Requirement | Evidence in Project |
|---|---|
| Failed-login monitoring | `/auth/login` records every attempt in the lightweight JSON data store and writes failed attempts to `security.log`. |
| Alert for multiple failed logins | After 3 failed logins from the same IP in 30 minutes, `failed_login_alert` is written to the log. |
| Fail2Ban/OSSEC | Example files are provided in `configs/fail2ban/` and `configs/ossec/`. |
| Rate limiting | General API limiter and stricter `/auth/login` limiter are configured. |
| CORS restriction | Only origins from `ALLOWED_ORIGINS` are accepted. |
| API authentication | `/incidents` and `/auth/failed-logins` require `x-api-key`. |
| Security headers | Helmet sets CSP, HSTS, X-Frame-Options, X-Content-Type-Options and Referrer-Policy. |

## Week 5 Evidence

| Requirement | Evidence in Project |
|---|---|
| Reconnaissance | SecOps CLI performs authorised target checks and records results. |
| SQL injection testing/fix | Login uses safe exact-match data access instead of string concatenation. |
| CSRF protection | `csurf` protects `/csrf/protected-form`; token available from `/csrf/token`. |
| Burp/SQLMap report support | Ethical hacking report template includes sections for tool results and fixes; command guidance is provided in `docs/MANUAL_TESTING_COMMANDS.md`. |

## Week 6 Evidence

| Requirement | Evidence in Project |
|---|---|
| OWASP ZAP/Nikto/Lynis | CLI can call these tools if installed; otherwise records them as skipped. |
| OWASP Top 10 mapping | `docs/OWASP_TOP_10_MAPPING.md`. |
| Dependency scanning | GitHub Actions runs `npm audit`; Dependabot is configured for weekly dependency update pull requests. |
| Docker image scanning | Optional GitHub Actions Trivy container scan job is included; local Docker execution is not required on a limited laptop. |
| Secure deployment | Main demo runs with Node.js/Python; optional Docker files show non-root user, read-only app filesystem, no-new-privileges, dropped capabilities and tmpfs runtime storage. |
| Final report/video | Final audit template and 4–5 minute video script are included. |
