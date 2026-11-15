# 📐 Casos de Estudio de Arquitectura y Desglose de ROI

Este documento destaca desafíos técnicos reales resueltos por **Atelier Busco SpA**, mostrando nuestros patrones de arquitectura, decisiones de ingeniería e impacto directo en el negocio.

🌐 **[English Version](../CASE_STUDIES.md)**

---

## 🌾 Caso de Estudio 1: AgTech Enterprise & Integración SAP S/4HANA (AgroControl Suite)

### 🎯 Problema de Negocio
Grandes exportadoras agrícolas sufrían cuellos de botella administrativos, digitación manual en papel y desconexión con cientos de productores externos. Los proveedores no contaban con visibilidad en tiempo real de recepciones de fruta, órdenes de compra ni estados de liquidación, generando altos costos de gestión y reclamos financieros.

### 🏗️ Arquitectura Técnica
- **Integración ERP:** Sincronización API bidireccional y segura con **SAP S/4HANA**, respaldada por nuestra alianza **SAP PartnerEdge Open Ecosystem (Build)**.
- **Backend:** API modular en Node.js 22+ y NestJS con caché en Redis, transacciones atómicas para pagos Webpay y despachadores automáticos de webhooks.
- **Operaciones Móviles en Terreno:** Aplicación móvil nativa en Flutter con sincronización offline-first y procesamiento **Audio-to-Text con NLP** para visitas de agrónomos a huertos, transformando el dictado de voz en reportes técnicos estructurados.
- **Roadmap DeepTech de Visión Computacional:** Modelos multimodales de segmentación (Meta SAM 3.1) y OCR desplegados en clusters GPU para evaluación automatizada de fruta directamente en camiones en patios de recepción.

### 📈 Impacto en el Negocio
- **Escala:** Operando en producción para más de **2.000 productores agrícolas registrados**.
- **Eficiencia Operativa:** Eliminación del 100% de llamadas y consultas rutinarias de pago a administración.
- **Velocidad de Reportabilidad:** Reducción del **70% en el tiempo de emisión de informes agronómicos** gracias a la captura por voz, eliminando el reporte manual incompleto.

---

## 🏦 Caso de Estudio 2: Plataforma SaaS de Factoring & FinTech B2B (Factor Adelanta)

### 🎯 Problema de Negocio
Las PyMEs requerían cálculo de anticipos, evaluación de riesgo y cobranza de facturas en tiempo real sin la carga operativa de planillas manuales. La plataforma exigía cero tiempo de inactividad transaccional, aislamiento estricto de datos multitenant y flujos financieros auditables.

### 🏗️ Arquitectura Técnica
- **Frontend:** Angular 22 Zoneless CSR + Signal Forms para cálculo dinámico de facturas y tablas de riesgo reactivas.
- **Backend:** API modular NestJS sobre Node.js 22+ con transacciones estrictas de TypeORM (`QueryRunner`) para asegurar actualizaciones atómicas entre libros contables.
- **Seguridad:** JWTs de corta duración, tokens de refresco rotativos en cookies HTTP-Only y filtrado global de excepciones con trazabilidad por `requestId`.

### 📈 Impacto en el Negocio
- **Velocidad de Despliegue:** MVP v1.0 completamente operativo en **85 días**.
- **Rendimiento:** Reducción del **65% en latencia de cómputo** del panel financiero gracias a Angular Signals Zoneless.
- **Confiabilidad:** 100% de consistencia de datos en los ciclos de aprobación y desembolso.

---

## 🤖 Caso de Estudio 3: Orquestación de IA Empresarial (Prompt Engine & Memory Service)

### 🎯 Problema de Negocio
Integrar LLMs directamente en los flujos del cliente generaba riesgos de cumplimiento normativo, costos descontrolados por uso de tokens y falta de persistencia de contexto entre canales de soporte y consultas operativas.

### 🏗️ Arquitectura Técnica
- **Capa de Orquestación:** `Prompt Engine API` propia que actúa como gateway seguro para versionado de prompts, límites de presupuesto de tokens y validación SAST.
- **Capa de Contexto:** `Memory Service` independiente que combina embeddings vectoriales con metadata relacional para habilitar memoria operativa a largo plazo.
- **Infraestructura Backend:** Node.js 22+ / FastAPI serverless ejecutado en AWS Lambda con procesamiento asíncrono de colas.

### 📈 Impacto en el Negocio
- **Reducción de Costos:** Reducción del **40% en costos de API de IA** mediante optimización de prompts y caché inteligente.
- **Gobernanza:** Trazabilidad y auditoría completa de todas las respuestas generadas por IA.

---

## 🏛️ Caso de Estudio 4: GovTech & Analítica Cívica de Alta Disponibilidad (Seguimiento Legislativo)

### 🎯 Problema de Negocio
Iniciativas del sector público y monitoreo cívico requerían procesar altos volúmenes de medios, datos legislativos y registros públicos con disponibilidad estricta y sin sobrecostos de infraestructura.

### 🏗️ Arquitectura Técnica
- **Pipelines de Datos:** Crawlers ETL automatizados construidos en Python/FastAPI desplegados sobre tareas serverless de AWS.
- **API y Visualización:** Backend NestJS en Node.js 22+ alimentando un dashboard ligero en Angular con caché en servidor y entrega en el borde (edge) vía AWS CloudFront.

### 📈 Impacto en el Negocio
- **Disponibilidad:** 99.95% de uptime durante eventos de alta demanda legislativa.
- **Costo Operativo:** Costo de hosting cercano a cero en periodos de inactividad gracias a la arquitectura serverless orientada a pago por uso.
