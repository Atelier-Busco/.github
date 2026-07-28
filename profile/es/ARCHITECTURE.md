# 🏛️ Atelier Busco — Estándares Públicos de Arquitectura e Ingeniería

En Atelier Busco construimos software con una **filosofía Senior sin relleno**. Nuestras decisiones técnicas están regidas por la mantenibilidad a largo plazo, velocidad de desarrollo, alto rendimiento y bajos costos operativos (enfoque en LTV).

🌐 **[English Version](../ARCHITECTURE.md)**

---

## ⚡ Estándar Frontend Web: Angular 22 (CSR + Zoneless)

Para productos web dinámicos que requieren máxima capacidad de respuesta y un manejo de estado estricto, nuestra opción por defecto es **Angular 22** en modalidad de Renderizado del Lado del Cliente (CSR).

* **Nativamente Zoneless:** Eliminamos la sobrecarga de `zone.js` (`provideExperimentalZonelessChangeDetection()`), logrando actualizaciones quirúrgicas de UI mediante Signals y un tamaño de bundle significativamente menor.
* **Motor Esbuild & Vite:** Ciclos de compilación en milisegundos mediante el Application Builder de Angular.
* **Arquitectura Basada en Componentes:** Componentes 100% Standalone por defecto, eliminando boilerplate innecesario de `NgModule`.
* **Manejo de Estado y Formularios Reactivos con Signals:** Flujo de control nativo (`@if`, `@for`, `@empty`) combinado con `input()` y `output()` Signals.

---

## 🚀 Estándar Backend: NestJS 11 Serverless

Nuestras arquitecturas de backend están construidas para alta disponibilidad y cero costos fijos en infraestructura cloud (AWS Lambda).

* **Seguridad por Defecto:** Protección global con `helmet`, políticas estrictas de CORS y rate-limiting global (`@nestjs/throttler`).
* **APIs Auto-Documentadas:** 100% de cobertura en Swagger (`@nestjs/swagger`) verificado en cada commit.
* **Desacoplamiento de Notificaciones:** Cero integración directa de SDKs de mensajería en la lógica de negocio; todo envío se despacha a través de nuestro `NotificationService` independiente.
* **Observabilidad Estructurada:** Logging JSON nativo etiquetado con trazabilidad única por `requestId` por cada contexto de ejecución.

---

## 🛡️ Prácticas Principales de Ingeniería

1. **Cero Secretos en Código:** Aislamiento obligatorio de variables de entorno para cualquier ambiente desplegado.
2. **Desarrollo Anclado a Especificaciones:** Cada sistema se diseña con límites claros (`SPEC.md` / `CONTEXT.md`) antes de escribir código de producción.
3. **Manejo de Operaciones Asíncronas:** Bloques try-catch explícitos y gestores de transacciones (`QueryRunner`) para escrituras multi-tabla.
