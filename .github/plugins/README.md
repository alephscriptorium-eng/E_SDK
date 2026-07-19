# Plugins — procedencia y estado

Copias con procedencia (2026-07-16) de la generación 1 de la casa madre de
las piezas (`.github_V1/plugins/` @ era Copilot, congelada 2026-05). El
protocolo que los rige: [`../PLUGINS.md`](../PLUGINS.md). **Estado: material
heredado, pendiente de reencarnación a la era Claude/MCP (WP-E13)** — los
manifests referencian rutas y dependencias de su casa de origen
(`ARCHIVO/PLUGINS/`, MCPGallery) que aquí no existen aún.

| plugin | puentea con | por qué está aquí |
|---|---|---|
| `lore-sdk` | submodule `DocumentMachineSDK` | la liturgia `@voz` completa: crear-voz, alimentar-corpus (/feed → /diff → /merge) |
| `vector-machine` | submodule `VectorMachineSDK` + UI | integración del stack vectorial y diseño de su fachada MCP |
| `foro-scraper` | la boca firehose (WP-E11) | scraping de foros/blogs con estado pausable — conversaciones indexadas → corpus |
| `arg-board` | la experiencia (WP-E31) | motor conversacional ARG: tableros transmedia, turnos como commits, BOE inmutable |

## No traídos (y dónde quedan)

- `escribiente` (audio→whisper) — depende de `wire-editor` + submodule
  node-red que este mundo no monta. Si el corpus oral llega, se trae con su
  cadena entera.
- `agent-creator` — catálogo de la generación 1; su sucesor real es la
  cristalización de la Document Machine y Bot Hilbert (ya en los
  submodules).

Ambos siguen en su origen: `.github_V1/plugins/` de la casa de las piezas.
