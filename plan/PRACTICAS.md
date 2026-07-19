# PRACTICAS — lectura obligatoria antes de tocar código

Estas prácticas son la **calibración local** de emmanuel-sdk sobre el
protocolo del swarm, que vive referenciado versionado en
`@alephscript/skills-scriptorium@0.2.0 › skills/swarm-orquestacion` (registry
`npm.scriptorium.escrivivir.co`, resoluble por `npm view` — C8; ver
`plan/roles/README.md`). Son autocontenidas vía esa referencia, no vía copia.
Son la lista de cosas por las que un WP **se devuelve**.

## 1. Reglas duras

1. **Registry-first.** Dependencias: por el registry
   (`npm.scriptorium.escrivivir.co`), con semver. Prohibido `file:`,
   tarballs `.tgz` committeados y rutas relativas a otras codebases. Lo que
   las piezas ofrezcan se instala; lo que este mundo produzca y merezca
   compartirse, se publica.
2. **Ni tocar ni nombrar codebases ajenas.** zeus-sdk se relee como
   procedencia (VISION §contrato), jamás se modifica ni se le introducen
   referencias a este mundo. Las piezas (Document/Vector Machine,
   cartógrafo) se trabajan en **sus repos propios**, nunca dentro del
   checkout de otro mundo.
3. **Sin nombres de transición.** `legacy`, `v2`, `-old`, `-new`, aliases de
   compatibilidad: prohibidos. Lo sustituido se demuele o archiva en el
   mismo WP.
4. **Reutiliza o publica, nunca copies.** Copy-paste desde otro repo =
   devolución. Si algo merece compartirse, se publica al registry con
   nombre y versión.
5. **El motor no trae lore (DE-3).** Ni temas, ni líneas, ni la fuente
   empaquetados. La fuente entra solo como línea del custodio por la puerta
   pública: satélites a ediciones remotas con autoridad, cero texto en el
   repo.
6. **Candados de VISION en todo diseño.** Sin admin-override; epoché (el
   colapso es de la persona); la nave abre dossiers, no los genera.
7. **Files-first.** El estado duradero son archivos; objetos pesados
   inmutables y direccionables. P2P/IPFS = pinnear y anotar, no migrar.
8. **Tests y specs en el mismo WP.** Lo nuevo llega con tests; si toca el
   contrato de alimentación, con SPEC actualizada.
9. **Commits convencionales**: `tipo(alcance): resumen`
   (`feat|fix|refactor|test|docs|chore`). Rupturas: `!` o
   `BREAKING CHANGE:`.

## 2. Submodules

El superproyecto monta las piezas como submodules (DE-1): cada una sigue
siendo su repo, con vida git propia.

- El brief de cada WP **declara qué repos toca** (superproyecto y/o
  submodules concretos).
- Rama `wp/<id>-<slug>` **en cada repo tocado**; el reporte lista commits
  POR repo.
- El **bump del puntero** de submodule en el superproyecto lo hace el
  orquestador al aceptar (✅), nunca el worker a medias.
- Un WP no deja un submodule en rama sin reportar: o se entrega o se
  revierte.
- Prohibido trabajar una pieza dentro del checkout de otro mundo: se
  trabaja en el submodule de ESTE superproyecto.

## 3. Alcance

El WP, todo el WP y solo el WP. Hallazgos → §hallazgos del reporte, no fixes
de pasada. WP mal especificado → parar y reportar, no reinterpretar.

## 4. Auto-revisión obligatoria

Al terminar, PARA. Relee el diff completo (por repo) contra este checklist y
corrige antes de reportar; luego rellénalo con honestidad en el reporte:

- [ ] ¿Dependencias `file:`/tgz/ruta-relativa nuevas? ¿Algo debía publicarse?
- [ ] ¿Referencia por ruta a zeus-sdk u otra codebase ajena?
- [ ] ¿Lore, tema o texto de la fuente empaquetado (gates c/d)?
- [ ] ¿Nombres de transición o copy-paste?
- [ ] ¿Algún diseño rompe un candado (admin-override, colapso ajeno, nave
      que genera)?
- [ ] ¿Tests prueban comportamiento? ¿SPEC actualizada si tocó el contrato?
- [ ] ¿Verificación real (validador/arranque ejecutado, no solo leído)?
- [ ] ¿Commits convencionales y por-repo correctos?
- [ ] ¿El diff contiene solo el alcance del WP?

Regla de evidencia: **no inventes observaciones**. Salida literal o
`⏳ sin verificar`.

## 5. Reporte

Desde [REPORTES/PLANTILLA.md](REPORTES/PLANTILLA.md) a
`REPORTES/WP-<id>-<slug>.md`. Sin reporte con evidencia y auto-revisión, no
hay revisión.
