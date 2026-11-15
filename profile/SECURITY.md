# 🛡️ Security & Responsible Disclosure Policy

At Atelier Busco SpA, security is an architectural requirement, not an afterthought. We maintain enterprise-grade security standards across our proprietary platforms, open-source repositories, and client infrastructure.

🌐 **[Versión en Español (Spanish Version)](es/SECURITY.md)**

---

## 🏛️ Cloud Security Alliance (CSA STAR Level 1)

Atelier Busco is listed on the **Cloud Security Alliance (CSA) STAR Registry (Level 1)** for our core cloud services. This certification demonstrates our commitment to transparency, rigorous cloud security controls, and adherence to CSA Cloud Controls Matrix (CCM) best practices.

---

## 🔑 Core Security Principles

- **Least Privilege Access:** Infrastructure, container instances, and database accounts are strictly scoped to minimum execution permissions.
- **Zero-Knowledge Secrets:** API keys, database credentials, and certificates are managed via encrypted environment managers (AWS Secrets Manager, Azure Key Vault, or Vercel Vault) with automated rotation.
- **Stateless & Rotational Authentication:** Short-lived access JWTs paired with secure, rotatable refresh tokens stored in HTTP-Only cookies or encrypted native storage (`flutter_secure_storage`).
- **Automated Hardening:** Global HTTP security headers (`helmet`), application-wide rate limiting (`throttler`), and global exception filtering with contextual `requestId` tracing.
- **Continuous Auditing & SAST/DAST:** Continuous static and dynamic application security testing embedded into automated GitHub Actions CI/CD pipelines.

---

## 🚨 Reporting Vulnerabilities

If you discover a potential security vulnerability within any Atelier Busco open-source project or public property, please report it immediately to our security team:

* **Email:** security@atelierbusco.com / info@atelierbusco.com
* **Response SLA:** We acknowledge all security inquiries within 24 business hours.

Please do not publicly disclose vulnerabilities until our team has had the opportunity to evaluate and patch the issue.
