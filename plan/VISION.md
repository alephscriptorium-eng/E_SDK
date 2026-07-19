# VISION — emmanuel-sdk

> WIP 2026-07-16. Papel primero. Lo abierto no se decide solo: lo resuelve
> el custodio (DECISIONES §abiertas).

## La idea

La persona trabaja su ser: **«ser es lo que emerge de las líneas que ha
almacenado y sus experiencias sobre ellas»**. El mundo da la boca, el volumen
privado y la maquinaria de destilación; el contenido lo trae cada cual.

No es plataforma: es **sound system** — spec de formatos, starterkit y
segmentadores para que cada dramaturgo traiga su línea.

Gesto fundante — **kenosis**: la autoridad no tiene canal privilegiado. La
fuente que este mundo venera entra como primera línea por el contrato
público, sujeta a las mismas reglas que la línea de cualquier persona.

## Contrato de alimentación

- **Lengua de líneas:** compatible por formato con la spec de zeus-sdk
  (`zeus-sdk/plan/DATOS.md` §1–2 — procedencia citada; se relee, jamás se
  toca): tronco curado por autor + satélites a fuentes remotas con
  autoridad. Compatibilidad por contrato, no conexión: cero llamadas entre
  mundos.
- **Boca firehose:** conversaciones indexadas → líneas → espacios
  exploratorios puros. Cantera de segmentadores (referencia histórica, no
  dependencia): `network-engine/linea-aleph` (Python, minúsculas).
- **Volúmenes privados:** files-first; objetos pesados inmutables y
  direccionables; añadir P2P/IPFS será pinnear y anotar, no migrar.

## Piezas — puntero, no copia

Un solo origen por pieza (su repo). Se montan como **submodules** (puntero
git, DE-1) para desarrollo; la distribución va por el registry
(`npm.scriptorium.escrivivir.co`). Copiar árboles, prohibido.

| pieza | submodule | papel aquí |
|---|---|---|
| Document Machine | `DocumentMachineSDK` (`para-la-voz-sdk`) | cristalizar la `@voz` de un corpus personal — la interioridad |
| Vector Machine | `VectorMachineSDK` (`aleph-deep-wiki`) | el corpus consultable (RAG) |
| Vector Machine UI | `VectorMachineUI` (`vm-sdk-chromadb-admin`) | consola del volumen |
| Cartógrafo + nave | `AgentLoreSDK` (`mcp-agent-lore-sdk`) | firehose → mapa + nave (browser). Su biblioteca trae dossiers de ejemplo del repo origen — no son canon de este mundo; WP-E10 extrae el motor limpio a paquete |

## La primera línea

El custodio vierte la fuente por la puerta pública: satélites a ediciones
remotas con autoridad (no se empaqueta texto), tronco curado como cualquier
dramaturgo. De ese corpus se destila la `@voz`; **lo que la `@voz` no
sostenga con cita a línea, no entra**.

## Candados

1. **Sin admin-override:** la autoridad juega sujeta al contrato.
2. **Epoché:** nadie colapsa el ser de otro; la identidad afirmada es acto
   de la persona.
3. **La nave abre dossiers; no los genera.**
4. **El motor no trae lore:** temas y líneas los traen los dramaturgos.

## Glosario mínimo

- **línea** — obra de datos: tronco curado + satélites con autoridad.
- **dramaturgo** — quien trae su línea y traza experiencias sobre ella.
- **`@voz`** — agente cristalizado de un corpus: produce *desde* sus reglas,
  no hablando sobre él.
- **nave** — browser de un dossier/espacio exploratorio; abre, no genera.
- **epoché** — mantener el campo abierto; colapsar es derecho de la persona.
- **kenosis** — la autoridad entra al contrato común, sin canal privilegiado.
