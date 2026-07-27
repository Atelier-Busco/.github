# 🏛️ Atelier Busco — Public Architecture & Engineering Standards

At Atelier Busco, we build software with a **Senior-first, zero-cruft philosophy**. Our technical choices are governed by long-term maintainability, developer speed, performance, and low operational overhead (LTV focus).

---

## ⚡ Web Frontend Standard: Angular 22 (CSR + Zoneless)

For dynamic web products requiring premium responsiveness and strict state governance, our default choice is **Angular 22** in Client-Side Rendering (CSR) mode.

* **Natively Zoneless:** We eliminate `zone.js` overhead (`provideExperimentalZonelessChangeDetection()`), yielding surgical UI updates via Signals and significantly smaller bundle sizes.
* **Esbuild & Vite Engine:** Sub-second build loops and modern ESM bundling powered by the Application Builder.
* **Component-First Architecture:** 100% Standalone components by default, eliminating unnecessary `NgModule` boilerplate.
* **Signal-Driven Reactive Forms & State:** Native control flow (`@if`, `@for`, `@empty`) combined with `input()` / `output()` Signals.

---

## 🚀 Backend Standard: NestJS 11 Serverless

Our backend architectures are built for high availability and low idle cost on cloud infrastructure (AWS Lambda).

* **Security by Default:** Global `helmet` protection, strict CORS governance, and application-wide rate limiting (`@nestjs/throttler`).
* **Self-Documenting APIs:** 100% Swagger coverage (`@nestjs/swagger`) enforced in every commit.
* **Decoupled Event Handling:** Zero direct messaging SDK integration in business logic; all alerts dispatch through our isolated `NotificationService`.
* **Structured Observability:** Native JSON logging tagged with unique `requestId` tracing per execution context.

---

## 🛡️ Core Engineering Practices

1. **Zero Hardcoded Secrets:** Mandatory environment variable isolation for all deployment targets.
2. **Spec-Anchored Development:** Every system is designed with explicit boundaries (`SPEC.md` / `CONTEXT.md`) before writing production code.
3. **No Unhandled Promises:** Async try-catch blocks and transaction managers (`QueryRunner`) for multi-entity writes.
