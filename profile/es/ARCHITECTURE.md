# 🏛️ Atelier Busco — Estándares Públicos de Arquitectura e Ingeniería

En Atelier Busco construimos software con una **filosofía Senior sin relleno**. Nuestras decisiones técnicas están regidas por la mantenibilidad a largo plazo, velocidad de desarrollo, alto rendimiento y bajos costos operativos (enfoque en LTV).

🌐 **[English Version](../ARCHITECTURE.md)**

---

## 🟢 Estándar de Runtime: Node.js 22+ LTS

Todos los servicios de backend, funciones serverless, microservicios y herramientas de terminal requieren estrictamente **Node.js 22+ LTS** como motor de ejecución mínimo:
* **Motor V8 Moderno:** Mejoras nativas de rendimiento para microservicios de alta concurrencia.
* **Estándares Web Nativos:** Uso de `fetch`, `WebSocket` y módulos criptográficos nativos sin dependencias externas pesadas.
* **Soporte ESM & Subpath Imports:** Soporte estricto de ES Modules y encapsulación limpia de paquetes internos.
* **Logging Estructurado Nativo:** Observabilidad JSON de alto rendimiento vinculada a la trazabilidad por `requestId`.

---

## 🚀 Estándar Backend: NestJS 11 Serverless & Fastify

Nuestras arquitecturas de backend están construidas para alta disponibilidad y cero costos fijos en infraestructura cloud (AWS Lambda y Azure):
* **Adaptadores de Alto Rendimiento:** NestJS combinado con Fastify o manejadores serverless ligeros para resolución de rutas en submilisegundos.
* **Seguridad por Defecto:** Cabeceras globales con `helmet`, políticas estrictas de CORS y limitación de tasa a nivel global (`@nestjs/throttler`).
* **Validación Estricta de Payloads:** DTOs obligatorios con `class-validator` y modo whitelist para eliminar datos no autorizados.
* **APIs Auto-Documentadas:** 100% de cobertura en Swagger OpenAPI (`@nestjs/swagger`) verificado en cada commit.
* **Desacoplamiento de Eventos:** Cero integración directa de SDKs de terceros en la lógica de dominio; todo envío se despacha a través de nuestro `NotificationService` independiente.

---

## ⚡ Estándar Frontend Web: Angular 22 (CSR + Zoneless)

Para productos web dinámicos que requieren máxima capacidad de respuesta y un manejo de estado estricto, nuestra opción por defecto es **Angular 22** en modalidad de Renderizado del Lado del Cliente (CSR):
* **Nativamente Zoneless:** Eliminamos la sobrecarga de `zone.js` (`provideExperimentalZonelessChangeDetection()`), logrando actualizaciones quirúrgicas de UI mediante Signals y bundles notablemente más ligeros.
* **Motor Esbuild & Vite:** Ciclos de compilación en milisegundos mediante el Application Builder de Angular.
* **Arquitectura Basada en Componentes:** Componentes 100% Standalone por defecto, eliminando boilerplate de `NgModule`.
* **Manejo de Estado Reactivo con Signals:** Flujo de control nativo (`@if`, `@for`, `@empty`) combinado con Signals de entrada y salida (`input()` / `output()`).

---

## 🧠 Arquitectura DeepTech, IA & Datos Espaciales

Nuestra capa de datos está diseñada para flujos de trabajo enterprise, IA multimodal y procesamiento espacial de alta precisión:
* **Núcleo Relacional + pgvector:** PostgreSQL actúa como almacén de datos primario, aprovechando la extensión `pgvector` para embeddings vectoriales, flujos RAG y búsqueda de similitud semántica.
* **Inteligencia Geoespacial (PostGIS):** Indexación espacial avanzada y ruteo topológico para logística, flotas y zonificación agrícola.
* **Orquestación GPU & Visión Computacional:** Descarga de cargas pesadas de inferencia (Meta SAM 3.1, Meta Llama, NLP de voz a texto) hacia clusters GPU escalables (AWS EC2 G5 / Modal) mediante colas asíncronas (SQS / BullMQ).
* **Gobernanza de IA (Prompt Engine & Memory Service):** Separación estricta entre la entrada de usuario y los modelos fundacionales mediante sanitización de entradas, control presupuestario de tokens y memoria operativa persistente.

---

## 🛡️ Prácticas Principales de Ingeniería

1. **Cero Secretos en Código:** Aislamiento obligatorio de variables de entorno mediante AWS Secrets Manager o Azure Vault.
2. **Desarrollo Anclado a Especificaciones:** Cada sistema se diseña con límites explícitos (`SPEC.md` / `CONTEXT.md`) antes de escribir código de producción.
3. **Manejo Estricto de Operaciones Asíncronas:** Bloques try-catch explícitos y gestores de transacciones (`QueryRunner`) para garantizar integridad multi-tabla.
4. **Commits Limpios e Integración Continua:** Commits atómicos con formato `type: concise description in English` validados en pipelines automáticos de CI/CD.
