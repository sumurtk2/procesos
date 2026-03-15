# SPEC: Mapa de Exposición a la IA de Procesos Empresariales en España

## Overview
Interactive treemap visualization showing AI exposure of ~120 business processes in Spanish companies. Same visual style as the jobs treemap (template_index.html) but adapted for business processes.

## Data Structure (docs/data.json)
Array of objects:
```json
{
  "title": "Gestión documental",
  "slug": "gestion-documental",
  "category": "administracion",
  "category_label": "Administración",
  "cost_pct_pyme": 2.5,
  "cost_pct_grande": 1.8,
  "exposure": 9,
  "readiness": 8,
  "exposure_rationale": "...",
  "readiness_rationale": "..."
}
```

## Categories (Áreas funcionales) — ~12 areas

1. **administracion** — Administración General
2. **finanzas** — Finanzas y Contabilidad
3. **rrhh** — Recursos Humanos
4. **comercial** — Comercialización y Ventas
5. **marketing** — Marketing y Comunicación
6. **atencion-cliente** — Atención al Cliente
7. **logistica** — Logística y Cadena de Suministro
8. **produccion** — Producción y Operaciones
9. **it** — Tecnología e Informática
10. **legal** — Legal y Cumplimiento
11. **id** — Investigación y Desarrollo
12. **direccion** — Dirección y Estrategia

## Processes per Category (~120 total)

### Administración General
- Gestión documental y archivo
- Gestión de correo y correspondencia
- Gestión de instalaciones y mantenimiento
- Recepción y centralita
- Gestión de viajes y desplazamientos
- Compras y aprovisionamiento general
- Gestión de flotas
- Control de inventario de oficina

### Finanzas y Contabilidad
- Contabilidad general
- Facturación y cobros
- Gestión de pagos a proveedores
- Conciliación bancaria
- Elaboración de presupuestos
- Control de gestión / reporting financiero
- Gestión fiscal y tributaria
- Auditoría interna
- Tesorería
- Análisis financiero y previsiones

### Recursos Humanos
- Selección y reclutamiento
- Gestión de nóminas
- Formación y desarrollo
- Evaluación del desempeño
- Gestión de beneficios sociales
- Administración de personal (altas, bajas, contratos)
- Prevención de riesgos laborales
- Clima laboral y cultura organizacional
- Gestión del talento y planes de carrera
- Control de presencia y horarios

### Comercialización y Ventas
- Prospección de clientes
- Gestión de ofertas y presupuestos
- Negociación y cierre de ventas
- Gestión de CRM
- Postventa y fidelización
- Gestión de canales de distribución
- Análisis de mercado y competencia
- Gestión de precios (pricing)
- Gestión de pedidos
- Venta online / e-commerce

### Marketing y Comunicación
- Estrategia de marketing digital
- Gestión de redes sociales
- Creación de contenidos
- SEO/SEM y publicidad online
- Email marketing y automatización
- Diseño gráfico y branding
- Eventos y ferias
- Relaciones públicas y prensa
- Análisis de datos de marketing
- Marketing de producto

### Atención al Cliente
- Atención telefónica (call center)
- Atención por email
- Chat en vivo y chatbots
- Gestión de reclamaciones
- Soporte técnico nivel 1
- Soporte técnico nivel 2
- Gestión de devoluciones
- Encuestas de satisfacción
- Base de conocimientos y FAQ
- Atención en redes sociales

### Logística y Cadena de Suministro
- Gestión de almacén
- Preparación de pedidos (picking)
- Transporte y distribución
- Gestión de proveedores
- Planificación de la demanda
- Control de inventario
- Logística inversa (devoluciones)
- Gestión de aduanas e importación
- Trazabilidad y seguimiento
- Optimización de rutas

### Producción y Operaciones
- Planificación de la producción
- Control de calidad
- Mantenimiento industrial
- Gestión de la cadena de montaje
- Seguridad industrial
- Gestión energética
- Mejora continua (lean/kaizen)
- Control de materias primas
- Gestión de residuos
- Automatización de procesos industriales

### Tecnología e Informática
- Soporte IT / helpdesk
- Administración de sistemas y servidores
- Desarrollo de software
- Ciberseguridad
- Gestión de bases de datos
- Gestión de proyectos IT
- Infraestructura de red
- Business intelligence y analytics
- Integraciones y APIs
- Gestión de licencias y SaaS

### Legal y Cumplimiento
- Contratos y revisión legal
- Protección de datos (RGPD/LOPDGDD)
- Cumplimiento normativo (compliance)
- Propiedad intelectual
- Litigios y reclamaciones legales
- Asesoría laboral
- Gestión de seguros
- Due diligence
- Normativa sectorial

### Investigación y Desarrollo
- Investigación de mercado
- Desarrollo de producto
- Prototipado y testeo
- Gestión de la innovación
- Análisis de patentes
- Vigilancia tecnológica
- Ensayos y certificaciones

### Dirección y Estrategia
- Planificación estratégica
- Toma de decisiones ejecutiva
- Gobierno corporativo
- Gestión de riesgos
- Relaciones institucionales
- Responsabilidad social corporativa (RSC)
- Gestión del cambio organizacional
- M&A y desarrollo de negocio

## Scoring Guidelines

### AI Exposure (0-10)
Score how much AI can transform/automate this process TODAY and near-term (2-3 years):
- 0-2: Minimal — physical, highly relational, regulatory barriers
- 3-4: Low — mostly physical or requiring deep human judgment
- 5-6: Moderate — mix of automatable and human-required tasks
- 7-8: High — predominantly digital, data-driven, pattern-based
- 9-10: Very high — almost fully automatable with current AI

### Readiness (0-10)
How easy/practical is it to implement AI in this process in a typical Spanish company:
- 0-2: Very hard — regulatory blockers, legacy systems, cultural resistance, high risk
- 3-4: Hard — significant barriers but possible with investment
- 5-6: Moderate — standard SaaS tools exist, some integration needed
- 7-8: Easy — plug-and-play solutions available, quick ROI
- 9-10: Trivial — tools already widely adopted, minimal friction

### Cost allocation (cost_pct_pyme / cost_pct_grande)
Estimated % of total operating costs for a typical PYME (10-50 employees) vs Gran Empresa (500+ employees).
All values across all processes should sum to ~100% for each company type.

## UI Differences from Jobs Template

The site should look visually identical to template_index.html but with these changes:

### Sidebar
- Title: "Exposición a la IA de los Procesos Empresariales"
- Subtitle: "~120 procesos · área = coste operativo · color = exposición a la IA"
- Toggle button: PYME / Gran Empresa (switches which cost data sizes the rectangles)
- Stats:
  - "Total procesos" (count)
  - "Exposición media ponderada" (weighted by cost)
  - Histogram of cost by exposure score
  - Breakdown by tier (same 5 tiers)
  - "Exposición por área" (horizontal bars showing avg exposure per category)
  - "Facilidad de implementación media" (readiness weighted avg)
  - Gradient legend

### Treemap
- Rectangle size = cost_pct (pyme or grande depending on toggle)
- Rectangle color = exposure score (same color scale)
- Labels show process name + exposure score

### Tooltip
- Process name
- AI Exposure bar (same as jobs)
- Stats: Área funcional, Coste operativo (X%), Exposición IA, Facilidad de implementación
- Rationale for exposure
- Rationale for readiness

### Toggle (PYME / Gran Empresa)
- Two buttons at top of sidebar, styled as a pill toggle
- Default: PYME
- Switching recalculates all stats and relayouts the treemap

## Files to Create

1. `docs/data.json` — all process data with scores and rationales
2. `docs/index.html` — the full site (based on template_index.html, heavily modified)
3. `README.md` — Spanish description of the project

## Important
- All text in Spanish
- All rationales in Spanish — natural, professional Spanish
- The treemap categories use category_label for display
- Readiness is shown in tooltip but does NOT affect rectangle color (color = exposure only)
- Be thorough with the scoring — each process needs a thoughtful rationale, not generic text
- Cost percentages should be realistic. For PYME, production/operations might be 25-35% while IT might be 3-5%. For Gran Empresa, more spread across areas.
