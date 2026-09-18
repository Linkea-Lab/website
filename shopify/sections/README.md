# Secciones sueltas de Shopify

Bloques autónomos (HTML + CSS + JS en un solo archivo) para pegar en una
página de producto. Todo lo editable vive arriba del archivo, entre las dos
rayas, en `{%- assign -%}`.

## kit-cierre.liquid — sección de cierre / última llamada

Cierre de la landing: promesa, ganchos de confianza, corte de envío, precio y CTA.

- **Fondo a sangre completa**: foto del producto (o URL/archivo propio) a todo el
  ancho del viewport, con desenfoque, zoom lento y velo oscuro regulable.
  El ancho exacto lo calcula el JS, así que no aparece scroll horizontal
  aunque el navegador pinte barra de scroll clásica.
- **Urgencia real**: cuenta atrás hasta la hora de corte (15:00) en horario
  Europe/Madrid. Fuera de hora avisa de que sale mañana, y viernes tarde o
  fin de semana, de que sale el lunes.
- **Precio en vivo**: escucha el evento `kit:precio` del selector de packs
  (`#kOferta`) y repinta precio, PVP tachado y porcentaje de descuento.
- **Accesibilidad**: respeta `prefers-reduced-motion`, la imagen es decorativa
  (`alt=""`) y sin JS el contenido se ve igual.

Capturas: `../cierre-desktop.png` y `../cierre-movil.png`.
