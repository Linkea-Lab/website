# AuraGalaxy · registro de decisiones

Producto: `gid://shopify/Product/16327347568975` · SKU `PROYECTOR HUEVO-24476`
Última actualización: 2026-09-18

---

## Producto y marca

| # | Decisión | Por qué | Estado |
|---|---|---|---|
| 1 | El producto se llama **AuraGalaxy**, con **™** justo tras la palabra | Construir marca sobre un producto genérico que venden veinte tiendas más. ™ y no ® porque no hay registro; la ® sin registro es infracción en España | Aplicado |
| 2 | Título: *AuraGalaxy. Tu habitación es una galaxia en 3 segundos* | Promete resultado y tiempo, no características | Escrito en Shopify |
| 3 | La forma se llama **huevo de dragón**, nunca "huevo de dinosaurio" | Un solo nombre en toda la ficha. Dragón vende mejor para público mixto adulto/infantil | Aplicado en textos nuevos |
| 4 | "huevo" en minúscula se mantiene en los textos | Es la forma del producto y lo que la gente busca en Google. Quitarlo cuesta tráfico | Aplicado |

## Precio y oferta

| # | Decisión | Por qué | Estado |
|---|---|---|---|
| 5 | Escalera 1→39,90 € · 2→69,90 € · 3→94,90 € sobre PVP 49,90 € | 39,90 es puerta de entrada, 69,90 el protagonista, 94,90 para quien quiere tres | En `B05-recuadro.liquid` |
| 6 | Máximo 3 unidades, no 5 | Casi nadie tiene cuatro habitaciones y las usa todas | Aplicado |
| 7 | Envío gratis en todos los pedidos | No condicionar el beneficio básico | Aplicado |
| 8 | Regalos digitales: playlist de Spotify desde 2 uds, guía PDF desde 3 | Coste marginal cero, valor percibido alto, y específicos del producto en lugar de genéricos | Aplicado |
| 9 | **Sin contador ni "oferta limitada a hoy"** | El precio no cambia mañana. Una urgencia falsa contamina la urgencia real (envío 24-48 h, pago al recibir). La variable `AVISO` existe pero va vacía | Decidido en contra de la petición inicial |

## Confianza y devoluciones

| # | Decisión | Por qué | Estado |
|---|---|---|---|
| 10 | No se menciona plazo de devolución de 14 días ni garantía de 3 años | Petición expresa del propietario | Aplicado |
| 11 | Se promete: pago al repartidor, pasarela cifrada, y hacerse cargo si llega dañado o con fallo de fábrica | Es lo que realmente ofrece el proveedor | Aplicado |
| 12 | **Eliminada** la nota "algunos productos no tienen garantía por estar en oferta" | Estaba publicada y contradecía todo el discurso de riesgo cero. Munición para una reclamación | Pendiente de pegar la descripción nueva |
| 13 | No se nombra ninguna pasarela concreta | Cobra con tarjeta normal, no con Redsys | Aplicado |

## Arquitectura de la ficha

| # | Decisión | Por qué | Estado |
|---|---|---|---|
| 14 | 26 archivos Liquid autocontenidos, no un bloque base compartido | En Shopify un bloque puede renderizarse aislado | Aplicado |
| 15 | Botón de contra reembolso **fuera** del recuadro de precios | Es un plugin y no se puede meter dentro | Aplicado |
| 16 | Escenas de uso en rejilla 3+3, sin párrafo descriptivo | Van vídeos cortos verticales. El titular dice el *cuándo*, el vídeo el *qué*, y la línea de ajustes (`Azul · lluvia · 1 hora`) deja algo de texto para SEO | `S04-escenas.liquid` |
| 17 | Reseña rotativa bajo la galería + 3 dudas desplegables bajo el botón | Copiado de Bonjour: todo lo decisivo sin hacer scroll | `B00b` y `B07b` |
| 18 | Reseñas largas, no cortas, y cada una empieza con una duda que resuelve | Parece escrita por una persona. Patrón verificado en el testimonio de Bonjour | `B00b` y `S09` |

## Vídeo

| # | Decisión | Por qué | Estado |
|---|---|---|---|
| 19 | Los vídeos se exportan **siempre en 9:16**, nunca en el formato de la caja | El recorte lo hace el navegador con `object-fit:cover`. Exportar recortado pierde píxeles de verdad en lugar de solo ocultarlos | Aplicado |
| 20 | Proporción de caja **3:4**, no 4:5 ni 9:16 | 3:4 recorta el 25 % frente al 30 % de 4:5. 9:16 no recorta nada pero deja tres vídeos de 658 px de alto en fila, un muro que obliga a hacer scroll para ver una sola fila | Aplicado en `trio-videos` y `S04` |
| 21 | El recorte se come **todo por abajo** (`object-position: center top`) | Lo que vende es el techo proyectado, que está en la parte alta del encuadre. Recortar por el centro se comía el 15 % superior | Aplicado |
| 22 | El encuadre se elige **por vídeo**, no global | Cada plano pide una cosa: el techo pide arriba, unas manos piden centro, un texto quemado pide abajo. Un ajuste único obliga a estropear dos de cada tres | `crop_1..3` en `trio-videos` |
| 23 | SEO title y description escritos vía API | 58 y 138 caracteres, por debajo del corte de Google. El title lleva la marca delante y las palabras que se teclean detrás; la description promete resultado y mete envió rápido y pago al recibir en el propio snippet | Escrito en Shopify |

## Medidas copiadas del CSS real de Bonjour

Descargadas de `custom.css` y `enfant-new.css` de su tema (no inventadas).

```
.pgallery_review_block   border:6px solid <pastel>; border-radius:16px; padding:24px; margin:24px 0 0
  estrellas              96px de ancho las cinco → 18px cada una
  texto                  font-weight:400; line-height:140%
  nombre 16px/700 · verificado 14px/500 con check verde #02b978

.cppanel-block_accordion border:1px solid #000; border-radius:16px; padding:0 16px
  heading                padding-block:16px; h5 15-16px/600
  separación             margin-top:12px entre cajas
  icono                  círculo con + de 24px, stroke-width:2, pasa a − al abrir
  abierta                box-shadow:3px 3px <color>
  cuerpo                 14px, line-height:180%
```

---

## Datos en conflicto · SIN RESOLVER

No publicar ninguno de estos hasta medir la unidad real.

| Dato | Fuente A | Fuente B |
|---|---|---|
| Peso | 490 g (HTML de la ficha) | 558 g (proveedor Dropi) |
| Sonidos de ambiente | 19 (HTML de la ficha) | 11 (imagen de Zibblo) |
| Combinaciones de aurora | 14 | sin fuente |

En `shopify/descripcion-auragalaxy.html` van como `XXX`. Borrar esas líneas o
rellenarlas, nunca publicarlas con el dato del proveedor sin comprobar.

## Competencia

- **Zibblo** vende el mismo producto a 59,95 $ con ficha de tema por defecto,
  sin secciones propias. La ventaja de Bazar Bizarro es la ficha, no el producto.
- **Bonjour Drink** (`es.bonjourdrink.co/pages/enfant-first-order`) es la
  referencia de arquitectura, no de producto.
