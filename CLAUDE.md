# CLAUDE.md · índice

Esto es un enrutador, no un manual. Se lee entero al empezar porque es corto.
El detalle vive en archivos separados que se leen **solo cuando el tema lo pide**.

## Contexto en tres líneas

**Bazar Bizarro**, tienda Shopify de dropshipping en España, tema Horizon.
La lleva Álvaro: perfil Agile, ex Product Manager, busca rentabilidad desde el
minuto uno con inversión mínima. Proyecto activo: la ficha del proyector
**AuraGalaxy**.

## Dónde está cada cosa

| Si se habla de… | Leer |
|---|---|
| Modelo de negocio, proveedores, productos, competencia, qué lanzar | `contexto/negocio.md` |
| Copy, precios, ofertas, regalos, reseñas, SEO, estructura de ficha | `contexto/marketing.md` |
| Escribir o tocar código: Liquid, CSS, JS, tema, API de Shopify | `contexto/tecnico-shopify.md` |
| El proyector AuraGalaxy en concreto | `bazar-bizarro/auragalaxy/DECISIONES.md` |
| Montar la ficha, orden de los bloques, qué falta antes de publicar | `bazar-bizarro/auragalaxy/README.md` |

No leas un archivo que no toca. Una conversación de estrategia no necesita las
restricciones de CSS, y una de código no necesita el perfil del propietario.

---

## Lo que aplica siempre

Estas cinco reglas no dependen del tema. Salen de errores reales, no de buenas
intenciones.

1. **Lee la fuente antes de opinar sobre ella.** Si hay una URL, un CSS, un HTML
   o una API accesible, se accede. Diseñar "al estilo de" un competidor teniendo
   su hoja de estilos descargable costó tres rondas de correcciones el
   18/09/2026.
2. **No afirmes que algo está en una web si no lo has visto renderizado.**
   Extraer texto del HTML no prueba que sea visible.
3. **Un fallo propio no es un bloqueo del sistema.** Antes de decir "no puedo",
   reintentar por otra vía y enseñar el error exacto. La escritura de SEO en
   Shopify se dio por bloqueada durante días por usar una mutación deprecada.
4. **Tutear, con humor, sin adular.** Si una idea del propietario es peor que la
   alternativa, se dice y se argumenta. Él decide después. Citar la fuente de
   cada dato: necesita poder explicarlo a terceros.
5. **Cerrar el ciclo antes de terminar la sesión.** Toda decisión nueva se
   escribe en el archivo que le toca, y todo error propio del que salga una
   regla se añade aquí. Sin esperar a que lo pidan: una retro cuyas acciones no
   se escriben no ha ocurrido. Lo que solo vive en el scratchpad no existe,
   porque el contenedor se recicla.

## Espejo en Notion

Este mismo índice y sus tres archivos están duplicados en Notion, para los
chats que no tienen este repositorio enganchado:
<https://app.notion.com/p/3dfe46a24338811d9846eb4f3502bf1c>

Si el repositorio y Notion dicen cosas distintas, **manda el repositorio**.
Al cambiar algo aquí, actualizar también la página.

## Cómo se mantiene este índice

Si este archivo crece, deja de leerse. Todo lo que sea consultable por tema se
saca a `contexto/` y se enruta desde la tabla de arriba. Aquí solo se queda lo
que hay que saber **en toda conversación, sea del tema que sea**.
