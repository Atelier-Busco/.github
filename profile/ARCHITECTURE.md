# 🏛️ Atelier Busco — Public Architecture & Engineering Standards

At Atelier Busco, we build software with a **Senior-first, zero-cruft philosophy**. Our technical choices are governed by long-term maintainability, developer speed, performance, and low operational overhead (LTV focus).

🌐 **[Versión en Español (Spanish Version)](es/ARCHITECTURE.md)**

---

## 🟢 Runtime Standard: Node.js 22+ LTS

All backend services, serverless functions, microservices, and developer tooling strictly require **Node.js 22+ LTS** as the minimum runtime engine:
* **Modern V8 Engine:** Native performance enhancements for high-concurrency microservices.
* **Native Web Standards:** Utilization of built-in `fetch`, `WebSocket`, and native crypto modules without bulky legacy dependencies.
* **ESM & Subpath Imports:** Strict ES Module support and clean internal package encapsulation.
* **Native Structured Logging:** High-throughput JSON observability integrated with `requestId` context tracing.

---

## 🚀 Backend Standard: NestJS 11 Serverless & Fastify

Our backend architectures are built for high availability and low idle cost on cloud infrastructure (AWS Lambda & Azure):
* **High-Throughput Adapters:** NestJS paired with Fastify or lightweight Serverless handlers for sub-millisecond route resolution.
* **Security by Default:** Global `helmet` headers, strict CORS policies, and application-wide rate limiting (`@nestjs/throttler`).
* **Strict Payload Validation:** Mandatory `class-validator` DTOs with strict whitelisting to eliminate unverified inputs.
* **Self-Documenting APIs:** 100% Swagger OpenAPI coverage (`@nestjs/swagger`) enforced in every commit.
* **Decoupled Event Handling:** Zero direct third-party messaging SDKs in domain logic; all alerts dispatch through our isolated `NotificationService`.

---

## ⚡ Web Frontend Standard: Angular 22 (CSR + Zoneless)

For dynamic web products requiring premium responsiveness and strict state governance, our default choice is **Angular 22** in Client-Side Rendering (CSR) mode:
* **Natively Zoneless:** We eliminate `zone.js` overhead (`provideExperimentalZonelessChangeDetection()`), yielding surgical UI updates via Signals and significantly smaller bundle sizes.
* **Esbuild & Vite Engine:** Sub-second build loops and modern ESM bundling powered by the Application Builder.
* **Component-First Architecture:** 100% Standalone components by default, eliminating unnecessary `NgModule` boilerplate.
* **Signal-Driven Reactive State:** Native control flow (`@if`, `@for`, `@empty`) combined with `input()` / `output()` Signals.

---

## 🧠 DeepTech, AI & Spatial Data Architecture

Our data layer is engineered for enterprise workflows, multimodal AI, and high-precision spatial processing:
* **Relational Core + pgvector:** PostgreSQL serves as our primary datastore, leveraging the `pgvector` extension for efficient vector embeddings, RAG pipelines, and semantic similarity search.
* **Geospatial Intelligence (PostGIS):** Advanced spatial indexing and topological routing for logistics, fleet monitoring, and agricultural territory mapping.
* **GPU Orchestration & Computer Vision:** Offloading heavy inference workloads (Meta SAM 3.1, Meta Llama, speech-to-text NLP) to scalable GPU clusters (AWS EC2 G5 / Modal) with asynchronous queueing (SQS / BullMQ).
* **AI Governance (Prompt Engine & Memory Service):** Strict separation between user inputs and foundation models via input sanitization, token budgeting, and stateful memory retention.

---

## 🛡️ Core Engineering Practices

1. **Zero Hardcoded Secrets:** Mandatory environment variable isolation (AWS Secrets Manager / Azure Vault) for all deployment targets.
2. **Spec-Anchored Development:** Every system is designed with explicit boundaries (`SPEC.md` / `CONTEXT.md`) before writing production code.
3. **Strict Async Governance:** Explicit try-catch blocks and transaction managers (`QueryRunner`) for multi-entity transactional integrity.
4. **Clean Commits & Continuous Integration:** Atomic commits adhering to `type: concise description in English` validated through automated CI/CD pipelines.
