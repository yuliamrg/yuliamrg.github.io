# Organizacion documental

## Objetivo

Definir como se documenta este repositorio para que la informacion sea facil de encontrar, mantener y actualizar sin duplicaciones inutiles.

## Principios

- Cada documento debe tener un proposito claro.
- Cada documento debe tener un responsable implicito de actualizacion: quien modifica la funcionalidad relacionada debe actualizar su documentacion.
- No crear documentos por intuicion; solo si resuelven una necesidad concreta.
- Evitar duplicar la misma explicacion en varios archivos.
- Mantener la documentacion corta, especifica y alineada con el estado real del repositorio.

## Mapa documental actual

- `README.md`: vista general del proyecto, estructura, mantenimiento y checklist de publicacion.
- `docs/rules/ARCHITECTURE.md`: reglas de arquitectura y limites de complejidad.
- `docs/rules/DOCUMENTATION.md`: politica de documentacion y ubicacion de cada tipo de contenido.
- `docs/rules/DESIGN_RULES.md`: reglas visuales, de contenido, accesibilidad y publicacion.
- `docs/rules/GIT_WORKFLOW.md`: flujo Git basico para mantenimiento del repositorio.
- `docs/cases/invoice-automation.md`: caso documentado de automatizacion de facturas.
- `docs/cases/maintenance-indicators.md`: caso documentado de indicadores de mantenimiento.
- `docs/cv/cv_data_analytics_en.md`: fuente textual editable del CV en ingles.
- `docs/cv/cv_data_analytics_en.html`: version HTML del CV en ingles.

## Reglas de organizacion

### 1. README

- Debe explicar que es el proyecto y como esta organizado.
- Debe enlazar a las reglas de arquitectura, documentacion y diseno.
- No debe contener detalle excesivo de decisiones tecnicas internas.

### 2. Documentos normativos

Son los archivos que definen reglas del repositorio:

- `docs/rules/ARCHITECTURE.md`
- `docs/rules/DOCUMENTATION.md`
- `docs/rules/DESIGN_RULES.md`
- `docs/rules/GIT_WORKFLOW.md`

Reglas:

- deben mantenerse breves y accionables
- no deben contradecirse entre si
- si una regla cambia, actualizar la referencia cruzada cuando aplique

### 3. Documentos de caso

Son documentos que explican proyectos o piezas del portafolio:

- deben describir contexto, problema, solucion e impacto
- deben evitar placeholders inexistentes
- deben enlazar solo recursos reales
- deben actualizarse si cambia el caso mostrado en la home

### 4. Documentos derivados

Son archivos exportados o de presentacion paralela:

- HTML exportado
- PDF

Reglas:

- deben tener una fuente editable identificable
- no deben considerarse la unica fuente de verdad
- si se regeneran, verificar enlaces y rutas despues del cambio

## Cuando actualizar la documentacion

- Si cambia la estructura de carpetas: actualizar `README.md` y `docs/rules/ARCHITECTURE.md`.
- Si cambia el criterio de mantenimiento: actualizar `docs/rules/DOCUMENTATION.md`.
- Si cambia el sistema visual o contenido editorial: actualizar `docs/rules/DESIGN_RULES.md`.
- Si cambia un proyecto del portafolio: actualizar el `.md` del caso correspondiente y la home afectada.
- Si cambia un archivo exportado: validar tambien el documento fuente y los enlaces a ese export.

## Reglas de calidad documental

- No dejar secciones vacias.
- No dejar enlaces rotos o referencias a archivos inexistentes.
- No mezclar borradores con documentacion estable sin marcarlo explicitamente.
- Escribir titulos claros y consistentes.
- Usar terminologia estable: proyecto, caso, export, home, version ES, version EN.

## Criterio para crear nuevos documentos

Crear un documento nuevo solo si cumple al menos una de estas condiciones:

- define una regla transversal del repositorio
- documenta un caso del portafolio con suficiente entidad propia
- evita sobrecargar el `README.md`
- reduce ambiguedad real de mantenimiento

Si no cumple esto, agregar la informacion al documento existente mas cercano.
