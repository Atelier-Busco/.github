# 🤝 Guía de Contribución Open Source

¡Muchas gracias por considerar contribuir a los **repositorios y plantillas públicas de Atelier Busco**! Construimos software con precisión, claridad y rigor enterprise.

🌐 **[English Version](../CONTRIBUTING.md)**

---

## 📐 Nuestras Expectativas de Ingeniería

1. **TypeScript Estricto & Estándar Standalone:**
   - Proyectos web siguen patrones de **Angular 22 Zoneless** (Signals, Application Builder, sin `zone.js`).
   - Proyectos Node.js siguen estándares modulares de **NestJS 11** con validación DTO obligatoria (`class-validator`) y decoradores de Swagger.
2. **Cero Valores Hardcodeados:** Secretos, URLs y flags de entorno deben inyectarse mediante archivos `.env`.
3. **Límites en Mensajes de Commit:**
   - Formato estándar: `tipo: descripción breve en inglés` (ej: `fix: resolve token refresh race condition`).
   - Nunca mezclar refactorizaciones con correcciones de errores en el mismo commit.

---

## 🔄 Flujo de Pull Requests

1. Haz un Fork del repositorio y crea tu rama desde `main`.
2. Asegúrate de que los unit tests pasen (`npm run test`) y el tipado sea limpio antes de enviar.
3. Abre un Pull Request con una descripción clara del problema resuelto y su impacto técnico.
