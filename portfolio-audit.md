# Auditoría de contenido — Portfolio (index.html)

**Alcance:** única vista del sitio (`index.html`), texto visible por defecto (inglés), textos sustituidos por i18n (inglés `en` / español `es`), meta `<title>` y `<meta name="description">`, UI fija (nav, footer, modal, sugerencia de idioma).  
**No se modificó código** en esta auditoría.

---

## 1. TEXTO ORIGINAL

### 1.1 `<head>` y metadatos

| Elemento | Contenido actual |
|----------|------------------|
| `lang` (html) | `en` |
| `<title>` | Thiago Fernández — Backend Developer |
| `meta description` | Backend Full Stack Developer specializing in API development, scalable services, and distributed systems. .NET, Node.js, Docker, Kubernetes. |

**Inconsistencias:**  
- “Full Stack” en meta vs “Backend Developer” en título y footer → **rol inconsistente**.  
- “**scalable services**” → buzzword sin evidencia en la meta.  
- No hay versión ES de meta/title (solo una página).

---

### 1.2 Navegación y UI global

**Inglés (DOM por defecto + parcialmente traducido):**

| Texto | Notas |
|-------|--------|
| thiago**.dev** | Marca |
| ./projects · ./integrations · ./experience · ./contact | Rutas estilo CLI; `nav.*` cambia a `./proyectos`, `./freelance`, etc. en ES |
| open_to_backend_roles() | Inglés fijo (no pasa por i18n) |
| lang · EN · ES | Inglés fijo |
| Menu (aria-label) | Inglés fijo |

**Español (`translations.es` para enlaces):** `./proyectos`, `./freelance`, `./experiencia`, `./contacto`

**Inconsistencias:**  
- CTA `open_to_backend_roles()` **siempre en inglés** aunque el sitio esté en ES.  
- `aria-label` del menú y del modal de galería **solo EN** (“Close gallery”, “Previous image”, “Next image”).  
- Mezcla de convención: labels de sección con `//` y números vs nav con `./`.

---

### 1.3 Hero

**Inglés (HTML por defecto + `en`):**

- Label: Backend / Distributed Systems  
- Rol: Building **APIs**, multi-tenant platforms / and backend services that survive production.  
- Tagline: .NET · Node.js · Docker · Kubernetes / Buenos Aires — backend for real-world systems  
- CTA: View proof of work · View freelance projects  

**Español (`es`):**

- Backend / Sistemas Distribuidos  
- Construyo **APIs**, plataformas multi-tenant / y servicios backend que sobreviven producción.  
- .NET · Node.js · Docker · Kubernetes / Buenos Aires — backend para sistemas reales  
- Ver evidencia de trabajo · Ver proyectos freelance  

**Inconsistencias / riesgos:**  
- “**multi-tenant platforms**” / “**plataformas multi-tenant**”: término técnico útil para perfiles técnicos; para RRHH puede sonar jerga sin una línea de contexto (“varios clientes aislados en un mismo producto”).  
- “**survive production**” / “**sobreviven producción**”: metáfora informal; funciona como tono personal pero no es el registro más “corporativo”.  
- “**real-world systems**” / “**sistemas reales**”: ligeramente genérico (casi todo es “real”).  
- Topónimo **Buenos Aires** aparece en ambas versiones (correcto).

---

### 1.4 Evidencia / Proof of work (`#proof-work`)

**Labels de sección**

| EN | ES |
|----|-----|
| // intro — proof of work | // intro — evidencia visual |

**Título**

| EN | ES |
|----|-----|
| What I built in real systems · in production. | Lo que construí en sistemas reales · en producción. |

**Inconsistencia de convención:** el label pasa de “proof of work” (EN) a “evidencia **visual**” (ES): no es la misma idea (uno es alcance de trabajo, el otro enfatiza capturas).

**Tarjetas (contenido paralelo EN/ES vía `proof.copy.*`):** AGIP, Flexwork, Faristol, Gestión Seguros, OurClub — cada una con párrafo lead + 3 bullets.

**Observaciones de idioma dentro del contenido:**  
- ES mezcla anglicismos técnicos inevitables (OpenAPI, deep linking, SSO, JWT, OAuth, stack, EAS, middleware) con texto en español → **aceptable** para audiencia técnica; para RRHH puro conviene 1 frase sin siglas al inicio.  
- “**Back-office**” en ES (Gestión Seguros) → préstamo del inglés; alternativa: “sistema de gestión interna”.  
- “**full stack**” en bullets (Flexwork ES) → anglicismo; alternativa: “desarrollo en frontend y backend”.

---

### 1.5 Freelance (`#integrations`)

**Labels de sección**

| EN | ES |
|----|-----|
| // 02 — freelance projects | // 02 — proyectos freelance |
| Freelance projects delivered for clients. | Proyectos freelance entregados a clientes. |

**Numeración vs orden visual:** en la página, **antes** de “personal” aparece freelance (02) y **después** personal (01) por el orden del DOM / script — posible **confusión** para el lector (no es solo texto, es convención de sección).

**Tarjeta 01 — título en HTML**

- OurClub — Members & bookings **platform** (EN fijo en HTML; el resto del bloque se traduce)

**Subsecciones (etiquetas):** Context · What I did · Impact · Stack | Contexto · Qué hice · Impacto · Stack  

**Contenido (resumen de issues):**  
- EN: “**B2B SaaS** for sports clubs…” → buzzword **SaaS** explícito.  
- ES: “**SaaS B2B**…” → mismo issue.  
- Título HTML mezcla con cuerpo: “platform” en título mientras el copy evitó “SaaS” en otras áreas recientemente.  
- Título móvil ES: “**App hinchas**” (coloquial/regional) vs EN “Fan app” → **tono desalineado** entre idiomas.  
- “**Material-style UI**” / “UI estilo Material” → claro para técnicos.  
- “**Fan**” / “**Accesos**” como etiquetas de producto: coherente internamente.

---

### 1.6 Proyectos personales (`#personal-projects`)

**Traducido solo:** label `// 01 — …` y título de sección “Personal projects · product views.” / “Proyectos personales · vistas del producto.”

**Siempre en inglés (sin entradas en `translations`):**

| Elemento | Texto |
|----------|--------|
| Labels por card | Summary · Live |
| RealSpend | Finance-focused product with analytics views and API-driven workflows. |
| VibeCoding | AI coding workspace with dashboard, modules and prompt tooling. |
| Contabilio | Accounting product with tax calculators and fiscal health simulators. |
| Contabilio Live | Coming soon |

**Inconsistencia crítica:** con el sitio en **español**, esta sección queda **mayormente en inglés** → rotura fuerte de consistencia.

**Buzzwords / vaguedad:**  
- “**API-driven workflows**”, “**prompt tooling**”, “**fiscal health simulators**”: suenan a marketing; poco impacto medible o responsabilidad explícita.  
- “**AI coding workspace**”: muy genérico en el mercado actual.

---

### 1.7 Experiencia (`#experience-timeline`)

**Labels**

| EN | ES |
|----|-----|
| // 03 — experience (condensed) | // 03 — experiencia (resumida) |
| Where I’ve used this. | Dónde usé todo esto. |

**Nombres de empresa** (propios, no traducibles): América Virtual, Faristol, Flexwork Latam.

**Bloques (paralelo EN/ES):**

- **América Virtual:** Backend Developer · period · descripción + 3 logros (OpenAPI contract-first, auth/caché/Gzip, Docker/K8s/OpenShift).  
- **Faristol:** Mobile Developer · …  
- **Flexwork Latam:** Full Stack Developer · … (incluye “improve UX” en EN / “mejorar la UX” en ES)

**Inconsistencias:**  
- “**contract-first**” en ES sin traducir (técnicos lo entienden).  
- “**Containerised**” (EN) vs “containerizados” (ES) — coherente.  
- Logros mezclan **qué** hizo con **cómo** (stack); poco “para qué” / impacto de negocio en una línea.

---

### 1.8 Contacto

| EN | ES |
|----|-----|
| // 04 — contact | // 04 — contacto |
| Let's talk | Hablemos |
| Currently open to new backend or full stack opportunities. If you're working on something interesting, reach out. | Abierto a nuevas oportunidades como backend o full stack. Si estás construyendo algo interesante, podemos hablar. |
| email · linkedin · github | idem (etiquetas en inglés siempre) |

**Fijos en cualquier idioma:**  
- Texto del botón EN/ES en sugerencia: “Sí, en español” / “No, keep English” → **mezcla intencional** en el mismo widget.  
- Links: `linkedin.com/in/` y `github.com/` son **placeholders** (no perfil real) → problema de **profesionalismo**, no solo de idioma.

---

### 1.9 Footer

- Thiago Fernández — Backend Developer · Buenos Aires  
- Año (inyectado por script; no auditado como copy)

**Sin versión ES** del footer.

---

### 1.10 Modal galería personal (texto visible)

- `×` cierre  
- aria-labels: Close gallery, Previous image, Next image (EN fijo)  
- Contador: generado por JS (no citado aquí)

---

## 2. PROBLEMAS DETECTADOS

### 2.1 Mezcla de idiomas

1. **Proyectos personales:** títulos de sección traducidos, cuerpo de cards **solo EN**.  
2. **Nav CTA** `open_to_backend_roles()` y **labels** email/linkedin/github **solo EN**.  
3. **Footer** solo EN.  
4. **Meta description** solo EN.  
5. **aria-labels** y parte del **lang suggestion** mezclan EN/ES.  
6. **Freelance card 1 title** “OurClub — Members & bookings platform” **no traducido** (resto del bloque sí en ES).

### 2.2 Falta de convención

1. Labels de intro: “proof of work” vs “evidencia **visual**” (ES).  
2. Secciones `// 01` personal vs `// 02` freelance **no siguen el orden vertical** de la página.  
3. Freelance usa **Context / Qué hice / Impacto / Stack**; proof usa **lead + bullets**; personal usa **Summary + Live** → **tres formatos distintos**.  
4. “Stack” en ES a veces anglicismo puro (freelance) vs “stack web .NET” en proof Gestión Seguros.

### 2.3 Buzzwords o términos flojos

1. Meta: “**scalable services**”.  
2. Hero: “multi-tenant platforms”, “survive production”, “real-world systems” (último muy genérico).  
3. Freelance: “**B2B SaaS**”.  
4. Personal: “API-driven workflows”, “AI coding workspace”, “prompt tooling”, “fiscal health simulators”.  
5. Experiencia Flexwork: “improve UX” sin resultado concreto.

### 2.4 Descripciones poco claras o poco orientadas a valor

1. Proyectos personales: una línea por proyecto **sin** rol explícito (“qué construiste vos vs qué es el producto”).  
2. Experiencia: bullets fuertes en **actividades**; falta a menudo **resultado** (latencia, incidentes, volumen, adopción) donde sea creíble.  
3. Título “Where I’ve used this” / “Dónde usé todo esto”: “esto” es **ambiguo** para quien llega sin leer todo el scroll.

### 2.5 RRHH vs técnico

| Audiencia | Problema |
|-----------|----------|
| **RRHH** | Muchas siglas seguidas sin puente en Hero y en bullets; orden de secciones 02 antes que 01; linkedin/github genéricos. |
| **Técnico** | Buen detalle en freelance y proof; experiencia podría añadir 1 dato duro (p. ej. escala, SLAs, patrones) sin inflar; meta “scalable” no aporta señal. |

### 2.6 Otros (profesionalismo)

1. Enlaces **LinkedIn y GitHub** sin usuario concreto.  
2. “Backend” vs “Full Stack” usados en distintos sitios sin una frase que aclare el foco actual.

---

## 3. REESCRITURA PROPUESTA

*Las siguientes versiones son propuestas editoriales: tono serio, escaneable, idioma homogéneo por bloque, menos buzzwords, más responsabilidad e impacto donde encaja.*

### 3.1 Meta + título (alineados al rol principal)

**Español (propuesta)**  
- **Title:** Thiago Fernández — Desarrollador backend  
- **Description:** Desarrollo de APIs y servicios backend en .NET y Node.js, con despliegue en contenedores (Docker, Kubernetes). Enfoque en sistemas en producción e integraciones.

**English (proposal)**  
- **Title:** Thiago Fernández — Backend developer  
- **Description:** Backend APIs and services in .NET and Node.js, shipped with containers (Docker, Kubernetes). Focus on production systems and integrations.

---

### 3.2 Navegación y CTA (traducibles)

**ES:**  
- CTA correo: `abierto_a_roles_backend()` o texto plano: **Disponible · Backend**  
- aria menú: **Menú**  
- Sugerencia idioma: unificar botones (ej. **Seguir en inglés** / **Ver en español**)

**EN:**  
- CTA: `open_to_backend_roles()` o **Open to backend roles**  
- Keep aria-labels in English if the page `lang` is `en`; mirror in Spanish when `lang` is `es` (dynamic).

---

### 3.3 Hero

**Español (propuesta)**  
- Label: Backend / sistemas distribuidos  
- Rol: Diseño e implementación de **APIs** y servicios backend para **varios clientes sobre un mismo producto** (multi-tenant), desplegados y operados en producción.  
- Tagline: .NET · Node.js · Docker · Kubernetes · Buenos Aires  
- CTAs: Ver trabajo en productos reales · Ver proyectos freelance  

**English (proposal)**  
- Label: Backend / distributed systems  
- Role: I design and ship **backend APIs and services** for **multi-tenant products** running in production.  
- Tagline: .NET · Node.js · Docker · Kubernetes · Buenos Aires  
- CTAs: See work in live products · See freelance projects  

*(Se sustituye “survive production” y “real-world” por formulaciones más directas; “multi-tenant” se puede mantener con gloss corto entre paréntesis en ES.)*

---

### 3.4 Proof of work — label + título

**ES (propuesta)**  
- Label: `// intro — trabajo en productos reales`  
- Título: Lo que hice **en** sistemas que están **en uso**  

**EN (proposal)**  
- Label: `// intro — work in live products`  
- Title: What I shipped **in** systems **running today**  

*(Alinea EN/ES sin cambiar el sentido a “solo capturas”.)*

---

### 3.5 Proof — tarjetas (resumen propuesto; mantener bullets)

**AGIP · ES:** Lead: Portal tributario de la Ciudad para trámites, pagos y uso interno. Bullets: (1) APIs y módulos backend multi-tenant. (2) Menos fricción operativa al unificar flujos e integraciones. (3) ASP.NET Core, contratos OpenAPI, IBM/CTG con timeouts, logs y reintentos.  
**AGIP · EN:** (Keep current with minor tweak: “**Government** city tax portal …” if accuracy allows.)

**Flexwork · ES:** Sustituir “full stack” por: “**Desarrollo en interfaz (Next.js) y backend (Node/Express)**…” donde aparezca.  
**EN:** “End-to-end delivery: Next.js UI, Node/Express APIs, Firebase Auth.”

**Personal projects — sección completa (propuesta nueva)**

**ES — etiquetas:** Resumen · En vivo (o Demo)  
**EN — labels:** Summary · Live

**RealSpend · ES**  
- Resumen: Panel para analizar gasto y riesgo con datos cargados vía API.  
- Bullets: Diseño de vistas analíticas; documentación/contrato de API; despliegue en Render.  

**RealSpend · EN**  
- Summary: Analytics dashboard for spend and risk, fed by APIs.  
- Bullets: Built analytic views; API surface and docs; deployed on Render.

**VibeCoding · ES**  
- Resumen: Entorno de trabajo para organizar prompts, módulos y pruebas con modelos de código (uso personal / demo).  
- Bullets: Flujos en dashboard; biblioteca de prompts; sandbox. *(Evitar “AI workspace” suelto.)*  

**VibeCoding · EN**  
- Summary: Workspace to organize prompts, modules, and code-model experiments (personal / demo).  

**Contabilio · ES**  
- Resumen: Simuladores y calculadoras impositivas para autónomos y monotributo (Argentina).  
- En vivo: Próximamente *(o fecha si la hay)*  

**Contabilio · EN**  
- Summary: Tax calculators and simulators for Argentine freelancers and monotributo.  
- Live: Coming soon  

---

### 3.6 Freelance

**Título card web · ES (propuesta):** OurClub — **Web de socios, reservas y pagos** (quita “platform”).  
**EN:** OurClub — **Members web: bookings and payments**

**Contexto · ES:** Producto **por suscripción** para clubes deportivos: socios, cobros, avisos y venta de entradas. Ya había mucho .NET en producción; el encargo fue sumar autogestión y APIs **sin** reemplazar todo el sistema.  
**EN:** Subscription product for sports clubs (members, billing, notices, ticketing). Large .NET estate already live; add self-service and APIs **without** a big-bang rewrite.

**Título móvil · ES (tono alineado con EN):** OurClub — **App de socio y control de acceso** (en lugar de “hinchas” si se busca registro neutro/profesional).  
**EN:** OurClub — **Member app and access control**

*(Resto de bloques Context / What I did / Impact / Stack pueden mantenerse con ajustes menores de redacción; el bloque “SaaS” queda reemplazado arriba.)*

---

### 3.7 Experiencia

**Título de sección · ES:** Dónde **apliqué** esto *(o)* **Experiencia** (más estándar para RRHH).  
**EN:** Where I’ve **applied** this · or **Experience**

**América Virtual — bullet ES (ejemplo con resultado):**  
- Diseño e implementación de APIs REST con contrato OpenAPI en entorno multi-tenant.  
- Autenticación por tokens, caché en memoria y compresión para **reducir tiempo de respuesta y carga en servidores**.  
- Contenedores Docker y despliegue en Kubernetes/OpenShift con configuración por entorno.

**Flexwork — sustituir “mejorar la UX” por:**  
- ES: Rutas dinámicas y carga diferida para **páginas más ligeras y navegación más fluida**.  
- EN: Dynamic routes and lazy loading for **lighter pages and smoother navigation**.

---

### 3.8 Contacto + footer

**ES**  
- Hablemos  
- Busco roles **de backend** (y colaboración full stack cuando el proyecto lo requiere). Escribime con contexto del equipo y del producto.  
- Footer: Thiago Fernández — Desarrollador backend · Buenos Aires  

**EN**  
- Let’s talk  
- Open to **backend** roles (and full-stack collaboration when the project needs it). Write with a bit of context on team and product.  
- Footer: Thiago Fernández — Backend developer · Buenos Aires  

**Enlaces:** reemplazar placeholders por URLs reales de LinkedIn y GitHub.

---

## 4. CRITERIOS APLICADOS

| Criterio | Qué se propone cambiar | Por qué mejora | RRHH | Técnico |
|----------|-------------------------|----------------|------|---------|
| Un idioma por vista | Traducir personal, footer, CTA nav, aria cuando `lang=es`; alinear meta | Lectura coherente sin saltos | ✅ | ✅ |
| Menos buzzwords | Quitar “scalable” vacío; sustituir “SaaS” por “suscripción” donde baste; hero más literal | Menos ruido, más credibilidad | ✅ | ✅ |
| Convención de secciones | Mismo tipo de label intro EN/ES; reconsiderar orden 01/02 o renumerar | Menos fricción cognitiva | ✅ | ✅ |
| Formato | Acercar personal a lead + bullets o a Context/Impacto corto | Escaneo en 10 s | ✅ | ✅ |
| Valor / impacto | 1 frase de resultado en logros (latencia, carga, operación) donde sea honesto | No solo lista de tareas | ✅ | ✅ |
| Profesionalismo | URLs reales; rol único (backend primero, full stack aclarado) | Confianza | ✅ | ✅ |

---

## 5. Seniority — decisión explícita (complemento)

**Decisión recomendada:** posicionarte como **ingeniero backend mid–senior** (no “staff/principal” sin evidencia pública de alcance org-wide; no “junior”).

**Señales que sostienen ese nivel**

- Contratos **OpenAPI-first**, entornos **multi-tenant**, integración **IBM/CTG** con operación defensiva (timeouts, logs, reintentos).
- **Kubernetes / OpenShift**, configuración por entorno, contenedores.
- **OurClub:** middleware .NET 6, convivencia con legado, Dapper en rutas calientes, APIs versionadas, mobile acoplado al mismo backend.

**Qué debía quedar como contexto, no como identidad principal**

- Rol **mobile** en Faristol y **full stack** en Flexwork → amplitud que **informa** cómo diseñás APIs para clientes móviles y front; no debe competir en el hero con el mensaje backend.

**Qué arrastraba ruido de seniority**

- Copy tipo “AI workspace / prompt tooling” sin marco → lectura **junior / builder genérico**.
- “Mejorar UX” sin resultado técnico → lectura **medio**.
- Mezcla en la misma página de bullets muy senior y frases vagas → **no queda claro el piso** de experiencia.

*Esta decisión quedó reflejada en el sitio (hero + secciones) en la revisión posterior a esta auditoría.*

---

## 6. Narrativa global — problema estructural (complemento)

**Problema:** el portfolio leía como **tres cajas desconectadas** (proof técnico / freelance producto / personal vago) sin una línea que dijera: *soy X → esto demuestro en Y → esto profundizo en Z → el timeline cierra el circuito*.

**Por qué importa más que micro-traducciones:** RRHH escanea **una historia** en segundos; el técnico busca **coherencia** entre “lo que decís ser” y “dónde aparece en cada sección”.

**Solución aplicada en el sitio (post-auditoría)**

1. **Hero:** párrafo explícito **mid–senior backend** + mapa de lectura: Proof = amplitud · side builds = experimentos · freelance = profundidad · experience = empleadores.
2. **Deck** bajo cada gran sección (`section-deck`): 1–2 frases que enlazan la sección con esa historia (proof “backend-heavy”, freelance “depth on one product line”, personal “not client work”, experience “roles behind the work above”).
3. **Personal renombrado** a *Side builds / experiments* con disclaimer de que **no define seniority**.
4. **Faristol + Flexwork** reescritos para enfatizar **auth, APIs, integración** y resultados medibles (p. ej. first meaningful paint) en lugar de “pantallas” o “UX” suelta.

---

## 7. Resumen ejecutivo

El portfolio ya tiene **tramos fuertes** (proof con bullets; freelance con Context/Impact/Stack). Los mayores huecos eran: **i18n incompleta en proyectos personales y footer**, **CTA/nav fijos en inglés**, **meta y hero con palabras cargadas**, **tres formatos de proyecto distintos**, **enlaces sociales genéricos**, y sobre todo **falta de decisión explícita de seniority** y **narrativa global** entre secciones. La revisión de contenido en `index.html` aborda narrativa, alineación de seniority y copy de experimentos personales; pendientes razonables: footer/CTA/nav bilingües y URLs reales de LinkedIn/GitHub.

---

*Fin del documento `portfolio-audit.md`.*
