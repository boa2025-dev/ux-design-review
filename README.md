# UX Design Review — Claude Skill

Skill para Claude que **revisa y guía diseño de interfaces** con fundamento, basado en las **[Laws of UX](https://lawsofux.com/)** y las **10 heurísticas de usabilidad de Jakob Nielsen**.

No produce una crítica suelta: genera un **informe priorizado y accionable** (Markdown) que aprobás y le pasás a un agente de implementación (ej. Claude Code) para aplicar los cambios o construir el diseño.

## Qué hace

Funciona en dos modos, para cualquier proyecto (web, app, SaaS, e-commerce, landing, dashboard):

- **Evaluación** — auditás una interfaz existente (captura, URL, código o descripción). Detecta problemas de usabilidad, los puntúa por **gravedad × esfuerzo** y los ordena por prioridad (P1 quick wins → P3).
- **Diseño nuevo** — proponés una pantalla, flujo o componente desde cero, con cada decisión fundamentada en un principio concreto.

Cada hallazgo cita el principio que lo respalda (una heurística de Nielsen o una Law of UX), y el informe termina en un **brief listo para implementar**.

## Estructura

```
ux-design-review/
├── SKILL.md                      # Workflow, scoring y template del informe
└── references/
    ├── nielsen-heuristics.md     # Las 10 heurísticas + método de scoring
    └── laws-of-ux.md             # ~30 principios cognitivos y cómo aplicarlos
```

## Instalación

**En Claude.ai / app:** Settings → Capabilities → Skills → subir el archivo `ux-design-review.skill`.

**En Claude Code:** colocá la carpeta `ux-design-review/` dentro del directorio de skills de tu proyecto o de usuario (ej. `~/.claude/skills/ux-design-review/`).

> Para regenerar el `.skill` desde la carpeta fuente, solo hay que comprimir el contenido de `ux-design-review/` en un zip y renombrarlo a `.skill`.

## Cómo se usa

Una vez instalado, se activa solo cuando le pedís cosas como:

- "Revisá esta pantalla de checkout, ¿qué mejorarías?"
- "Auditá la usabilidad de mi landing."
- "¿Cómo diseño el onboarding de esta app?"

…incluso si no nombrás "UX" ni "heurística".

## Créditos y fuentes

- **Laws of UX** — Jon Yablonski · https://lawsofux.com/
- **10 Usability Heuristics** — Jakob Nielsen / Nielsen Norman Group
- Referencia en español de las heurísticas: https://uifrommars.com/10-reglas-heuristicas-como-aplicarlas/

El contenido de `references/` es una síntesis propia de esos marcos teóricos, redactada para uso del skill. Los marcos originales pertenecen a sus respectivos autores.

## Licencia

Sugerencia: MIT para el código/estructura del skill. Tené en cuenta que los marcos teóricos citados tienen sus propias licencias y autoría.
