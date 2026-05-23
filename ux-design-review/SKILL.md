---
name: ux-design-review
description: Revisión y guía de diseño UX/UI para cualquier proyecto (web, app, SaaS, e-commerce, landing, dashboard), fundamentada en las Laws of UX y las 10 heurísticas de Nielsen. Usá este skill SIEMPRE que el usuario quiera (a) evaluar/auditar una interfaz existente —captura, URL, código o descripción— o (b) diseñar una pantalla, flujo o componente nuevo, incluso si no nombra "UX" ni "heurística". Se activa con pedidos como "revisá esta pantalla", "qué mejorarías de esta UI", "auditá la usabilidad de mi app/sitio", "cómo diseño este onboarding/checkout/dashboard", "esta landing convierte mal", "dame feedback de diseño", o cuando manda un screenshot de una interfaz pidiendo opinión. Produce un informe priorizado y accionable (Markdown) que el usuario aprueba y le pasa a un agente de implementación (ej. Claude Code) para aplicar los cambios o construir el diseño. NO usar para diseño gráfico no-interactivo (logos, flyers, ilustraciones) ni para escribir el código final directo sin pasar por el informe de aprobación.
---

# UX Design Review

Revisar y guiar diseño de interfaces con fundamento, no a ojo. Cada recomendación se apoya en un principio nombrado (una heurística de Nielsen o una Law of UX), porque así el usuario aprueba entendiendo el *porqué* y el resultado es defendible.

El entregable no es una crítica linda: es un **brief accionable**. El flujo real es:

> **El usuario pide revisión/diseño → este skill produce un informe → el usuario lo aprueba → se lo pasa a un agente de implementación (ej. Claude Code) para construir.**

Todo lo que escribas tiene que servir a ese flujo. Si una sección no ayuda a aprobar o a implementar, sobra.

## Los dos modos

Detectá cuál corresponde por el pedido. A veces se mezclan (ej. "revisá esto y proponé cómo rehacerlo") — está bien combinar.

- **Modo Evaluación** — hay una interfaz que ya existe (captura, URL, código, o descripción detallada) y el usuario quiere saber qué está mal y cómo mejorarlo.
- **Modo Diseño nuevo** — todavía no existe; el usuario quiere ayuda para diseñar una pantalla, flujo o componente desde cero, bien fundamentado.

## Antes de empezar

1. **Identificá qué te dieron** y trabajá con eso: una captura (miralá en detalle), una URL (podés navegarla/fetchearla si tenés la herramienta), código de un componente, o una descripción. Si es una captura, basá los hallazgos en lo que realmente se ve, no en suposiciones genéricas.
2. **Contexto mínimo:** necesitás saber **plataforma** (iOS / Android / web / responsive) y **objetivo de la pantalla** (qué tarea hace el usuario ahí). Si falta algo crítico y no se infiere, preguntá *una sola cosa*; si se infiere razonablemente, asumilo y aclaralo en el informe. No frenes el trabajo con interrogatorios.
3. **Cargá la teoría que vayas a usar.** No la tenés que recitar de memoria:
   - `references/nielsen-heuristics.md` — las 10 heurísticas (qué chequear + ejemplos) y el método de scoring (gravedad × esfuerzo → prioridad). **Leelo siempre**: es la base de la evaluación y de la priorización.
   - `references/laws-of-ux.md` — ~30 principios cognitivos (Hick, Fitts, Jakob, Miller, Gestalt, Peak-End, Von Restorff, etc.). Leelo cuando un hallazgo se explique mejor con un principio cognitivo que con una heurística, o en Modo Diseño para fundamentar decisiones.

## Modo Evaluación — workflow

1. **Recorré la interfaz con las 10 heurísticas** como checklist mental (no como lista a llenar). Para cada una preguntá "¿se cumple acá?". Sumá Laws of UX cuando aporten precisión (ej. un botón chico y lejano → Fitts; demasiadas opciones → Hick/Choice Overload).
2. **Registrá solo hallazgos reales.** No rellenes con las 10 heurísticas si no todas aplican. Un informe de 5 hallazgos sólidos vale más que 10 forzados. Si algo está *bien* y vale destacarlo, podés mencionarlo brevemente, pero el foco es lo accionable.
3. **Puntuá cada hallazgo** con gravedad (Alta/Media/Baja) y esfuerzo (Bajo/Medio/Alto), y derivá la prioridad (P1 quick wins → P3) según el método en `references/nielsen-heuristics.md`.
4. **Para cada hallazgo, definí el cambio concreto.** No "mejorar el feedback" sino "agregar estado *loading* al botón y un toast de confirmación al guardar".
5. **Escribí el informe** con el template de abajo, ordenando los hallazgos por prioridad.

## Modo Diseño nuevo — workflow

1. **Entendé la tarea del usuario en esa pantalla/flujo** y la plataforma. Ese es el norte: el diseño sirve a esa tarea.
2. **Proponé el diseño fundamentando cada decisión** en principios concretos. Ej.: "una sola acción primaria destacada por contraste (Von Restorff), defaults precargados para bajar la carga (Tesler), progreso visible si el flujo tiene varios pasos (Goal-Gradient)".
3. **Anticipá las heurísticas críticas** desde el diseño: estado del sistema (H1), prevención de errores (H5), control/deshacer (H3), reconocer en vez de recordar (H6). Diseñá para cumplirlas de entrada.
4. **Describí la estructura concreta:** layout, jerarquía, componentes, estados (vacío, carga, error, éxito), copy clave. Suficiente para que el agente de implementación lo construya sin inventar.
5. **Opcional — wireframe rápido:** si el entorno lo permite (ej. visualizer disponible) y ayuda a que el usuario apruebe *viendo* y no solo leyendo, acompañá la propuesta con un wireframe/diagrama de baja fidelidad. No es obligatorio ni reemplaza al brief de texto.
6. **Escribí el informe** con el template (sección "Propuesta de diseño" en lugar de "Hallazgos").

## Estructura del informe

El informe se entrega como archivo **Markdown** (`.md`) en `/mnt/user-data/outputs/`, porque se lee bien para aprobar y se le pasa directo al agente de implementación. Usá este esqueleto:

```markdown
# Revisión UX — [pantalla / flujo / producto]

**Modo:** Evaluación · **Plataforma:** [iOS / web / …] · **Objetivo de la pantalla:** [tarea del usuario]

## Resumen ejecutivo
[2–4 frases: estado general, los hallazgos más importantes, y qué se gana al implementar. Que el usuario entienda en 20 segundos si vale la pena seguir leyendo.]

## Hallazgos priorizados

### P1 · Quick wins (alto impacto, bajo esfuerzo)

#### 1. [Título corto y claro del problema]
- **Dónde:** [ubicación exacta en la interfaz]
- **Problema:** [qué falla y por qué molesta al usuario]
- **Principio:** [H# heurística / Law of UX citada]
- **Gravedad:** Alta · **Esfuerzo:** Bajo
- **Recomendación:** [el cambio concreto]

### P2 · Importantes
[mismo formato]

### P3 · Mejora continua
[mismo formato]

## Brief para Claude Code
[Ver más abajo. Es la sección que el usuario aprueba y copia.]
```

Para **Modo Diseño nuevo**, reemplazá "Hallazgos priorizados" por:

```markdown
## Propuesta de diseño
[Estructura, jerarquía y componentes, con cada decisión clave fundamentada en un principio entre paréntesis. Incluí estados: vacío, carga, error, éxito.]

## Decisiones de diseño y su fundamento
[Tabla o lista corta: decisión → principio → por qué. Para que el usuario apruebe entendiendo.]
```

## La sección "Brief para Claude Code" (lo más importante)

Es el *payload*. El usuario la aprueba y se la pega a Claude Code, así que tiene que ser ejecutable sin ambigüedad y sin que Claude Code tenga que adivinar.

Reglas:
- **Imperativo y concreto.** "Subí la altura del botón primario a 48px y agregale estado *loading*", no "mejorar los botones".
- **Ordenado por prioridad** (P1 primero), numerado.
- **Cada ítem se basta a sí mismo:** qué cambiar, dónde, y a qué estado final llegar.
- **Referenciá componentes/archivos** si los conocés del contexto (ej. `CheckoutButton.tsx`, `app/onboarding/`). Si no los conocés, describí el elemento de forma inequívoca.
- **Sin teoría acá.** El *porqué* ya quedó arriba en los hallazgos; el brief es solo el *qué hacer*. Claude Code necesita la acción, no la justificación.
- Si hay decisiones que dependen de algo que no sabés (ej. "¿el backend ya devuelve este error?"), marcalas como **[Verificar]** en vez de asumir.

Ejemplo de un ítem del brief:

```markdown
### P1
1. **Botón "Comprar" (pantalla de producto):** agregá estado `loading` (spinner + texto "Procesando…") y `disabled` mientras se procesa el pago, y un toast "Pedido confirmado" al terminar. Hoy no hay feedback y el usuario clickea de nuevo. → cumple H1 (visibilidad del estado).
2. **Inputs del checkout:** aceptá el teléfono con o sin guiones/espacios y normalizá del lado del cliente; no rechaces formatos válidos. → Postel's Law.
```

(Notá que acá sí va un puntero corto al principio al final del ítem — opcional, ayuda a Claude Code a no romper la intención. Mantenelo en una línea.)

## Tono y formato

- Escribí el informe en el **idioma del usuario** (por defecto, español rioplatense), directo y sin relleno. Priorizá entregables listos para usar sobre explicaciones largas.
- No infles. Si una sección no aplica (ej. no hay P3), omitila.
- Cero adulación. El valor está en encontrar problemas reales y proponer fixes claros, no en elogiar.
- Después de crear el archivo, presentalo con `present_files` y dale al usuario un cierre corto: 1–2 frases con lo más importante y la invitación a aprobar o ajustar. No repitas el informe en el chat.

## Errores a evitar

- **Listar las 10 heurísticas mecánicamente.** Reportá solo lo que aplica de verdad.
- **Recomendaciones vagas.** Todo hallazgo necesita un cambio concreto y ejecutable.
- **Saltearte el fundamento.** Si no podés nombrar el principio detrás de un hallazgo, probablemente sea opinión estética, no un problema de UX — distinguilo o dejalo afuera.
- **Generar el código final.** Este skill produce el informe; la implementación la hace el agente de implementación (ej. Claude Code) después de la aprobación. (Salvo que el usuario pida explícitamente el código acá.)
- **Sobre-preguntar.** Una pregunta crítica como mucho; lo demás se asume y se aclara.
