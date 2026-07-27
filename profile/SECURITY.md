# 🛡️ Security & Responsible Disclosure Policy

At Atelier Busco, security is an architectural requirement, not an afterthought.

---

## 🔑 Core Security Principles

- **Least Privilege Access:** Infrastructure and database user accounts strictly scoped to necessary execution permissions.
- **Zero-Knowledge Secrets:** API keys, database credentials, and secrets are managed via encrypted environment managers (AWS Secrets Manager / Vercel Vault).
- **Stateless & Rotational Authentication:** Short-lived access JWTs paired with secure, rotatable refresh tokens stored in HTTP-Only cookies or encrypted native storage (`flutter_secure_storage`).
- **Automated Hardening:** Global HTTP security headers (`helmet`), application-wide rate limiting (`throttler`), and global exception filtering with tracing IDs.

---

## 🚨 Reporting Vulnerabilities

If you discover a potential security vulnerability within any Atelier Busco open-source project or public property, please report it immediately to our security team.

* **Email:** security@atelierbusco.com / info@atelierbusco.com
* **Response SLA:** We acknowledge all security inquiries within 24 business hours.

Please do not publicly disclose vulnerabilities until our team has had the opportunity to evaluate and patch the issue.
