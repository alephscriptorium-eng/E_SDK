# WP-I60 · activacion-skill — reporte

| dato | valor |
| ---- | ----- |
| agente | worker (subagente) |
| fecha | 2026-07-19 |
| repos tocados | emmanuel-sdk (solo `plan/`) |
| ramas | `wp/i60-activacion` |
| commits | `40c4b03` (dedup) + commit de este reporte |
| estado propuesto | listo para revisión |

## Qué se hizo

Se desduplicó el protocolo del swarm en `plan/roles/`. Los 5 prompts genéricos
(ORQUESTADOR, WORKER, REVISION, CORRECCION, BRIEF) eran una copia derivada del
protocolo canónico y se **eliminaron con `git rm`**; su fuente pasa a ser el
paquete publicado `@alephscript/skills-scriptorium@0.2.0 ›
skills/swarm-orquestacion` (versión **fijada**, registry
`npm.scriptorium.escrivivir.co`). `plan/roles/README.md` se reescribió como
**referencia versionada** más la **calibración local** de emmanuel
(multi-repo/submodules §2 y «el motor no trae lore»), visible sin abrir el
paquete. Se cosieron `plan/README.md` y `plan/PRACTICAS.md` para que
«autocontenido» signifique «autocontenido vía referencia versionada, resoluble
por `npm view` (C8)», no «copiado aquí».

## Archivos tocados (por repo)

- emmanuel-sdk · `plan/roles/ORQUESTADOR.md` · **borrado** (git rm) — copia genérica
- emmanuel-sdk · `plan/roles/WORKER.md` · **borrado** (git rm) — copia genérica
- emmanuel-sdk · `plan/roles/REVISION.md` · **borrado** (git rm) — copia genérica
- emmanuel-sdk · `plan/roles/CORRECCION.md` · **borrado** (git rm) — copia genérica
- emmanuel-sdk · `plan/roles/BRIEF.md` · **borrado** (git rm) — copia genérica
- emmanuel-sdk · `plan/roles/README.md` · modificado — referencia versionada + calibración local
- emmanuel-sdk · `plan/README.md` · modificado — «autocontenido» = vía referencia versionada
- emmanuel-sdk · `plan/PRACTICAS.md` · modificado — cabecera: calibración local sobre el paquete
- emmanuel-sdk · `plan/REPORTES/WP-I60-activacion-skill.md` · creado — este reporte

## Evidencia

> Salida literal.

### CA1 · dedup (los prompts genéricos ya no están copiados)

```
$ grep -rniE "^# Rol: (orquestador|agente worker|revisión|corrección)|^# Brief para lanzar worker" plan/
exit=1        # ← sin coincidencias: ninguna definición de prompt genérico vive ya en plan/

$ ls -1 plan/roles/
README.md     # ← único fichero; la definición del protocolo es ahora referencia al paquete
```

### CA2 · referencia versionada resoluble (C8)

```
$ npm view @alephscript/skills-scriptorium --registry=https://npm.scriptorium.escrivivir.co version
0.2.0
===EXIT 0===

$ npm view @alephscript/skills-scriptorium --registry=https://npm.scriptorium.escrivivir.co
@alephscript/skills-scriptorium@0.2.0 | UNLICENSED | deps: none | versions: 2
Skills library — método marco-agnóstico en formato skill estándar (SKILL.md + recursos)
https://skills.s-sdk.escrivivir.co
dist
.tarball: https://npm.scriptorium.escrivivir.co/@alephscript/skills-scriptorium/-/skills-scriptorium-0.2.0.tgz
.shasum: d7001e24d2d2278c34d0b176feeac004cda09455
dist-tags:
latest: 0.2.0

$ npm view @alephscript/skills-scriptorium@0.2.0 --registry=https://npm.scriptorium.escrivivir.co version
0.2.0
exit=0        # ← la versión FIJADA 0.2.0 existe y resuelve
```

### CA3 · autocontención (calibración local visible sin abrir el paquete)

```
$ grep -rniE "el motor no trae lore|bump del puntero de submodule|referencia versionada|npm view" plan/roles/README.md plan/README.md plan/PRACTICAS.md
plan/roles/README.md:9:## Protocolo canónico (referencia versionada)
plan/roles/README.md:22:npm view @alephscript/skills-scriptorium@0.2.0 \
plan/roles/README.md:49:- El **bump del puntero de submodule** en el superproyecto lo hace el
plan/roles/README.md:55:### 2. El motor no trae lore (PRACTICAS §1.5, DE-3)
plan/README.md:12:vía referencia versionada** (resoluble por `npm view`, C8): este plan basta por
plan/README.md:24:| [roles/](roles/README.md) | referencia versionada al protocolo del swarm + calibración local (submodules, lore-fuera) | orquestador |
plan/PRACTICAS.md:6:`npm.scriptorium.escrivivir.co`, resoluble por `npm view` — C8; ver
plan/PRACTICAS.md:28:5. **El motor no trae lore (DE-3).** Ni temas, ni líneas, ni la fuente
```

El `plan/` sigue operable con su contenido + la referencia: submodules §2 y
lore-fuera quedan escritos en el árbol; el resto del protocolo se resuelve por
`npm view`/`npm install` de la versión fijada.

### CA4 · alcance (el diff toca SOLO plan/)

```
$ git diff --stat main...HEAD
 plan/PRACTICAS.md         |   9 ++--
 plan/README.md            |  12 ++++--
 plan/roles/BRIEF.md       |  48 ----------------------
 plan/roles/CORRECCION.md  |  31 --------------
 plan/roles/ORQUESTADOR.md |  62 ----------------------------
 plan/roles/README.md      | 102 ++++++++++++++++++++++++----------------------
 plan/roles/REVISION.md    |  55 -------------------------
 plan/roles/WORKER.md      |  53 ------------------------
 8 files changed, 67 insertions(+), 305 deletions(-)

$ git diff --name-only main...HEAD | grep -vE "^plan/"
exit=1        # ← nada fuera de plan/: cero submodules, cero referencias al marco, cero mundos ajenos
```

### CA5 · ceguera (Eje V)

```
# patrón real usado al correr = <marco> | <términos-marco>
# (no se transcribe el literal del marco en este árbol público)
$ git diff main...HEAD | grep -niE "<marco>|<términos-marco>"
diff_exit=1   # ← 0 coincidencias en el diff

$ grep -rniE "<marco>|<términos-marco>" plan/
tree_exit=1   # ← 0 coincidencias en el árbol público plan/
```

La única cita de procedencia es el nombre versionado del paquete
(`@alephscript/skills-scriptorium@0.2.0`), permitido por el brief.

## Auto-revisión (PRACTICAS §4 — con honestidad)

- [x] Deps file:/tgz/ruta-relativa nuevas: ninguna; la referencia es por registry con versión fijada.
- [x] Referencias a codebases ajenas: ninguna; solo la cita versionada del paquete público.
- [x] Lore/tema/fuente empaquetado (gates c/d): no; se conserva la regla lore-fuera.
- [x] Nombres de transición / copy-paste: al contrario, se elimina la copia (dedup).
- [x] Candados de VISION respetados: sin cambios de diseño; solo documentación de plan.
- [x] Tests de comportamiento / SPEC actualizada: N/A (WP documental); verificación = CA2 (`npm view`).
- [x] Verificación real ejecutada: `npm view` contra el registry real, greps y `git diff` — salida literal arriba.
- [x] Commits por repo correctos: convencionales, en castellano, un repo (emmanuel-sdk).
- [x] Diff solo del alcance: solo `plan/` (CA4).

## Hallazgos fuera de alcance

- Ninguno.

## Dudas / bloqueos

- Ninguno. El registry resolvió `0.2.0` sin incidencias desde este entorno.

---

## Revisión del orquestador

_(la rellena el orquestador: aceptado ✅ / devuelto con lista numerada)_
