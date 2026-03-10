# /client-proposal — MedZone PR Client Proposal Generator

Generate a tailored, physician-ready engagement proposal combining financial analysis and professional business writing.

## What This Skill Does

Produces a complete MedZone PR proposal document ready to send to a prospective physician client. The output combines:
1. **Healthcare Revenue Strategist** — financial analysis, service recommendations, ROI projections
2. **Medical Business Writer** — physician-grade copy, professional tone, no marketing fluff

## Activation

When the user runs `/client-proposal`, collect:

1. "Physician's name and title?" (e.g., Dr. María López, Internal Medicine)
2. "Specialty and municipality?"
3. "Practice size — solo, small group (2-5), or larger group?"
4. "What are their primary pain points?" (e.g., declining cap rates, rising costs, wants to add income)
5. "Which MedZone PR services are you proposing?" (or ask Claude to recommend based on specialty)
6. "Any specific financial figures you want included?" (current revenue, target income goal)
7. "What's the engagement fee/structure?"

## Output Format

```markdown
# Propuesta de Consultoría — MedZone PR
## Dr. [Name] | [Specialty] | [Municipality], Puerto Rico

---

### Su Realidad Actual
[2-3 sentences demonstrating insider knowledge of their specific situation.
Reference the payer mix, capitation dynamics, and financial pressure they face.
This is where trust is built — show you understand before offering solutions.]

---

### La Oportunidad

Con base en el perfil de su práctica, esto es lo que es posible:

| Servicio | Ingreso Mensual Proyectado | Costo Inicial | Punto de Equilibrio |
|----------|---------------------------|---------------|---------------------|
| [Service 1] | $[amount] | $[amount] | [X] meses |
| [Service 2] | $[amount] | $[amount] | [X] meses |
| **Total nuevo ingreso** | **$[amount]/mes** | | |

**Impacto anual proyectado**: $[amount]

---

### Cómo Trabajamos Juntos

**Fase 1 — Evaluación** (Semanas 1-2)
Auditamos sus operaciones actuales, finanzas, y mezcla de pagadores.
Entregable: Informe completo de oportunidad de ingresos.

**Fase 2 — Estrategia** (Semanas 3-4)
Diseñamos su portafolio de servicios personalizado y modelo financiero.
Entregable: Plan de implementación con proyecciones conservadoras.

**Fase 3 — Implementación** (Meses 2-3)
Construimos y lanzamos — usted se enfoca en sus pacientes.
Entregable: Servicios operando, staff entrenado, sistemas funcionando.

**Fase 4 — Optimización** (Mes 4 en adelante)
Refinamos basado en resultados reales.
Entregable: Informes mensuales de rendimiento.

---

### Sobre MedZone PR

Fundado por el Dr. James Collazo — médico licenciado con experiencia directa en
operaciones de práctica médica en Puerto Rico. Trabajamos exclusivamente con médicos
independientes en la isla porque conocemos este mercado desde adentro.

No somos consultores que leyeron sobre salud. Somos médicos que construimos negocios.

---

### Inversión

[Pricing structure]

---

### Próximo Paso

[Single, clear CTA — e.g., "Responda a este correo para agendar una llamada de 30 minutos.
Sin costo, sin compromiso."]

---
*MedZone PR | Dr. James Collazo, MD | medzonePR.com*

---

## English Version

[Mirror the full proposal in English if requested, maintaining the same financial figures
and structure but adapting the voice for English-language readers]
```

## Key Rules

- Always lead with the physician's problem, not MedZone PR's services
- Use real numbers — never vague percentages or "significant improvements"
- Spanish is the primary language for PR physician proposals
- The physician's credentials (MD background) are the #1 trust signal — use them
- Never use consulting buzzwords: "leverage," "synergy," "unlock potential," "transform"
- Keep it under 2 pages — physicians don't read long proposals
