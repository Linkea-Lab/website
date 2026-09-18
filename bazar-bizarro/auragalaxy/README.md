# AuraGalaxy · ficha de producto

Kit de bloques y secciones Liquid para la ficha del proyector AuraGalaxy en
Shopify (tema Horizon), más las maquetas de trabajo y los textos.

## Qué hay aquí

```
bloques/     11 bloques para la columna derecha del producto
secciones/   13 secciones a ancho completo
maquetas/    maqueta-A.html y maqueta-B.html — para ver el conjunto en el navegador
shopify/     descripcion-auragalaxy.html — pegar en el editor <> de la descripción
guia-20-formas.html   guía regalo que se desbloquea con el pack de 3
DECISIONES.md         por qué cada cosa es como es
```

## Orden de montaje en la ficha

**Columna derecha**, de arriba abajo:

```
B01   título (H1 desde product.title)
B01b  frase de descripción SEO
B02   valoración Trustpilot en una línea
B01c  popup "¿se ve así de verdad?"
B03   tres tarjetas con icono
B04   pregunta: ¿cuántas habitaciones?
B05   recuadro de precio + regalos
B06   en stock + fecha de entrega
      ← aquí va el botón del plugin de contra reembolso
B06b  caja azul de tranquilidad
B07b  tres dudas desplegables
```

**Bajo la galería:** `B00b` (reseña rotativa).
`B00` y `B07` son las variantes anteriores, más sobrias. Se conservan.

**Secciones**, en orden: S01 → S13.

## Cómo se edita un bloque

Cada archivo es independiente y lleva su propio CSS. Todo lo editable está
entre las dos rayas del principio:

```
{%- comment -%} ═══════ EDITA AQUÍ ═══════ {%- endcomment -%}
...colores, textos, imágenes, vídeos...
{%- comment -%} ══════ FIN · NO TOQUES NADA MÁS ABAJO ══════ {%- endcomment -%}
```

Las listas van en una sola variable, con `|` entre campos y `~` entre elementos.

## Comunicación entre bloques

`B04` emite `kit:cantidad` → `B05` emite `kit:precio` → lo consumen `S12` y `S13`.
Si falta alguno, los demás siguen funcionando.

## Antes de publicar

- [ ] Sustituir los huecos grises por los vídeos y fotos reales
- [ ] Rellenar o borrar el peso y el número de sonidos (ver DECISIONES.md)
- [ ] Pegar `shopify/descripcion-auragalaxy.html` en la descripción del producto
- [ ] Abrir el perfil de Trustpilot y poner el enlace en `B02` y `B00b`
- [ ] Crear la playlist de Spotify del regalo
