# plan/roles — protocolo del swarm (emmanuel-sdk)

El protocolo de swarm (orquestador / worker / revisión / corrección / brief y
la plantilla de reporte) **ya no se copia aquí**: es genérico, vive publicado
y versionado, y este mundo lo **referencia**. En `plan/roles/` solo queda la
**calibración local** de emmanuel: lo propio de este mundo que el protocolo
genérico no fija.

## Protocolo canónico (referencia versionada)

| dato | valor |
| ---- | ----- |
| paquete | `@alephscript/skills-scriptorium` |
| versión | **`0.2.0`** (fijada; nunca `latest`) |
| skill | `skills/swarm-orquestacion` (SKILL.md + `reference/roles/`) |
| registry | `https://npm.scriptorium.escrivivir.co` |

Consulta / instalación (resoluble por registry, sin copiar los prompts):

```bash
# comprobar que la versión fijada existe
npm view @alephscript/skills-scriptorium@0.2.0 \
  --registry=https://npm.scriptorium.escrivivir.co version

# traer el paquete a un runner
npm install @alephscript/skills-scriptorium@0.2.0 \
  --registry=https://npm.scriptorium.escrivivir.co
```

Los prompts de rol (ORQUESTADOR, WORKER, REVISION, CORRECCION, BRIEF, README)
y la plantilla de reporte son los de `skills/swarm-orquestacion/reference/`
del paquete en la versión fijada. Un runner los consume tal cual desde el
paquete; este árbol no los duplica.

## Calibración local de emmanuel (delta sobre el canónico)

Lo que el protocolo genérico NO fija y este mundo sí. Queda visible aquí sin
abrir el paquete:

### 1. Multi-repo por submodules (PRACTICAS §2, DE-1)

El genérico asume «un repo = el mundo». Este mundo monta las piezas como
submodules (cada una su repo git propio), así que un WP puede tocar el
superproyecto **y/o N submodules**:

- El brief **declara los repos tocados**; rama `wp/<id>-<slug>` en CADA repo
  tocado.
- El reporte lista commits **por repo**.
- El **bump del puntero de submodule** en el superproyecto lo hace el
  orquestador al aceptar (✅) — nunca el worker a medias.
- Un WP no deja un submodule en rama sin reportar: o se entrega o se revierte.
- Prohibido trabajar una pieza dentro del checkout de otro mundo: se trabaja
  en el submodule de ESTE superproyecto.

### 2. El motor no trae lore (PRACTICAS §1.5, DE-3)

Ni temas, ni líneas, ni la fuente empaquetados. El contenido entra solo por
la puerta pública del contrato (satélites a ediciones remotas con autoridad);
cero texto de la fuente en el repo. Empaquetar lore = devolución (gates c/d).

## Dónde vive el estado (recordatorio local)

- **`plan/BACKLOG.md` es del orquestador y vive en main.** 🔶 al asignar,
  ✅ al aceptar. El worker no lo edita nunca.
- **El reporte vive en la rama del WP** (`plan/REPORTES/WP-….md`): nombre
  único = sin conflictos; llega a main con el merge.
- **`plan/DECISIONES.md` §abiertas es del custodio.**

## Primer lote sugerido (Ola E0)

WP-E00 (gates) y WP-E01 (SPEC del contrato) — paralelizables. E01 es el
corazón del sound system: conviene un worker con criterio, no el más rápido.
