<!--
  PERFIL DE GITHUB — Nicolás Estragues
  Cómo usarlo: crea un repo PÚBLICO llamado igual que tu usuario (TuQRApp/TuQRApp),
  marca "Add a README" y pega este contenido. Reemplaza todo lo que diga TuQRApp o [COMPLETAR].
-->

<h1 align="center">Hola, soy Nicolás 👋</h1>

<p align="center">
  <b>Fundador y desarrollador de productos digitales en Chile 🇨🇱</b><br/>
  Construyo herramientas que resuelven problemas concretos: pagos por QR, revisión normativa con IA, gestión de ensayos clínicos, investigación de mercado y automatización de trading.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/📍_Santiago,_Chile-0A66C2?style=for-the-badge" alt="Santiago, Chile"/>
  <img src="https://img.shields.io/badge/Construyendo-TuQR-FF7A18?style=for-the-badge" alt="Construyendo TuQR"/>
  <img src="https://img.shields.io/badge/Idiomas-Español_·_English-2ea44f?style=for-the-badge" alt="Idiomas"/>
</p>

---

## 🚀 Qué estoy construyendo

Trabajo de punta a punta: producto, frontend, backend serverless, despliegue y modelo de negocio. Mis proyectos combinan **arquitectura de sistemas**, **integración de APIs e IA** y **problemas reales del mercado chileno**.

| Proyecto | Qué es | Stack |
|---|---|---|
| 🟧 **[TuQR](https://tuqr.io)** | Plataforma para que comerciantes y emprendedores reciban transferencias bancarias con un QR, sin que el cliente tenga que digitar datos. Incluye panel de administración, flyers imprimibles y modelo de negocio por QR activo. | HTML · CSS · JS · Cloudflare Workers · GitHub Pages |
| 🏛️ **ArchiCheck** ([hoja de ruta pública](https://github.com/TuQRApp/archicheck-roadmap)) | SaaS chileno de revisión automatizada de expedientes de arquitectura. Contrasta proyectos contra el Plan Regulador Comunal (PRC) y la normativa nacional (OGUC, LGUC, Ley 19.300) usando IA, con un motor de verificación de reglas probado (27/27 tests). | React · Cloudflare Workers · Claude API · PostgreSQL · Vercel |
| 🧪 **Ensayos Clínicos** | Herramienta de preparación de sitio para centros de investigación clínica en Chile: documentos esenciales por estudio con versiones y vencimientos, personal, tareas y una vista de lo que falta antes de un monitoreo. Diseñada con reglas deterministas, sin datos de participantes. En etapa de validación con centros. | React · Vite · Supabase · Vercel |
| 📋 **Survey Panel** | Plataforma de gestión de paneles de encuestados para investigación de mercado: encuestas propias enviadas por correo, auto-inscripción con formularios configurables por encuesta, asignación masiva, incentivos a encuestados y pagos a reclutadores, con importación de datos desde Excel. | React · Vite · Supabase · Serverless API (Vercel) |
| 📈 **[trading-bot-ops](https://github.com/TuQRApp/trading-bot-ops)** | Sistema de operación de bots de trading algorítmico: especificación de estrategias, hoja de ruta por fases, tracker de proyecto, backtests y panel de feedback para trabajo en conjunto con un trader. Estrategias basadas en OBV + divergencia MACD + ADX sobre 21 instrumentos en MT5. | Python · MetaTrader 5 · HTML/JS · GitHub Pages |

---

## 🏗️ Arquitectura y uso de APIs

Mi fuerte es **diseñar cómo se conectan las piezas**: qué habla con qué, dónde vive la fuente de verdad y cómo se integra la IA sin volverla un punto frágil.

- **Proxy serverless para las APIs de IA.** En ArchiCheck el frontend nunca llama directo al proveedor de IA: un **Cloudflare Worker** hace de intermediario, protege las credenciales, controla CORS y registra consultas en la base de datos.
- **IA con contexto y con control.** Integro la **Claude API** inyectando la normativa oficial (OGUC, LGUC, Ley 19.300, Planes Reguladores) en cada análisis, y valido los resultados con un **motor de reglas determinista** (27/27 tests) para no depender solo del modelo.
- **Varios modelos, un mismo flujo de trabajo.** Uso **Claude Code, Codex y DeepSeek** de forma complementaria: genero prompts con contexto del repo y pido revisiones cruzadas de código entre modelos, con scripts propios para automatizarlo.
- **Fuente de verdad en la nube, clientes locales desacoplados.** Un **Worker + D1** concentra los datos y los agentes locales en Node.js consultan la cola por *polling* saliente, sin abrir puertos ni exponer el computador.
- **APIs REST como capa de datos liviana.** En TuQR uso la **API REST de GitHub** como almacenamiento versionado (`data.json`) con panel de administración propio, y **Cloudflare Workers** para la lógica que necesita backend.
- **Bases de datos con aislamiento y respaldo.** **Supabase** (Auth, Postgres con *Row Level Security*, Storage) para productos multi-cliente; **Cloudflare D1** para backends edge; **PostgreSQL** con esquemas, vistas y funciones SQL de verificación para ArchiCheck.
- **Integración con sistemas externos.** **Python** para bots de trading conectados a **MetaTrader 5**, e importación y normalización de datos desde Excel y fuentes oficiales (BCN) hacia JSON/SQL estructurado.
- **Despliegue y costo mínimo.** **GitHub Pages, Vercel y Cloudflare** con CI en **GitHub Actions**; infraestructura casi gratuita hasta validar tracción.

---

## 🧰 Stack y herramientas

**Frontend**
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)

**Backend y APIs**
![Cloudflare Workers](https://img.shields.io/badge/Cloudflare_Workers-F38020?style=flat-square&logo=cloudflare&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![REST API](https://img.shields.io/badge/REST_APIs-009688?style=flat-square&logo=fastapi&logoColor=white)
![Serverless](https://img.shields.io/badge/Serverless_Functions-000000?style=flat-square&logo=vercel&logoColor=white)

**Bases de datos**
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white)
![Cloudflare D1](https://img.shields.io/badge/Cloudflare_D1-F38020?style=flat-square&logo=cloudflare&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-336791?style=flat-square&logo=databricks&logoColor=white)
![JSON](https://img.shields.io/badge/JSON-000000?style=flat-square&logo=json&logoColor=white)

**IA y modelos de lenguaje**
![Claude API](https://img.shields.io/badge/Claude_API-D97757?style=flat-square&logo=anthropic&logoColor=white)
![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat-square&logo=anthropic&logoColor=white)
![Codex](https://img.shields.io/badge/OpenAI_Codex-412991?style=flat-square&logo=openai&logoColor=white)
![DeepSeek](https://img.shields.io/badge/DeepSeek-4D6BFE?style=flat-square&logo=deepseek&logoColor=white)
![Prompt Engineering](https://img.shields.io/badge/Prompt_Engineering-555555?style=flat-square)

**Despliegue, datos y flujo de trabajo**
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![GitHub Pages](https://img.shields.io/badge/GitHub_Pages-222222?style=flat-square&logo=githubpages&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)
![Wrangler](https://img.shields.io/badge/Wrangler-F38020?style=flat-square&logo=cloudflare&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)
![MetaTrader 5](https://img.shields.io/badge/MetaTrader_5-1E90FF?style=flat-square)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat-square&logo=microsoftexcel&logoColor=white)

---

## 🔍 Áreas en las que trabajo

- **Productos para el mercado chileno:** pagos por transferencia, normativa urbana, investigación clínica, investigación de mercado y trading.
- **Arquitectura de sistemas:** diseño de capas, proxies seguros, colas, polling y fuentes de verdad únicas.
- **Integración de APIs y datos:** IA, bases de datos, servicios de terceros y hardware, conectados con bajo costo y alta trazabilidad.
- **IA aplicada:** prompts estructurados, normativa inyectada como contexto, validación determinista y revisión cruzada entre modelos.
- **Software para procesos regulados:** trazabilidad, versiones de documentos, vencimientos y respaldo de información.
- **Desarrollo asistido por IA:** uso Claude Code con archivos `CLAUDE.md` y `ROADMAP.md` para mantener contexto entre sesiones y trabajar de forma ordenada en repos reales.
- **Modelo de negocio:** de la idea a la monetización (suscripciones por QR activo, convenios con municipios y asociaciones de comerciantes).

---

## 📌 Principios con los que trabajo

- Primero resolver el problema real, después pulir la tecnología.
- Validar con usuarios antes de construir: si el mercado no responde, no se construye.
- Costos de infraestructura cercanos a cero hasta que el producto demuestre tracción.
- Reglas verificables y tests antes que confiar ciegamente en la IA.
- Documentar para que el proyecto sobreviva al cambio de computador (o a mí mismo).

---

## 📊 GitHub en números

<p align="center">
  <img height="170" src="https://github-readme-stats.vercel.app/api?username=TuQRApp&show_icons=true&theme=transparent&hide_border=true" alt="Estadísticas de GitHub"/>
  <img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=TuQRApp&layout=compact&theme=transparent&hide_border=true" alt="Lenguajes más usados"/>
</p>

---

## 🤝 Conversemos

Me interesa conversar sobre colaboraciones, pilotos con comercios, centros de investigación o instituciones, y proyectos que mezclen IA con procesos regulados.

<p>
  <a href="https://linkedin.com/in/[COMPLETAR]"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="https://tuqr.io"><img src="https://img.shields.io/badge/tuqr.io-FF7A18?style=for-the-badge&logo=googlechrome&logoColor=white" alt="TuQR"/></a>
  <a href="mailto:[COMPLETAR]"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>
</p>
