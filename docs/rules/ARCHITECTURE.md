# Arquitectura del proyecto

## Alcance

Este proyecto es un sitio estatico bilingue para GitHub Pages. La arquitectura debe seguir el principio de simplicidad operativa: pocos archivos, dependencias minimas, rutas predecibles y mantenimiento manual controlado.

## Principios de arquitectura

- Priorizar simplicidad sobre abstraccion.
- Mantener el sitio funcional solo con archivos estaticos.
- Evitar capas o herramientas que agreguen complejidad sin mejorar claramente el mantenimiento.
- Disenar para edicion manual directa del repositorio.
- Mantener paridad estructural entre espanol e ingles.

## Decisiones estructurales obligatorias

### 1. Arquitectura de renderizado

- El renderizado es 100% estatico.
- No se permiten SSR, SSG con framework, APIs obligatorias ni procesos de build.
- HTML, CSS y JavaScript deben poder servirse tal como estan desde GitHub Pages.

### 2. Arquitectura de archivos

- `index.html` es la entrada principal en espanol.
- `en/index.html` es la entrada principal en ingles.
- `styles.css` concentra todos los estilos compartidos.
- Los assets visuales viven en `assets/`.
- Los documentos exportables viven en `exports/` y `en/exports/`.
- La documentacion vive en `docs/`, separada por tipo: `rules/`, `cases/` y `cv/`.

### 3. Arquitectura de estilos

- Todo estilo reusable debe vivir en `styles.css`.
- No agregar estilos inline salvo casos excepcionales y justificados.
- Los tokens globales deben declararse en `:root`.
- Los componentes visuales deben reutilizar clases existentes antes de crear nuevas.

### 4. Arquitectura de comportamiento

- El JavaScript debe ser minimo, progresivo y no critico para leer el contenido.
- No se deben crear modulos JS separados mientras el comportamiento siga siendo pequeno y local.
- Si el JavaScript crece, se debe extraer a un archivo dedicado antes de duplicar logica.

### 5. Arquitectura de contenido

- La home es la fuente principal de presentacion del perfil.
- Los archivos en `docs/cases/` funcionan como documentacion extensa de casos.
- Los documentos en `docs/cv/` son piezas de apoyo, no la fuente principal del sitio.
- El contenido debe mantenerse sincronizado entre idiomas cuando represente la misma seccion del sitio.

## Limites de complejidad

- No introducir nuevas carpetas si solo van a contener un archivo.
- No dividir CSS por modulos mientras exista un unico sitio y una sola hoja de estilos sea manejable.
- No crear una capa de componentes si el HTML actual puede mantenerse con secciones claras.
- No duplicar logica, textos o recursos si pueden centralizarse sin romper la naturaleza estatica del sitio.

## Reglas de evolucion

Si el proyecto crece, la evolucion debe ser por etapas:

### Etapa 1. Sitio simple

- En raiz solo deben quedar entradas del sitio y archivos operativos minimos.
- Un solo `styles.css`.
- JS inline minimo.

### Etapa 2. Sitio estatico con mas paginas

Aplicado en este repositorio porque ya existe documentacion suficiente para separarla del codigo del sitio:

- mover JS a `assets/js/`
- mover CSS a `assets/css/`
- mantener `docs/` para documentacion extendida
- mantener URLs compatibles con GitHub Pages

### Etapa 3. Replanteamiento tecnico

Solo justificar si la cantidad de paginas, contenido o mantenimiento manual deja de ser viable:

- evaluar generador estatico o pipeline
- documentar la razon del cambio
- definir plan de migracion antes de introducir tecnologia nueva

## Reglas de consistencia

- Todo cambio estructural debe reflejarse en `README.md`.
- Toda nueva regla de mantenimiento debe reflejarse en `docs/rules/DOCUMENTATION.md` o en la politica documental vigente.
- Si cambia una ruta compartida, debe verificarse en ES y EN.
- Si cambia una seccion del sitio, debe revisarse la equivalencia de idioma y sus enlaces asociados.

## Checklist de arquitectura antes de aceptar cambios

- El cambio sigue siendo compatible con GitHub Pages sin build.
- No se agrego una capa tecnica innecesaria.
- La estructura de carpetas sigue siendo comprensible en una sola lectura.
- ES y EN siguen la misma arquitectura de navegacion.
- La documentacion del repositorio fue actualizada si hubo cambios estructurales.
