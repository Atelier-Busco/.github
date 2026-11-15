# 🤝 Guía de Contribución Open Source

¡Gracias por considerar contribuir a los **repositorios públicos y plantillas de Atelier Busco**! Construimos software con precisión, claridad y rigor de nivel enterprise.

🌐 **[English Version](../CONTRIBUTING.md)**

---

## 📐 Expectativas de Ingeniería

1. **Línea Base de Runtime & TypeScript Estricto:**
   - Todos los repositorios requieren **Node.js 22+ LTS** como entorno de ejecución mínimo.
   - Los proyectos web siguen patrones de **Angular 22 Zoneless** (Signals, Application Builder, sin sobrecarga de `zone.js`).
   - Los proyectos Node.js siguen estándares modulares de **NestJS 11 / Fastify** con validación DTO obligatoria (`class-validator`) y decoradores de Swagger OpenAPI.
2. **Cero Valores Hardcodeados:** Secretos, URLs y parámetros de configuración deben inyectarse mediante variables `.env`.
3. **Límite de Mensajes de Commit:**
   - Formato estándar: `type: concise description in English` (ej. `fix: resolve token refresh race condition`).
   - No mezclar refactorizaciones con corrección de errores en un mismo commit.

---

## 🔄 Flujo de Pull Requests

1. Haz un fork del repositorio y crea tu rama de feature a partir de `main`.
2. Asegura que los tests unitarios pasen (`npm run test`) y que el chequeo de tipos sea impecable antes de enviar.
3. Abre un Pull Request describiendo con claridad el problema resuelto y el impacto técnico.
