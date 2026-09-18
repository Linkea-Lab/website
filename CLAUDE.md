# CLAUDE.md

Reglas de trabajo para este repositorio. Escritas a partir de errores reales
cometidos en sesiones anteriores, no de buenas intenciones.

## Contexto

Repositorio de trabajo de **Bazar Bizarro**, tienda Shopify de dropshipping en
España. Propietario: perfil Agile, ex Product Manager, busca proyectos rentables
con inversión mínima. Espera respuestas directas, con fuentes, sin relleno, y
prefiere una verdad incómoda a una respuesta cómoda.

Proyecto activo: `bazar-bizarro/auragalaxy/` — ficha de producto del proyector
AuraGalaxy. Ver `bazar-bizarro/auragalaxy/DECISIONES.md`.

## Reglas de verificación

1. **Lee la fuente antes de opinar sobre ella.** Si existe una URL, un CSS, un
   HTML o una API a la que se puede acceder, se accede. Diseñar "al estilo de"
   un competidor cuando su hoja de estilos es pública y descargable costó tres
   rondas de correcciones en la sesión del 18/09/2026.
   `curl -s <url> -o fichero` y luego `grep` sobre el CSS real.
2. **No afirmes que algo está en una web si no lo has visto renderizado.**
   Extraer texto del HTML no prueba que sea visible: puede ser un carrusel, un
   bloque oculto o un `display:none`.
3. **Un fallo propio no es un bloqueo del sistema.** Antes de decir "no puedo",
   reintentar con otra vía y enseñar el error exacto. La escritura de SEO en
   Shopify se dio por bloqueada durante días: el problema era usar
   `productUpdate(input:)`, deprecado en favor de `productUpdate(product:)`
   con `ProductUpdateInput`.
4. **Datos de producto: nunca los del proveedor sin verificar.** Peso, número de
   sonidos, combinaciones de color. Si hay conflicto entre dos fuentes, se marca
   el hueco y se pide medir la unidad real. Un dato falso publicado es una
   reseña de una estrella garantizada.

## Reglas de entrega

5. **Lo que solo vive en el scratchpad, no existe.** El contenedor se recicla.
   Todo entregable (Liquid, HTML, textos) se commitea en este repositorio además
   de publicarse como artefacto.
6. **Cada archivo Liquid es autocontenido.** Sin archivo base compartido: cada
   bloque lleva su propio `<style>`, porque en Shopify un bloque puede ir solo.
   Zona de edición al principio, entre dos rayas, con colores, textos, imágenes
   y vídeos juntos. Sin comentarios de relleno.
7. **Al crear una variante, no se pisa la anterior.** Sufijo `b` en el nombre
   (`B07` → `B07b`) y archivo nuevo.
8. **Regenerar índice y zip tras tocar cualquier `.liquid`.** Si no, el índice
   sirve código viejo.

## Restricciones técnicas de los bloques Liquid

- **Prohibido:** `color-mix()`, `:has()`, anidación CSS nativa, `let`, `const`,
  funciones flecha. Máxima compatibilidad de navegadores.
- **Permitido:** `clamp()`, `aspect-ratio`, `gap`, `:focus-visible`,
  `env(safe-area-inset-*)`, `object-fit`, prefijos `-webkit-`.
- **Especificidad:** el tema Horizon pisa los selectores de una sola clase.
  Encadenar dos o tres (`.k-of .k-of-lista .k-of-rnom`). Nunca `!important`.
- **Fuente:** Nunito variable autoalojada desde `theme.liquid`. Los bloques
  llevan `CARGAR_FUENTE = false`.
- **CSS del tema:** límite de 1.500 caracteres a nivel tema y 500 por sección,
  sin `@import`, URLs solo desde `cdn.shopify.com`.

## Comunicación

9. **Tutear, con humor, sin adular.** Si una idea del propietario es peor que la
   alternativa, se dice y se argumenta. Él decide después.
10. **Citar la fuente de cada dato.** Necesita poder explicarlo a terceros.
11. **No invocar normativa legal al diseñar precios o devoluciones.** Petición
    expresa suya. Se diseña con criterio comercial; el riesgo legal lo asume él.

## Mejora continua

12. **Cerrar el ciclo antes de terminar la sesión.** Toda decisión de producto,
    precio, copy o diseño que se tome en una sesión se añade a
    `bazar-bizarro/auragalaxy/DECISIONES.md` antes de cerrarla, con su porqué en
    una línea. Todo error propio del que salga una regla se añade a este
    archivo. Se hace sin esperar a que el propietario lo pida: una retro cuyas
    acciones no se escriben no ha ocurrido.
13. **Este archivo es solo para lo que hay que saber siempre.** Lo que hay que
    consultar cuando toca va en el archivo del proyecto y se enlaza desde aquí.
    Si esto crece sin límite, se come el contexto de cada sesión y deja de
    leerse.
