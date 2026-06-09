# Ethical Hacking Report

## Rules of Engagement
Testing was performed only on an authorised local/test application.

## Reconnaissance
- Target: `http://localhost:3000`
- Open service: Node.js/Express API
- Key endpoints: `/health`, `/auth/login`, `/csrf/token`, `/incidents`

## Vulnerability Testing Summary
| Test | Tool/Method | Result | Fix Applied |
|---|---|---|---|
| SQL Injection | Manual payload review / SQLMap in test lab if approved | Login uses exact-match lookup with no dynamic SQL execution | No string-concatenated SQL; if later migrated to SQL, use parameterised queries |
| CSRF | Token validation test | Protected route requires CSRF token | `csurf` middleware added |
| Brute Force | Repeated failed login attempts | Rate limiter returns 429 after threshold | `express-rate-limit` added |
| Headers | Header check | Helmet sets CSP/HSTS and related headers | `helmet` configured |
| CORS | Origin test | Unapproved origin blocked | Restricted origin allowlist |

## Manual Tool Evidence to Attach

- SQLMap result or screenshot using a captured authorised request.
- Burp Suite CSRF test screenshot showing failure without token and success with token.
- Optional Nikto/ZAP output if available.

## Notes
Do not test third-party systems without written permission.
