# Portafolio estático de Yuliam Rivera

Sitio personal bilingüe desplegado en GitHub Pages para presentar perfil profesional, experiencia, proyectos y CV en español e inglés.

## Objetivo del proyecto

El repositorio contiene una implementación estática, sin build ni dependencias de servidor. La prioridad es mantener una publicación simple, rápida y fácil de editar.

## Reglas del repositorio

- [docs/rules/ARCHITECTURE.md](./docs/rules/ARCHITECTURE.md): reglas de arquitectura, limites de complejidad y evolucion permitida.
- [docs/rules/DOCUMENTATION.md](./docs/rules/DOCUMENTATION.md): organizacion documental y criterios de actualizacion.
- [docs/rules/DESIGN_RULES.md](./docs/rules/DESIGN_RULES.md): reglas visuales, de contenido, accesibilidad y publicacion.
- [docs/rules/GIT_WORKFLOW.md](./docs/rules/GIT_WORKFLOW.md): flujo Git basico para cambios pequenos y publicacion ordenada.

## Stack

- HTML estático
- CSS global
- JavaScript mínimo inline para navegación móvil
- Assets locales y documentos exportados en PDF

## Estructura del repositorio

```text
/
|-- index.html                     # Home en español
|-- en/
|   `-- index.html                 # Home en inglés
|-- styles.css                     # Estilos compartidos ES/EN
|-- assets/
|   `-- profile.png                # Foto de perfil
|-- exports/
|   `-- cv_data_analytics.pdf      # CV en español
|-- en/exports/
|   `-- cv_data_analytics_en.pdf   # CV en inglés
|-- docs/
|   |-- rules/
|   |   |-- ARCHITECTURE.md        # Reglas de arquitectura del sitio
|   |   |-- DOCUMENTATION.md       # Politica de organizacion documental
|   |   |-- DESIGN_RULES.md        # Reglas visuales, de contenido y publicacion
|   |   `-- GIT_WORKFLOW.md        # Reglas basicas para trabajo con Git
|   |-- cases/
|   |   |-- invoice-automation.md  # Caso de automatizacion de facturas
|   |   `-- maintenance-indicators.md
|   |-- cv/
|   |   |-- cv_data_analytics_en.md
|   |   `-- cv_data_analytics_en.html
`-- README.md                      # Entrada general del repositorio
```

## Qué documenta cada archivo

- `index.html`: propuesta de valor, experiencia, proyectos, stack, formación y contacto en español.
- `en/index.html`: equivalente funcional de la home en inglés.
- `styles.css`: sistema visual compartido entre ambas versiones.
- `docs/rules/ARCHITECTURE.md`: limites tecnicos y reglas estructurales del proyecto.
- `docs/rules/DOCUMENTATION.md`: criterios para crear, ubicar y actualizar documentacion.
- `docs/rules/DESIGN_RULES.md`: criterios de diseño, contenido, accesibilidad y publicacion.
- `docs/rules/GIT_WORKFLOW.md`: reglas minimas para revisar, committear y publicar cambios.
- `docs/cases/invoice-automation.md`: documentacion extensa del caso de automatizacion de facturas con Apps Script, AppSheet y Looker Studio.
- `docs/cases/maintenance-indicators.md`: documentacion extensa del caso de pipeline analitico para indicadores de mantenimiento.
- `docs/cv/cv_data_analytics_en.md`: version editable del CV en ingles.
- `docs/cv/cv_data_analytics_en.html`: version HTML lista para exportar o revisar visualmente.

## Flujo de mantenimiento

### 1. Actualizar contenido principal

Si cambia el perfil, experiencia, proyectos o contacto:

- editar `index.html`
- replicar el cambio correspondiente en `en/index.html`
- verificar que los enlaces entre `/` y `/en/` sigan correctos

### 2. Actualizar documentos de apoyo

Si cambia el CV o la descripción de proyectos:

- actualizar los archivos `.md` asociados
- regenerar o reemplazar los PDF exportados en `exports/` y `en/exports/` cuando aplique
- comprobar que los botones "Abrir CV" y "Open CV" apunten al archivo correcto

### 3. Revisar consistencia visual

Después de cualquier cambio:

- revisar mobile, tablet y desktop
- validar contraste y estados de foco
- confirmar que ES y EN conserven la misma estructura

## Vista local

Como es un sitio estático, puede abrirse directamente en navegador. Si se prefiere una previsualización por servidor local:

```powershell
python -m http.server 8000
```

Luego abrir `http://localhost:8000`.

## Checklist antes de publicar

- La home en español carga sin errores.
- La home en inglés carga sin errores.
- Los links de idioma funcionan en ambos sentidos.
- Los PDFs del CV abren correctamente.
- Los enlaces externos usan `target="_blank"` y `rel="noopener"` cuando aplica.
- La navegación móvil abre y cierra correctamente.
- No se rompió la paridad de contenido entre ES y EN.

## Notas de mantenimiento

- Mantener la solución sin bundlers ni frameworks salvo que exista una necesidad real.
- Evitar duplicar estilos inline; centralizar cambios en `styles.css`.
- Mantener textos concretos y orientados a impacto.
- Si se agregan nuevos assets, usar rutas relativas compatibles con GitHub Pages.
- Si cambia la estructura del repositorio, actualizar `README.md` y los archivos bajo `docs/rules/`.
