# BACKLOG — emmanuel-sdk, por olas

Convención: WPs autocontenidos con **CA** verificables. Estados: ⬜ pendiente
· 🔶 en curso (agente + fecha, lo marca el orquestador al asignar) · ✅
aceptado (solo orquestador). El brief declara qué repos toca cada WP
(PRACTICAS §2).

Este backlog NO gobierna zeus-sdk (prohibido tocarlo) ni ninguna codebase
ajena por dentro: las piezas se trabajan en **sus repos propios**.

---

## Ola E0 — El contrato

- ⬜ **WP-E00 · Gates del mundo** — test raíz `npm run gates` (patrón grep):
  (a) deps `file:`/tgz/ruta relativa; (b) referencias por ruta a codebases
  ajenas (zeus-sdk o cualquier otra); (c) lore/tema empaquetado en el motor;
  (d) texto de la fuente empaquetado (solo satélites, DE-3).
  **CA:** rojo con violación sintética de cada tipo; verde sobre el repo.

- ⬜ **WP-E01 · SPEC del contrato de alimentación** — formato de línea
  (tronco curado + satélites a fuentes con autoridad), compatible por
  formato con la lengua de zeus (procedencia: `zeus-sdk/plan/DATOS.md`
  §1–2, se relee, no se toca). Entregable: `SPEC/linea.md` + ejemplos
  **sintéticos** (jamás la fuente).
  **CA:** una línea sintética valida contra la spec con herramienta del
  repo; cero dependencia de código ajeno.

- ⬜ **WP-E02 · Starterkit del dramaturgo** — plantilla de volumen privado
  files-first + guía de segmentación (cantera de referencia:
  `network-engine/linea-aleph`, citada, no copiada).
  **CA:** un volumen de ejemplo sintético completo y navegable a mano.

## Ola E1 — La boca y las máquinas

- ⬜ **WP-E10 · Cartógrafo como paquete (motor sin lore)** — extraer de
  `mcp-agent-lore-sdk` (su repo) el motor mapa/nave/itinerarios, sin
  biblioteca de temas, y publicarlo al registry (nombre: DA-5).
  **CA:** instala del registry; gate (c) verde: cero lore de fábrica.

- ⬜ **WP-E11 · Boca firehose** — conversación indexada → línea (spec E01)
  → espacio exploratorio abierto en nave.
  **CA:** un hilo sintético cruza entero: línea válida + nave que lo abre.

- ⬜ **WP-E12 · La `@voz` personal** — girar la Document Machine
  (`para-la-voz-sdk`, su repo) hacia el corpus personal: configuración de
  volumen privado.
  **CA:** corpus sintético → informe de análisis → `@voz` que produce
  citando líneas.

- ⬜ **WP-E13 · Reencarnar los plugins gen-1** — los cuatro instalados en
  `.github/plugins/` (lore-sdk, vector-machine, foro-scraper, arg-board;
  procedencia en su README) pasan de la era Copilot a la era Claude/MCP:
  manifests saneados (rutas de datos propias, sin deps de la casa de
  origen), agentes operativos contra los submodules de ESTE mundo.
  **CA:** cada plugin ejercita su liturgia contra un submodule real (p. ej.
  lore-sdk: /feed → /diff-corpus sobre corpus sintético); gate (b) verde.

## Ola E2 — La primera línea *(bloqueada por DA-3)*

- ⬜ **WP-E20 · La primera línea** — el custodio vierte la fuente por la
  puerta pública: tronco curado + satélites a las ediciones decididas en
  DA-3.
  **CA:** valida contra SPEC; gate (d) verde (cero texto empaquetado);
  satélites resolubles.

- ⬜ **WP-E21 · Destilación con cita** — la `@voz` de la primera línea.
  **CA:** muestreo de afirmaciones de la `@voz`: cada una con cita a línea;
  lo insostenible, fuera.

## Ola E3 — La experiencia *(bloqueada por DA-1/DA-2/DA-4)*

- ⬜ **WP-E30 · Volumen privado P2P** — según DA-2; P2P/IPFS = pinnear y
  anotar.
  **CA:** dos volúmenes sintéticos se comparten sin servidor central.

- ⬜ **WP-E31 · Experiencia ichthys** — encuentro P2P o ad hoc de personas
  sobre sus líneas; el diseño respeta epoché (el colapso es de cada cual).
  **CA:** guion de experiencia completo sobre volúmenes sintéticos, con los
  cuatro candados de VISION verificados.
