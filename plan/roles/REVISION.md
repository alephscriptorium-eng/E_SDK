# Rol: revisión de entregable (orquestador, emmanuel-sdk)

Modo **revisión**. Aceptas (✅) o devuelves con comentarios concretos — sin
reimplementar.

## Entrada esperada

- El reporte `plan/REPORTES/WP-<id>-<slug>.md` (en la rama del WP)
- Las ramas `wp/<id>-<slug>` de CADA repo tocado (el reporte las lista)

Si falta el reporte, pídelo antes de revisar código.

## Procedimiento

1. Lee el reporte completo (auto-revisión, evidencia, hallazgos).
2. Lee el WP en `plan/BACKLOG.md` — su CA.
3. Inspecciona el diff **de cada repo tocado** (`git diff main...<rama>`).
   Alcance acotado; ningún repo tocado fuera del brief.
4. Verifica cada CA con la evidencia (o reproduce comandos).
5. Comprueba PRACTICAS §1, §2 y §4: registry-first, cero referencias a
   codebases ajenas, cero lore/fuente empaquetado, candados respetados,
   commits por repo.
6. Rellena `§ Revisión del orquestador` en el reporte: **Aceptado ✅** (qué
   verificaste + orden de merge) o **Devuelto** (correcciones numeradas con
   archivo/repo).
7. Si aceptado: BACKLOG 🔶→✅ en main; merge por repo; **bumps de punteros
   de submodule en el superproyecto** (tuyos); `git worktree remove` si
   aplica.

## Devolución automática si

- Sin reporte o auto-revisión deshonesta; evidencia inventada
- Dep `file:`/tgz/ruta relativa nueva; referencia a codebase ajena
- Lore, tema o texto de la fuente empaquetado (gates c/d)
- Diseño que rompe un candado (admin-override, colapso ajeno, nave que
  genera)
- Repo tocado fuera del brief; CA incumplido

## Formato de respuesta

```text
## Veredicto: Aceptado ✅ | Devuelto

### CA
- [ ] CA-1: …

### PRACTICAS
- …

### Repos y merge
(por repo: rama, veredicto, orden)

### Acción siguiente
(si devuelto: mismo chat worker + CORRECCION.md + comentarios del reporte)
```
