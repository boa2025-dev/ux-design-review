# Heurísticas de Nielsen + método de evaluación

Las 10 reglas heurísticas de usabilidad de Jakob Nielsen, en palabras propias, con **qué chequear** y **ejemplos** (bien/mal). Sirven para detectar errores de usabilidad "de bulto" sin tests con usuarios. Son la columna vertebral del **Modo Evaluación**.

Al final está el **método de scoring** (gravedad × esfuerzo → prioridad) adaptado del proceso clásico de evaluación heurística.

---

## Las 10 heurísticas

### H1 — Visibilidad del estado del sistema
- **Idea:** el usuario siempre debe saber qué está pasando; recibe *feedback* claro y a tiempo razonable de cada acción.
- **Qué chequear:** botones sin estado *hover*/*loading*/*disabled*; envíos sin confirmación ni error; procesos largos sin indicador; campo de formulario activo no diferenciado.
- **Ejemplo:** ✅ barra de carga que avanza, toast de "Guardado". ❌ hacés clic en "Enviar" y no pasa nada visible.

### H2 — Coincidencia entre el sistema y el mundo real
- **Idea:** hablá el idioma del usuario, con palabras y conceptos familiares; seguí convenciones del mundo real.
- **Qué chequear:** jerga técnica ("Error 404", "token inválido"), textos sin contexto ("Date de alta"), colores con significado invertido (éxito en rojo).
- **Ejemplo:** ✅ "No encontramos esa página". ❌ "Error 500: Internal Server Error".

### H3 — Control y libertad del usuario
- **Idea:** dale salidas de emergencia: deshacer, cancelar, volver. El usuario se equivoca y necesita revertir sin drama.
- **Qué chequear:** acciones destructivas sin deshacer/confirmar; flujos sin "volver" o "cancelar"; cambios irreversibles sin aviso.
- **Ejemplo:** ✅ "Deshacer envío" de Gmail; confirmación antes de borrar. ❌ se borra al toque, sin vuelta atrás.

### H4 — Consistencia y estándares
- **Idea:** lo mismo debe verse y comportarse igual en todo el producto; respetá convenciones de la plataforma (alineado con Jakob's Law).
- **Qué chequear:** botones/enlaces inconsistentes; íconos con significado no estándar; elementos clicables que no parecen clicables; términos distintos para la misma cosa.
- **Ejemplo:** ✅ el pulgar arriba = like en todos lados. ❌ una estrella que a veces es favorito y a veces rating.

### H5 — Prevención de errores
- **Idea:** mejor que un buen mensaje de error es que el error no ocurra. Diseñá para evitarlo.
- **Qué chequear:** acciones peligrosas sin confirmación; falta de validación en tiempo real; ausencia de avisos preventivos.
- **Ejemplo:** ✅ Gmail te avisa si escribiste "adjunto" y no adjuntaste nada; medidor de fuerza de contraseña. ❌ dejás enviar un formulario con campos mal sin avisar antes.

### H6 — Reconocer en lugar de recordar
- **Idea:** minimizá la carga de memoria; mostrá las opciones en vez de obligar a recordarlas.
- **Qué chequear:** opciones escondidas detrás de menús/hover/modales; pedir datos que el sistema ya conoce; falta de autocompletado o de "vistos recientemente".
- **Ejemplo:** ✅ autocompletar, "productos que viste". ❌ tener que recordar un código de un paso anterior.

### H7 — Flexibilidad y eficiencia de uso
- **Idea:** que sirva tanto al novato como al experto; aceleradores para los que ya saben.
- **Qué chequear:** falta de atajos, defaults o personalización; onboarding obligatorio que no se puede saltar; un único camino para todos.
- **Ejemplo:** ✅ atajos de teclado + onboarding salteable; configuración avanzada opcional. ❌ obligar al experto a pasar por el tutorial cada vez.

### H8 — Estética y diseño minimalista
- **Idea:** mostrá solo lo necesario en cada momento; cada elemento extra compite con lo relevante.
- **Qué chequear:** pantallas saturadas; información que no aporta a la tarea actual; demasiados CTAs.
- **Ejemplo:** ✅ el home de Google (casi solo el buscador). ❌ landing con 8 banners y 5 botones compitiendo.

### H9 — Ayudar a reconocer, diagnosticar y recuperarse de errores
- **Idea:** cuando el error igual ocurre, el mensaje debe decir en lenguaje claro qué pasó, por qué, y cómo salir.
- **Qué chequear:** mensajes genéricos ("usuario o contraseña incorrectos" sin pista); errores que culpan al usuario; páginas de error sin salida.
- **Ejemplo:** ✅ 404 que explica y ofrece volver al home o buscar. ❌ "Se produjo un error" sin más.

### H10 — Ayuda y documentación
- **Idea:** lo ideal es no necesitar manual, pero cuando hace falta, que la ayuda sea fácil de encontrar y orientada a la tarea.
- **Qué chequear:** campos complejos sin explicación; ausencia de FAQ/tooltips; ayuda que no se encuentra cuando se necesita.
- **Ejemplo:** ✅ tooltip que explica el formato de la contraseña; FAQ accesible. ❌ formulario críptico sin ninguna pista.

---

## Método de scoring (gravedad × esfuerzo → prioridad)

Para que el informe sea accionable y priorizable, cada hallazgo se puntúa en dos ejes (adaptado del proceso clásico de evaluación heurística, que usa *ranking* de gravedad + *rating* de facilidad de solución):

**Gravedad** — impacto en el usuario / en la conversión:
- **Alta** — bloquea o frustra una tarea clave; el usuario se va o se equivoca seguido.
- **Media** — genera fricción notable pero hay workaround.
- **Baja** — molestia menor, cosmético, edge case.

**Esfuerzo** — costo de implementación:
- **Bajo** — cambio puntual de copy, color, espaciado, estado.
- **Medio** — nuevo componente o lógica acotada.
- **Alto** — rediseño de flujo, cambios estructurales o de backend.

**Prioridad derivada** (para ordenar el informe):
- **P1 — Quick wins:** gravedad Alta/Media + esfuerzo Bajo. Van primero: máximo impacto, mínimo costo.
- **P2 — Importantes:** gravedad Alta + esfuerzo Medio/Alto.
- **P3 — Mejora continua:** gravedad Baja, o gravedad Media + esfuerzo Alto. Para próximas iteraciones.

Regla práctica: si hay poco tiempo, las heurísticas que más mueven la aguja con poco cambio suelen ser **H1 (estado del sistema), H5 (prevención de errores) y H3 (control del usuario)**.

> Nota mobile vs. escritorio: los principios son los mismos, pero la implementación cambia (espacio limitado, áreas táctiles, conexión más lenta, estándares de plataforma distintos). Anotá la plataforma objetivo y evaluá en ese contexto.
