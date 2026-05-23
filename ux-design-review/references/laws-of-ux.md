# Laws of UX — referencia de principios

Principios psicológicos y cognitivos para diseño de interfaces (basados en *Laws of UX*, Jon Yablonski). Cada entrada tiene: **qué dice** (definición breve, en palabras propias) y **qué chequear / cómo aplicar** (la parte accionable para una auditoría o un diseño nuevo).

Usá esta tabla para nombrar el principio exacto detrás de cada hallazgo. Citar el principio le da fundamento al informe: el usuario aprueba entendiendo el *por qué*, no por gusto estético.

---

## Carga cognitiva y memoria

### Cognitive Load (Carga cognitiva)
- **Qué dice:** los recursos mentales que el usuario necesita para entender y operar una interfaz son finitos; si los gastás en cosas accesorias, no le quedan para la tarea real.
- **Qué chequear:** ¿hay información o decisiones que no aportan a la tarea actual? ¿Se puede diferir, agrupar o eliminar? Pantallas saturadas, jerga, pasos redundantes.

### Working Memory (Memoria de trabajo)
- **Qué dice:** la memoria de trabajo retiene y manipula información temporalmente; es limitada y frágil.
- **Qué chequear:** ¿se obliga al usuario a recordar datos de una pantalla a otra (códigos, valores, instrucciones)? Mostralos en contexto en vez de pedir que los memorice.

### Miller's Law (Ley de Miller)
- **Qué dice:** la persona promedio retiene ~7 (±2) elementos en memoria de trabajo. No es un límite de diseño rígido, pero sí un recordatorio de agrupar.
- **Qué chequear:** listas o menús larguísimos sin agrupar. Aplicar *chunking* (ver abajo).

### Chunking (Agrupamiento)
- **Qué dice:** partir la información en grupos con significado la vuelve más fácil de procesar y recordar.
- **Qué chequear:** números de teléfono/tarjetas sin separar, formularios sin secciones, navegación sin categorías. Agrupá por significado.

### Selective Attention (Atención selectiva)
- **Qué dice:** las personas filtran el entorno y atienden solo a un subconjunto de estímulos, normalmente los ligados a su objetivo. Lo que parece "publicidad" se ignora (banner blindness).
- **Qué chequear:** info importante con aspecto de aviso/banner. CTAs camuflados. Ubicá lo crítico en el camino del ojo, no en zonas que se ignoran.

---

## Decisión y opciones

### Hick's Law (Ley de Hick)
- **Qué dice:** el tiempo para decidir crece con la cantidad y complejidad de opciones.
- **Qué chequear:** menús/onboardings con demasiadas opciones a la vez. Reducí, escondé lo avanzado, usá defaults inteligentes, dividí decisiones complejas en pasos.

### Choice Overload (Sobrecarga de opciones)
- **Qué dice:** demasiadas opciones abruman y paralizan (la "paradoja de la elección").
- **Qué chequear:** grillas de planes/productos infinitas, demasiados CTAs compitiendo. Destacá una opción recomendada, limitá lo visible.

### Occam's Razor (Navaja de Occam)
- **Qué dice:** entre soluciones que funcionan igual, elegí la más simple (menos supuestos, menos elementos).
- **Qué chequear:** pasos, campos o pantallas que se pueden eliminar sin perder función. Si dudás de un elemento, probá sacarlo.

### Tesler's Law (Ley de conservación de la complejidad)
- **Qué dice:** todo sistema tiene una complejidad mínima irreducible. La pregunta es quién la absorbe: el sistema o el usuario.
- **Qué chequear:** ¿se le está pasando al usuario complejidad que el sistema podría asumir (autocompletar, defaults, inferencia)? Cargá esa complejidad del lado del producto.

### Paradox of the Active User (Paradoja del usuario activo)
- **Qué dice:** los usuarios no leen manuales; empiezan a usar el producto de una.
- **Qué chequear:** funciones que dependen de leer instrucciones previas. Diseñá para que se aprenda usando: tooltips contextuales, defaults sensatos, recuperación de errores.

---

## Percepción y agrupamiento (Gestalt)

### Law of Proximity (Proximidad)
- **Qué dice:** los elementos cercanos se perciben como un grupo.
- **Qué chequear:** espaciado que agrupa cosas no relacionadas o separa cosas relacionadas (label lejos de su campo, acción lejos de su objeto). Ajustá el espaciado para reflejar relaciones reales.

### Law of Common Region (Región común)
- **Qué dice:** los elementos dentro de un borde/área compartida se perciben como grupo.
- **Qué chequear:** uso de tarjetas, contenedores y fondos. ¿Los bordes agrupan lo que corresponde? Cards bien usadas reducen carga cognitiva.

### Law of Similarity (Similitud)
- **Qué dice:** elementos visualmente similares se perciben como relacionados.
- **Qué chequear:** ¿elementos con la misma función se ven distintos (confunde)? ¿Elementos distintos se ven iguales (falsa relación)? Coherencia visual = coherencia semántica.

### Law of Uniform Connectedness (Conexión uniforme)
- **Qué dice:** elementos conectados visualmente (líneas, contenedores, color compartido) se perciben más relacionados que los que solo están cerca.
- **Qué chequear:** agrupamientos que necesitan conexión explícita (líneas, fondos) y no la tienen, o viceversa.

### Law of Prägnanz (Simplicidad)
- **Qué dice:** el ojo interpreta lo ambiguo o complejo en su forma más simple posible, porque exige menos esfuerzo.
- **Qué chequear:** formas/layouts innecesariamente complejos. Simplificá: formas reconocibles, jerarquía clara.

---

## Interacción y rendimiento

### Fitts's Law (Ley de Fitts)
- **Qué dice:** el tiempo para alcanzar un target depende de su tamaño y de la distancia. Targets grandes y cercanos = más rápidos y fáciles.
- **Qué chequear:** botones chicos, áreas táctiles menores a ~44px, acciones primarias lejos del pulgar en mobile, targets pegados que generan errores. Agrandá lo importante, acercalo al recorrido natural.

### Doherty Threshold (Umbral de Doherty)
- **Qué dice:** la productividad se dispara cuando sistema y usuario responden a un ritmo <400ms; nadie debería esperar al otro.
- **Qué chequear:** acciones sin feedback inmediato, esperas sin indicador. Usá respuestas optimistas, skeletons, percepción de velocidad.

### Flow (Flujo)
- **Qué dice:** estado de inmersión total y enfocada en una actividad. Las interrupciones lo rompen.
- **Qué chequear:** interrupciones innecesarias (modales, pop-ups, pedidos de permiso a destiempo) que cortan una tarea en curso.

### Postel's Law (Ley de Postel / robustez)
- **Qué dice:** sé liberal en lo que aceptás, conservador en lo que devolvés. Tolerá variedad en el input del usuario.
- **Qué chequear:** campos que rechazan formatos válidos (teléfonos con/sin guiones, mayúsculas, espacios). Aceptá variantes y normalizá del lado del sistema.

---

## Modelos mentales y expectativas

### Mental Model (Modelo mental)
- **Qué dice:** el usuario llega con un modelo interno de cómo *debería* funcionar algo, formado por experiencias previas.
- **Qué chequear:** ¿la interfaz contradice lo que el usuario espera? Alinear con el modelo mental reduce fricción; romperlo exige muy buena razón.

### Jakob's Law (Ley de Jakob)
- **Qué dice:** los usuarios pasan la mayor parte del tiempo en *otros* sitios, así que esperan que el tuyo funcione como los que ya conocen.
- **Qué chequear:** patrones reinventados sin necesidad (carritos, búsqueda, navegación, formularios). Seguí convenciones salvo que innovar aporte un valor claro.

### Cognitive Bias (Sesgo cognitivo)
- **Qué dice:** errores sistemáticos de juicio que afectan percepción y decisión; el diseño puede amplificarlos o mitigarlos.
- **Qué chequear:** patrones que explotan sesgos de forma manipuladora (dark patterns) vs. usarlos éticamente (defaults útiles, anclaje honesto).

---

## Motivación, progreso y memoria de la experiencia

### Goal-Gradient Effect (Efecto gradiente de meta)
- **Qué dice:** la motivación aumenta a medida que el objetivo se acerca.
- **Qué chequear:** procesos largos sin indicador de progreso. Mostrá avance, dá un empujón inicial (progreso "ya empezado"), barras de pasos.

### Zeigarnik Effect (Efecto Zeigarnik)
- **Qué dice:** se recuerdan mejor las tareas incompletas o interrumpidas que las terminadas.
- **Qué chequear:** oportunidades para señalar lo que falta (perfil incompleto, checklist de onboarding) y motivar a cerrarlo.

### Peak-End Rule (Regla del pico y el final)
- **Qué dice:** la experiencia se juzga sobre todo por su momento más intenso y por cómo termina, no por el promedio.
- **Qué chequear:** ¿hay un pico positivo memorable? ¿El final (confirmación, éxito, despedida) deja buena sensación? Cuidá especialmente cierres y momentos de error.

### Serial Position Effect (Efecto de posición serial)
- **Qué dice:** se recuerdan mejor el primer y el último ítem de una serie.
- **Qué chequear:** ubicá lo más importante al principio y al final de listas y navegaciones; el medio se diluye.

### Von Restorff Effect (Efecto de aislamiento / Von Restorff)
- **Qué dice:** entre varios elementos similares, el que difiere se recuerda mejor.
- **Qué chequear:** ¿la acción principal se distingue del resto? Destacá un único CTA por contraste; si todo grita, nada resalta.

---

## Estética, esfuerzo y priorización

### Aesthetic-Usability Effect (Efecto estética-usabilidad)
- **Qué dice:** lo que se ve más lindo se percibe como más usable, y genera más tolerancia a problemas menores.
- **Qué chequear:** no descuidar el pulido visual (no es solo cosmética: afecta la percepción de calidad y confianza). Cuidado: la estética puede tapar problemas reales de usabilidad en tests.

### Pareto Principle (Principio de Pareto / 80-20)
- **Qué dice:** ~80% de los efectos vienen del ~20% de las causas.
- **Qué chequear:** identificá el 20% de funciones/pantallas que generan el 80% del valor y priorizá ahí. No gastes esfuerzo parejo en todo.

### Parkinson's Law (Ley de Parkinson)
- **Qué dice:** una tarea se infla hasta ocupar todo el tiempo disponible.
- **Qué chequear:** procesos que podrían acelerarse con autocompletado, defaults o límites de tiempo. Reducí la fricción para que la tarea no se "estire".
