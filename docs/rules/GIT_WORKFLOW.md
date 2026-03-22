# Flujo Git basico

## Objetivo

Definir un flujo Git simple, suficiente para este repositorio estatico, sin imponer ceremonias innecesarias.

## Principios

- Hacer cambios pequenos y trazables.
- No mezclar en un mismo commit cambios visuales, estructurales y documentales si pueden separarse con claridad.
- Antes de subir cambios, verificar que el sitio siga consistente en ES y EN.
- Si un cambio modifica estructura o contenido, actualizar la documentacion relacionada en el mismo trabajo.

## Reglas basicas

### 1. Antes de empezar

- Revisar `git status`.
- Entender si hay cambios locales sin terminar antes de editar.
- No sobrescribir trabajo previo sin revisarlo.

### 2. Alcance por cambio

- Un cambio debe tener un objetivo claro.
- Evitar commits gigantes con multiples temas no relacionados.
- Si hay una reorganizacion de carpetas, separar ese trabajo de cambios visuales cuando sea posible.

### 3. Commits

- Escribir mensajes concretos y cortos.
- Describir el resultado, no el esfuerzo.
- Preferir mensajes como:
  - `docs: reorganiza documentacion en docs/`
  - `site: ajusta enlaces del CV en ES y EN`
  - `styles: mejora responsive del hero`

### 4. Verificaciones minimas antes de commit

- `git diff` fue revisado.
- `index.html` y `en/index.html` siguen consistentes si el cambio afecta contenido o rutas.
- Los archivos movidos o renombrados siguen referenciados correctamente.
- Si hubo cambio estructural, `README.md` y documentos en `docs/rules/` fueron revisados.

### 5. Pull, merge y sincronizacion

- Hacer `pull` antes de subir si el remoto pudo cambiar.
- Resolver conflictos con criterio, no aceptando cambios a ciegas.
- Si hay conflicto en documentacion, preservar la version que refleje el estado real actual del repo.

### 6. Que evitar

- No hacer `git add .` sin revisar.
- No hacer commits con archivos temporales, exportes accidentales o basura local.
- No reordenar archivos solo por preferencia personal sin actualizar la documentacion.
- No mezclar cambios personales del contenido con refactors estructurales sin dejar trazabilidad clara.

## Flujo sugerido

```powershell
git status
git diff
git add <archivos>
git commit -m "docs: actualiza estructura documental"
git pull --rebase
git push
```

## Regla de publicacion

Todo cambio que afecte navegacion, rutas, documentos exportados o estructura del repositorio debe revisarse pensando en GitHub Pages antes de hacer push.
