# Brief para lanzar worker (emmanuel-sdk)

_Plantilla que rellena el **orquestador** (tras marcar 🔶 en BACKLOG) y el
usuario pega en un **chat nuevo** junto con `plan/roles/WORKER.md`._

---

```text
(rol) plan/roles/WORKER.md

WP: WP-E?? · <título>
Repos tocados: emmanuel-sdk | <repo de pieza> (ruta del clon) …
Rama: wp/e??-<slug> (en cada repo tocado)
Worktree: ../emmanuel-wp-e??   (solo si hay workers en paralelo)
Reporte: plan/REPORTES/WP-E??-<slug>.md

Lecturas extra (además de PRACTICAS + WP en BACKLOG + VISION):
- plan/DECISIONES.md DE-?/DA-?
- (archivos concretos que el orquestador ya identificó)

Notas del orquestador:
- (conflictos con otros WPs en vuelo, orden de merge, excepciones de gates…)

Empieza: sitúate en rama/worktree, lee PRACTICAS entero, luego implementa.
```

---

## Ejemplo — Ola E0

### WP-E01

```text
(rol) plan/roles/WORKER.md

WP: WP-E01 · SPEC del contrato de alimentación
Repos tocados: emmanuel-sdk (solo SPEC/ y ejemplos sintéticos)
Rama: wp/e01-spec-linea
Reporte: plan/REPORTES/WP-E01-spec-linea.md

Lecturas extra:
- plan/VISION.md §contrato de alimentación y §candados
- zeus-sdk/plan/DATOS.md §1–2 (SOLO lectura: procedencia del formato;
  prohibido tocar o citar hacia allí)

Notas: ejemplos SINTÉTICOS — la fuente real no entra aquí (gate d, DE-3);
la vierte el custodio en WP-E20 cuando DA-3 se cierre.
```
