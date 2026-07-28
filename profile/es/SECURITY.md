# 🛡️ Política de Seguridad & Divulgación Responsable

En Atelier Busco, la seguridad es un requerimiento de arquitectura, no una idea secundaria.

🌐 **[English Version](../SECURITY.md)**

---

## 🔑 Principios Core de Seguridad

- **Acceso de Menor Privilegio:** Cuentas de infraestructura y base de datos limitadas estrictamente a los permisos de ejecución necesarios.
- **Manejo de Secretos Zero-Knowledge:** API keys, credenciales de BD y secretos son administrados mediante gestores de entorno encriptados (AWS Secrets Manager / Vercel Vault).
- **Autenticación Estáteles & Rotativa:** JWTs de acceso de corta duración combinados con tokens de refresco rotativos guardados en cookies HTTP-Only o almacenamiento nativo encriptado (`flutter_secure_storage`).
- **Hardening Automatizado:** Encabezados globales de seguridad HTTP (`helmet`), rate-limiting a nivel de aplicación (`throttler`) y filtrado global de excepciones con tracing IDs.

---

## 🚨 Reporte de Vulnerabilidades

Si descubres una vulnerabilidad potencial en cualquier proyecto open-source o propiedad pública de Atelier Busco, por favor repórtala de inmediato a nuestro equipo de seguridad.

* **Correo:** security@atelierbusco.com / info@atelierbusco.com
* **SLA de Respuesta:** Confirmamos recepción de todas las consultas de seguridad en un plazo máximo de 24 horas hábiles.

Agradecemos no divulgar públicamente vulnerabilidades hasta que nuestro equipo haya tenido la oportunidad de evaluar y corregir el problema.
