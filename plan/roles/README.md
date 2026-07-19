# plan/roles — el protocolo del swarm (emmanuel-sdk)

Derivado del protocolo canónico de los mundos hermanos (@ 2026-07-16),
autocontenido aquí. Agnóstico de herramienta: cualquier runner los consume
tal cual.

## Roles

| Prompt | Rol | Cuándo |
| ------ | --- | ------ |
| [ORQUESTADOR.md](ORQUESTADOR.md) | Orquestador | Chat principal: estado, asignación, revisión, ✅ |
| [WORKER.md](WORKER.md) | Worker | Chat nuevo por WP: implementar + reportar |
| [REVISION.md](REVISION.md) | Orquestador | Revisar un entregable (reporte + diffs) |
| [CORRECCION.md](CORRECCION.md) | Worker | Tras devolución: corregir en las mismas ramas |
| [BRIEF.md](BRIEF.md) | Orquestador → usuario | Plantilla de brief para lanzar un worker |

## Dónde vive el estado

- **`plan/BACKLOG.md` es del orquestador y vive en main.** Marca 🔶 al
  asignar y ✅ al aceptar. El worker no lo edita nunca.
- **El reporte vive en la rama del WP** (`plan/REPORTES/WP-….md`): nombre
  único = sin conflictos; llega a main con el merge.
- **`plan/DECISIONES.md` §abiertas es del custodio.**

## Submodules (regla de este mundo, PRACTICAS §2)

Un WP puede tocar el superproyecto y/o N submodules (cada uno repo git
propio):

- El brief **declara los repos tocados**; rama `wp/<id>-<slug>` en CADA repo
  tocado.
- El reporte lista commits POR repo.
- El **bump del puntero de submodule** lo hace el orquestador al aceptar
  (✅) — nunca el worker.
- Paralelismo: un worktree por chat worker:

```bash
git worktree add ../emmanuel-wp-e00 -b wp/e00-gates
# al aceptar y mergear: git worktree remove ../emmanuel-wp-e00
```

## Flujo

```text
1. Chat orquestador (ORQUESTADOR.md) → «Estado del swarm»
2. Orquestador propone lote, marca 🔶 en main y rellena un BRIEF por WP
3. Usuario abre worktrees + chats worker (WORKER.md + brief)
4. Worker termina → reporte en plan/REPORTES/ (en su rama) → avisa
5. Chat orquestador (REVISION.md + reporte + ramas) → ✅ + merge, o devolución
6. Si devuelto: mismo chat worker (CORRECCION.md + comentarios del reporte)
```

## Reglas de oro

1. Un WP = un chat worker = una rama por repo tocado = (si hay paralelo) un
   worktree.
2. Solo el orquestador escribe en BACKLOG; solo el custodio cierra
   DECISIONES.
3. Prohibido tocar o nombrar codebases ajenas (PRACTICAS §1.2).
4. El motor no trae lore; la fuente no se empaqueta (PRACTICAS §1.5).
5. El brief + `plan/` bastan: no se asume historial de otros chats.
6. ✅ implica autorización de merge.
7. Commits convencionales (PRACTICAS §1.9).

## Primer lote sugerido (Ola E0)

WP-E00 (gates) y WP-E01 (SPEC del contrato) — paralelizables. E01 es el
corazón del sound system: conviene un worker con criterio, no el más rápido.
