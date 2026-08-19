# Technical Requirements Document (TRD)

---

### 1. Arquitectura General
Aplicación web estática sin servidor backend (Serverless/Static Site). Todos los datos de los proyectos estarán integrados en el código fuente del frontend.

### 2. Stack Tecnológico - Frontend
- [cite_start]**Framework/Librería:** Vue.js (aprovechando tu experiencia previa [cite: 7]) o simplemente HTML5 + CSS (Tailwind CSS) para máxima ligereza.
- **Alojamiento (Hosting):** GitHub Pages o Vercel (capa gratuita).

### 3. Estrategia CI/CD
- [cite_start]**Automatización:** Uso de GitHub Actions para análisis de código estático (Linting) [cite: 19] y despliegue automático del frontend a la plataforma de hosting elegida tras cada actualización en la rama principal.