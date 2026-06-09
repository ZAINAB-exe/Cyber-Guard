# Final Security Audit Report

## 1. Project Overview
CyberGuard SecOps secures a Node.js API and provides a Python CLI for authorised target-based security checks.

## 2. Scope
- Target application: `http://localhost:3000`
- Testing type: defensive security audit and hardening validation
- Tools: CyberGuard CLI, OWASP ZAP, Nikto, Lynis, SQLMap/Burp Suite evidence if available, manual checks

## 3. Implemented Security Controls
- Rate limiting on general API and login endpoint
- Restricted CORS policy
- API key protection for sensitive routes
- CSP, HSTS, X-Frame-Options, X-Content-Type-Options, Referrer-Policy
- Safe server-side data access for SQL injection prevention
- CSRF token route and CSRF-protected form route
- Failed-login logging and suspicious login summary endpoint
- Fail2Ban/OSSEC sample configuration
- Docker hardening, Trivy container scanning, Dependabot and dependency scanning workflow

## 4. Findings Summary
| ID | Severity | Area | Finding | Status |
|---|---|---|---|---|
| F-01 | Medium | Monitoring | Fail2Ban/OSSEC requires server installation path update | Documented |
| F-02 | Info | Deployment | HTTPS must be enabled in production reverse proxy | Planned/Required |

## 5. Evidence
Attach CLI generated JSON/Markdown reports, screenshots of headers, rate-limit response, and GitHub workflow output.

## 6. Conclusion
The application includes the required Week 4–6 security improvements and provides clear evidence for final submission. Production deployment should use HTTPS, secret rotation, and real server monitoring.
