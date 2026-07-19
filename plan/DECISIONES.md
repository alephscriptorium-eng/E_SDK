# DECISIONES — registro de emmanuel-sdk

Independiente de los registros de otros mundos (que no nos conocen o no
conocemos). Formato: DE-n, fecha, decisión, consecuencia. Las abiertas
(DA-n) las resuelve el custodio.

## Tomadas

- **DE-0 · 2026-07-16 · Sound system, no plataforma.** El mundo define el
  contrato de alimentación; el contenido lo traen los dramaturgos. Vale
  también para la autoridad: la fuente entra como primera línea por la
  puerta pública (kenosis). Consecuencia: cargar contenido de fábrica en el
  motor = devolución (gate WP-E00).
- **DE-1 · 2026-07-16 · Un solo origen por pieza; submodule como puntero,
  registry como canal.** Cada pieza vive en su repo (único origen). Para
  desarrollo, este mundo las monta como **submodules** (puntero git, no
  copia — decisión del custodio, 2026-07-16): DocumentMachineSDK,
  VectorMachineSDK, VectorMachineUI, AgentLoreSDK. Para distribución, el
  canal es el registry (`npm.scriptorium.escrivivir.co`): lo que este mundo
  produzca y merezca compartirse, se publica. Copiar árboles sigue
  prohibido.
- **DE-2 · 2026-07-16 · Compatibilidad por contrato con la lengua de
  líneas.** El formato de línea es compatible con la spec de zeus-sdk
  (procedencia citada en VISION). zeus se relee, jamás se toca ni se le
  introducen referencias a este mundo; cero llamadas entre mundos.
- **DE-3 · 2026-07-16 · El motor no trae lore.** Candados de VISION: sin
  admin-override, epoché (el colapso es de la persona), la nave abre y no
  genera, temas y líneas los traen los dramaturgos. La fuente no se
  empaqueta: satélites a ediciones remotas con autoridad.

## Abiertas (bloquean lo indicado)

- **DA-1 · ¿Kenosis y ser-desde-las-líneas se funden o compiten?** *(bloquea
  el diseño de gracia/jubileo/resurrección y WP-E31)* — la `@voz` del corpus
  propio como interioridad ya tiene sustrato; los canales
  `word|grace|covenant` aún no.
- **DA-2 · Volúmenes privados** *(bloquea WP-E30)* — ¿partición por-persona
  en Vector Machine, o volumen local files-first con sync?
- **DA-3 · Cómo entra el corpus fundacional** *(bloquea WP-E20)* — el mundo
  no tiene canon (DE-3): todo corpus es un volumen/release que valida contra
  la SPEC. Queda decidir la liturgia de entrada: ¿release exportado por un
  Dramaturgo (diseñador del juego), línea curada por el custodio, o ambas
  puertas? Y para el primero que entre: ¿qué ediciones/satélites remotos con
  autoridad se apuntan? La decisión es del custodio.
- **DA-4 · ¿Quién traza la línea base de una persona?** *(bloquea WP-E31)* —
  ¿ella misma, el dramaturgo, o su `@voz`?
- **DA-5 · Nombres de paquetes** *(bloquea publicaciones al registry)* —
  candidatos `@emmanuel/ichthys` (reconocimiento), `@emmanuel/charis`
  (gracia). Sin decidir.
