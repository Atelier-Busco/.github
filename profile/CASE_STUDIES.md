# 📐 Architectural Case Studies & ROI Breakdown

This document highlights real-world technical challenges solved by **Atelier Busco**, showcasing our architectural patterns, engineering trade-offs, and measurable business outcomes.

---

## 🏦 Case Study 1: B2B FinTech & Factoring SaaS Platform

### 🎯 Business Problem
SMEs needed real-time invoice discounting, risk evaluation, and advance calculation without manual spreadsheet overhead. The platform required zero transaction downtime, strict multi-tenant data isolation, and auditable financial workflows.

### 🏗️ Technical Architecture
- **Frontend:** Angular 22 Zoneless CSR + Signal Forms for real-time invoice calculations and dynamic risk tables.
- **Backend:** Modular NestJS API with strict TypeORM transaction managers (`QueryRunner`) to ensure atomic multi-ledger updates.
- **Security:** Short-lived JWTs, HTTP-Only rotational refresh tokens, and global exception filtering with `requestId` tracing.

### 📈 Business Impact
- **Deployment Speed:** Shipped fully operational v1.0 MVP in **85 days**.
- **Performance:** Reduced financial dashboard calculation latencies by **65%** via Zoneless Angular Signals.
- **Reliability:** 100% data consistency across invoice approval and payout cycles.

---

## 🤖 Case Study 2: Enterprise AI Orchestration (Prompt Engine & Memory Service)

### 🎯 Business Problem
Integrating third-party LLMs directly into client workflows created compliance risks, unmanaged token costs, and lack of state persistence across customer support and internal query channels.

### 🏗️ Technical Architecture
- **Orchestration Layer:** Proprietary `Prompt Engine API` acting as a secure gateway for prompt versioning, token budget guardrails, and SAST validation.
- **Context Layer:** Isolated `Memory Service` combining vector embeddings with relational metadata to enable long-term operational memory.
- **Backend Infrastructure:** Serverless Node.js / FastAPI running on AWS Lambda with async background queue processing.

### 📈 Business Impact
- **Cost Reduction:** Cut LLM API costs by **40%** through prompt optimization and caching.
- **Governance:** Full audit trail for all AI-generated responses across B2B channels.

---

## 🏛️ Case Study 3: High-Reliability GovTech & Civic Analytics

### 🎯 Business Problem
Public sector and civic monitoring initiatives required processing massive volumes of media, legislative data, and public records with strict availability and zero infrastructure bloat.

### 🏗️ Technical Architecture
- **Data Pipelines:** Automated ETL crawlers built with Python/FastAPI deployed on AWS serverless tasks.
- **API & Visualization:** NestJS backend powering a lightweight Angular dashboard with server-side caching and static CDN edge delivery via AWS CloudFront.

### 📈 Business Impact
- **Uptime:** 99.95% availability during peak legislative decision events.
- **Infrastructure Overhead:** Near-zero idle hosting costs due to serverless pay-per-execution architecture.
