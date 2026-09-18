# Técnico · Shopify y Liquid

Leer cuando se vaya a escribir o tocar código: bloques Liquid, CSS, JavaScript,
tema, o la API de Shopify.

## Cómo se escriben los bloques

- **Cada archivo es autocontenido.** Sin archivo base compartido: cada bloque
  lleva su propio `<style>`, porque en Shopify un bloque puede renderizarse
  aislado.
- **Zona de edición al principio**, entre dos rayas, con colores, textos,
  imágenes y vídeos juntos. Sin comentarios de relleno.
- **Las listas van en una sola variable**, con `|` entre campos y `~` entre
  elementos.
- **Al crear una variante no se pisa la anterior.** Sufijo `b` en el nombre
  (`B07` → `B07b`) y archivo nuevo.
- **Tras tocar cualquier `.liquid`, regenerar índice y zip**, o el índice sirve
  código viejo.

## Compatibilidad de navegadores

- **Prohibido:** `color-mix()`, `:has()`, anidación CSS nativa, `let`, `const`,
  funciones flecha.
- **Permitido:** `clamp()`, `aspect-ratio`, `gap`, `:focus-visible`,
  `env(safe-area-inset-*)`, `object-fit`, prefijos `-webkit-`.

## Trampas conocidas del tema Horizon

- **Especificidad:** pisa los selectores de una sola clase. Encadenar dos o tres
  (`.k-of .k-of-lista .k-of-rnom`). Nunca `!important`.
- **Fuente:** Nunito variable autoalojada desde `theme.liquid`. Los bloques van
  con `CARGAR_FUENTE = false`.
- **CSS del tema:** 1.500 caracteres a nivel tema y 500 por sección, sin
  `@import`, URLs solo desde `cdn.shopify.com`.

## Vídeo vertical en cajas anchas

Los vídeos se exportan siempre en 9:16. El recorte lo hace el navegador con
`object-fit: cover`, y `object-position` decide por dónde. Exportar ya recortado
pierde píxeles de verdad en lugar de solo ocultarlos.

| Caja | Visible de un 9:16 | Recorte |
|---|---|---|
| 16/9 | 32 % | 68 % |
| 1/1 | 56 % | 44 % |
| 4/5 | 70 % | 30 % |
| 3/4 | 75 % | 25 % |
| 9/16 | 100 % | 0 % |

## API de Shopify

- `productUpdate(input:)` está **deprecado**. Usar
  `productUpdate(product: $product)` con `ProductUpdateInput`.
- Antes de cualquier mutación: `graphql_schema` → construir →
  `validate_graphql_codeblocks` → ejecutar.
