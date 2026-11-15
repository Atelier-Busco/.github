# 🛡️ Política de Seguridad & Divulgación Responsable

En Atelier Busco SpA, la seguridad es un requerimiento de arquitectura, no una idea secundaria. Mantenemos estándares de seguridad de nivel enterprise en nuestras plataformas propietarias, repositorios de código abierto e infraestructura de clientes.

🌐 **[English Version](../SECURITY.md)**

---

## 🏛️ Acreditaciones Normativas y de Ciberseguridad Cloud

### 🇨🇱 Proveedor Registrado de Ciberseguridad — ANCI (Chile)
Atelier Busco SpA se encuentra registrada formalmente como proveedor de tecnología y ciberseguridad ante la **Agencia Nacional de Ciberseguridad (ANCI)** de Chile, en cumplimiento con las exigencias de la **Ley Marco de Ciberseguridad (Ley N° 21.663)**. Esta acreditación oficial garantiza que nuestras arquitecturas, gobernanza de datos y protocolos operativos cumplen con los estándares nacionales para la protección de redes y sistemas informáticos en infraestructura crítica y servicios esenciales.

### 🌐 Cloud Security Alliance (CSA STAR Nivel 1)
Atelier Busco se encuentra listado en el **CSA STAR Registry (Nivel 1)** de la Cloud Security Alliance para sus servicios cloud centrales. Este reconocimiento valida nuestro compromiso con la transparencia, la gobernanza cloud y el cumplimiento de las mejores prácticas de la matriz de controles de seguridad en la nube (CCM).

---

## 🔑 Principios Core de Seguridad

- **Acceso de Menor Privilegio:** Instancias, contenedores y cuentas de base de datos limitados estrictamente a los permisos mínimos de ejecución necesarios.
- **Manejo de Secretos Zero-Knowledge:** API keys, credenciales de BD y certificados administrados mediante gestores de entorno encriptados (AWS Secrets Manager, Azure Key Vault o Vercel Vault) con rotación automática.
- **Autenticación Stateless & Rotativa:** JWTs de acceso de corta duración combinados con tokens de refresco rotativos guardados en cookies HTTP-Only o almacenamiento nativo encriptado (`flutter_secure_storage`).
- **Hardening Automatizado:** Encabezados globales de seguridad HTTP (`helmet`), rate-limiting a nivel de aplicación (`throttler`) y filtrado global de excepciones con tracing IDs contextuales (`requestId`).
- **Auditoría Continua & SAST/DAST:** Pruebas automáticas de seguridad estática y dinámica integradas directamente en nuestros pipelines de GitHub Actions.

---

## 🚨 Reporte de Vulnerabilidades

Si descubres una vulnerabilidad potencial en cualquier proyecto open-source o propiedad pública de Atelier Busco, por favor repórtala de inmediato a nuestro equipo de seguridad:

* **Correo:** security@atelierbusco.com / info@atelierbusco.com
* **SLA de Respuesta:** Confirmamos recepción de todas las consultas de seguridad en un plazo máximo de 24 horas hábiles.

Agradecemos no divulgar públicamente vulnerabilidades hasta que nuestro equipo haya tenido la oportunidad de evaluar y corregir el problema.
