# plan/ — centro de mando de emmanuel-sdk

Mundo del **ser-desde-las-líneas**, en fase papel-primero. Aquí trabaja un
**swarm de agentes** con un **orquestador que solo lee ficheros y piensa**:
el swarm implementa WPs, el orquestador asigna, revisa y es el único que
marca ✅; el usuario (el custodio) resuelve las decisiones abiertas.

Protocolo derivado del canónico de los mundos hermanos (@ 2026-07-16),
autocontenido aquí: este plan basta por sí solo, sin historial de chats ni
lecturas externas.

## Mapa de documentos

| doc | qué contiene | quién lo edita |
| --- | ------------ | -------------- |
| [VISION.md](VISION.md) | la idea, la kenosis, el contrato, las piezas, los candados, glosario | orquestador |
| [BACKLOG.md](BACKLOG.md) | olas E0–E3 con CA | orquestador (estado); swarm propone |
| [PRACTICAS.md](PRACTICAS.md) | **lectura obligatoria antes de tocar código** | orquestador |
| [DECISIONES.md](DECISIONES.md) | tomadas (DE-n) y abiertas (DA-n, las cierra el custodio) | orquestador |
| [roles/](roles/README.md) | protocolo del swarm (orquestador/worker/revisión/corrección/brief) | orquestador |
| [REPORTES/](REPORTES/) | un acta por WP, según [REPORTES/PLANTILLA.md](REPORTES/PLANTILLA.md) | swarm |

## Ciclo de trabajo (resumen; detalle en roles/)

1. El orquestador asigna un WP (marca 🔶 en BACKLOG, siempre en main) y
   entrega un brief que **declara los repos tocados** (este mundo y/o las
   piezas en sus repos propios).
2. El worker implementa en rama `wp/<id>-<slug>` (worktree si hay paralelo),
   con tests y auto-revisión.
3. Reporte en `REPORTES/WP-<id>-<slug>.md` con evidencia literal
   (`⏳ sin verificar` existe; inventar observaciones, no).
4. El orquestador revisa contra CA + PRACTICAS y marca ✅ (= autorización de
   merge) o devuelve.

## La regla que gobierna todo lo demás

Este mundo **no monta submodules ni copia árboles**: un solo origen por
pieza (su repo), un solo canal (`npm.scriptorium.escrivivir.co`). Y **el
motor no trae lore**: el contenido —temas, líneas, la fuente misma— entra
solo por la puerta pública del contrato.
