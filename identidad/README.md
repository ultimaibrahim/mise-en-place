# Identidad de mise

Hasta ahora mise no tenía rostro propio: tomaba prestada la tipografía de étoile (Giaza) y no tenía símbolo. Esta carpeta lo resuelve con tres piezas que salen de lo que mise hace.

## Símbolo: la bandeja con una casilla llena

Una bandeja de 3 × 3 compartimentos (la *mise en place* de una cocina y la charola de un almacén) que también es una hoja de cálculo, con una casilla rellena: **el producto en su lugar**. Une los tres mundos de mise: cocina, inventario y Sheets.

- `mise-simbolo.svg`: versión de color (verde de operación `#3D5A47`).
- `mise-simbolo-mono.svg`: usa `currentColor`, para cualquier fondo.
- `favicon.svg`: el símbolo en crema sobre un mosaico verde con esquinas redondeadas, con trazos más gruesos para que se lea a 16 px. Enlazarlo con `<link rel="icon" type="image/svg+xml" href="identidad/favicon.svg">`.
- Solo una casilla va llena y siempre es la de abajo a la derecha. No cambiarla de lugar ni rellenar más.
- Espacio libre mínimo alrededor: el ancho de una casilla. Tamaño mínimo: 14 px.

## Tipografía

| Uso | Fuente | Por qué |
|---|---|---|
| Nombre (**siempre en minúsculas: `mise`**), títulos cortos | **Big Shoulders Stencil Display**, 900 | Es el rotulado de caja y estiba: plantilla de stencil, condensada, legible a distancia. En minúsculas la `m` y la `s` quedan compactas y la `i` con su punto en bloque: se reconoce sin el símbolo. |
| Etiquetas de nodo (BDG, PDA, PDM) | La misma, 900, mayúsculas | Siglas, como en una caja. |
| Cifras, folios, hashes, kardex | **Martian Mono** | Monoespaciada ancha: los saldos y los folios se alinean como en un libro mayor. |
| Texto corrido | La del producto (Plus Jakarta Sans en la web) | Sin cambios. |

Se probaron otras plantillas (Saira Stencil One, Stardos, Allerta, Sirin y Big Shoulders Stencil Text); Big Shoulders Stencil Display fue la que mejor se mantiene compacta y propia en minúsculas (Saira Stencil One también funciona, pero es más genérica).

Regla: el stencil es solo para el nombre y las etiquetas cortas; nunca para párrafos. Giaza queda para étoile y la marca LCP.

Los archivos están en `fonts/` (woff2, variables). Ejemplo:

```css
@font-face { font-family: 'Big Shoulders Stencil Display'; src: url('fonts/BigShouldersStencilDisplay.woff2') format('woff2'); font-weight: 100 900; }
@font-face { font-family: 'Martian Mono'; src: url('fonts/MartianMono.woff2') format('woff2'); font-weight: 100 800; font-stretch: 75% 112.5%; }
.mise-nombre { font: 900 3rem/.85 'Big Shoulders Stencil Display', Impact, sans-serif; letter-spacing: .01em; }  /* minúsculas */
```

## Color

- Operación (hojas y web de LCP): verde `#3D5A47`, sage `#7A9E8A`, crema `#F5EFE6`, según el core de Ibrahim.
- Portafolio personal (ultimaibrahim.dev): menta `#9DE3BD` sobre el fondo violeta. No se mezclan las dos paletas.

## Dónde se usa hoy

- Portafolio de ultimaibrahim: nombre, símbolo y cifras de la ficha de mise.
- Pendiente de decidir por Ibrahim: llevarlo a `mise-web` (favicon, encabezado) y a la página de estado de las hojas. No se tocó ningún archivo de la app.

Muestra visual: abre `muestra.html` en el navegador.
