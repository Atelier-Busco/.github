# 🤝 Open Source Contribution Guidelines

First off, thank you for considering contributing to **Atelier Busco's public repositories and blueprints**! We build software with precision, clarity, and enterprise rigor.

---

## 📐 Our Engineering Expectations

1. **Strict TypeScript & Standalone Standard:**
   - Web projects follow **Angular 22 Zoneless** patterns (Signals, Application Builder, no `zone.js`).
   - Node.js projects follow **NestJS 11** modular standards with mandatory DTO validation (`class-validator`) and Swagger decorators.
2. **Zero Hardcoded Values:** Secrets, URLs, and environment flags must be injected via `.env` configurations.
3. **Commit Message Boundary:**
   - Standard format: `type: concise description in English` (e.g., `fix: resolve token refresh race condition`).
   - Never mix refactoring with bug fixes in the same commit.

---

## 🔄 Pull Request Workflow

1. Fork the repository and create your feature branch from `main`.
2. Ensure unit tests pass (`npm run test`) and typechecking is clean before submitting.
3. Open a Pull Request with a clear description of the problem solved and technical impact.
