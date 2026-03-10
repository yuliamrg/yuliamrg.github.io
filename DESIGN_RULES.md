# Reglas de Diseno

Estas reglas aplican a este portafolio estatico desplegado en GitHub Pages. La prioridad no es solo que se vea bien, sino que siga siendo facil de mantener, rapido de cargar y seguro de publicar sin pipeline complejo.

## Restricciones del contexto

- El sitio se despliega como archivos estaticos en GitHub Pages.
- No debe depender de build steps, bundlers ni frameworks cliente para renderizar.
- Cualquier interaccion debe funcionar con HTML, CSS y JavaScript minimo.
- Los assets deben ser pocos y livianos para no penalizar la carga inicial.
- La version en espanol y en ingles deben mantenerse equivalentes en estructura.

## Reglas de sistema visual

- Usar arquitectura de tokens en tres niveles: primitivos, semanticos y de componente.
- Mantener los colores en variables CSS dentro de `:root`; no introducir hex sueltos salvo casos excepcionales.
- Conservar contraste minimo WCAG AA:
  - texto normal: 4.5:1
  - componentes UI: 3:1
- Usar una sola direccion visual: editorial + operativa. Evitar mezclar estilos corporativos genericos con bloques excesivamente decorativos.
- La tipografia debe seguir esta jerarquia:
  - titulares: `Fraunces`
  - interfaz y lectura: `Manrope`
- Mantener radios, sombras y espaciados consistentes con tokens globales.

## Reglas de layout

- Disenar mobile-first y luego escalar a tablet y desktop.
- El ancho de contenido no debe superar el token `--container`.
- Cada seccion principal debe vivir dentro de una superficie (`section-panel`) para dar ritmo y separacion visual.
- No usar mas de 3 columnas en desktop para grids de contenido.
- En mobile, toda CTA importante debe quedar visible sin requerir precision fina de puntero.

## Reglas de contenido

- Abrir con propuesta de valor e impacto medible, no con biografia larga.
- Cada proyecto debe comunicar en este orden: problema, solucion, impacto.
- El contenido debe reforzar el contexto donde mejor encaja el perfil: operaciones, mantenimiento, reporting y automatizacion.
- Evitar texto abstracto o claims vagos sin evidencia.
- El tono debe ser profesional y concreto; no usar lenguaje inflado.

## Reglas de interaccion

- Toda navegacion nueva debe ser accesible por teclado.
- Los estados de foco deben ser visibles y no depender del navegador por defecto.
- Si se agrega JS, debe ser progresivo:
  - el contenido base debe seguir accesible sin JS
  - el JS solo mejora navegacion o experiencia, no desbloquea contenido esencial
- Evitar carruseles, sliders y animaciones decorativas pesadas.
- Respetar `prefers-reduced-motion`.

## Reglas para GitHub Pages

- No introducir dependencias de servidor, SSR ni rutas que asuman reescrituras.
- Mantener links relativos correctos entre `/` y `/en/`.
- Si se agregan recursos nuevos, verificar que funcionen desde rutas estaticas.
- No depender de APIs externas para renderizado critico.
- Cualquier formulario futuro debe resolverse con servicios externos compatibles con sitio estatico o mediante enlaces directos.

## Regla de calidad antes de publicar

- Verificar version ES y EN.
- Verificar responsive en 320px, 768px y 1280px.
- Verificar navegacion con teclado.
- Verificar que los enlaces externos usen `target="_blank"` con `rel="noopener"` cuando aplique.
- Verificar que la home siga cargando sin errores con solo archivos estaticos.
