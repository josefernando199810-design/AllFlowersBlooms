# Feedback 04 — Andrea quiere armar su propio ramo

## Quién soy
Soy **Andrea**, tengo 22 años y estudio en la U. Compro casi todo desde el celular (iPhone) y descubro tiendas por Instagram y TikTok. Quería **armar yo misma un ramo** para la graduación de mi mejor amiga: escoger las flores, el color del papel y los extras, y sumarle **peluche, chocolates, globo y tarjeta**. Siempre busco promos o códigos de descuento, y comparo lo bonito y moderno que se ve el sitio con otras floristerías de IG.

Probé el sitio en producción (https://pure-floral-bloom.base44.app) simulando un iPhone 13, el 21/10/2026. **No confirmé ningún pedido**: me detuve en "Confirmar pedido".

---

## Lo que hice, paso a paso

1. **Fui directo al constructor**, `/carrusel-de-flores`, porque la portada dice *"Elige tus flores, tus colores de envoltura y agregados favoritos para crear un momento inolvidable."*
   - Resultado: *"El constructor de ramos no está disponible en este momento."* Nada más. No hay botón, alternativa ni link a WhatsApp. Lo mismo pasa en escritorio.
2. **Volví al inicio** y abrí el menú (☰). Aparecen: *Inicio, Flores en stock, Cómo pedir, Nosotros, Información, Redes sociales, Acceso*. **No hay ningún link al constructor, a Promociones ni a Complementos.** El menú me costó abrirlo (ver bugs).
3. **Busqué promos** en `/promociones`. El banner dice *"ESPECIAL DÍA DEL NOVIO 🩵• SEPTIEMBRE"*, pero estamos en octubre, y abajo dice *"No hay promociones activas en este momento."* Tampoco hay campo de **código de descuento** en ninguna parte del checkout.
4. **Plan B: un ramo ya hecho.** En "Ramos destacados" elegí **Sueño Kitty ($35)**: tulipanes rosados y azules con peluche de Hello Kitty. Al tocar "Comprar" se abre un modal de 3 pasos: *Personaliza → Tus datos → Resumen*.
5. **Paso "Personaliza".** Subí la cantidad a 2. En *"AGREGA COMPLEMENTOS"* solo hay **CHOCOLATES** (Snickers $2, KitKat $1.60, Hershey's $2.50, Cookies 'n' Creme $2) y **TARJETAS** (artesanal con flor morada $1.50, minimalista con sobre *Gratis*). No hay peluches ni globos: en `/complementos/peluches` y `/complementos/globos` sale *"No hay productos disponibles en esta categoría."* Agregué un Snickers y una tarjeta, y el *"Total estimado"* se actualizó bien ($72.00 con la tarjeta gratis).
6. **Paso "Tus datos".** Los campos son nombre, WhatsApp (+503), correo, fecha, punto de entrega y notas. Al elegir mañana, el sitio me avisó: *"Esta fecha no está disponible. Debes seleccionar una fecha con al menos 3 días de anticipación."* Está claro. El botón va diciendo lo que falta (*"Falta: nombre, teléfono, correo electrónico, fecha deseada, punto de entrega"*), y eso me gustó.
7. **Paso "Resumen".** Muestra el número de pedido *"#AFB-C1PA7"*, la fecha, el punto de entrega, los complementos, el total, el *"Anticipo (50%)"* y el *"Saldo pendiente"*. **Ahí me detuve; no toqué "Confirmar pedido".**
8. También revisé `/flores-en-stock` (3 arreglos), `/tu-pedido` (consulta por teléfono), `/redes` y el ícono de la bolsa.

---

## Lo que me encantó 💐
- **Las fotos de los ramos y los nombres** (*Sueño Kitty, Lovely Lotso, With love, Snoopy, Velvet Bunny, Cotton Candy*). Son exactamente el tipo de ramo temático que se hace viral en TikTok, y el catálogo es bien variado (más de 60 diseños, desde $1.75).
- **El modal de 3 pasos** es rápido y claro, y el total se actualiza en vivo. Los complementos se agregan con un toque.
- El botón que dice qué falta (*"Falta: …"*) en lugar de solo marcar error.
- **La validación de los 3 días** es clara y el calendario ya bloquea las fechas anteriores.
- El resumen muestra el anticipo del 50% y el saldo, así sé cuánto pago ahora.
- En mis pruebas no vi errores de JavaScript en consola ni imágenes rotas.

---

## Dónde me confundí o me trabé
1. **La promesa principal no existe.** La portada promete *"Elige tus flores, tus colores de envoltura y agregados"*, pero el constructor dice *"no está disponible en este momento"*. Para mí, que entré por eso, fue un balde de agua fría. Si lo hubiera visto en un anuncio de IG, me salgo.
2. **Faltan peluche y globo.** Las categorías `/complementos/peluches` y `/complementos/globos` existen pero están vacías, y el modal solo ofrece chocolates y tarjetas. Para una graduación, el globo es lo primero que busco.
3. **La promo está vencida.** *"ESPECIAL DÍA DEL NOVIO 🩵• SEPTIEMBRE"* en octubre se siente abandonado, sobre todo junto a *"No hay promociones activas"*. Tampoco hay campo de cupón, así que no puedo usar un código de influencer.
4. **El ícono de la bolsa no es un carrito.** Al tocar "Bolso" sale *"Estado de tu pedido, Métodos de pago, Zonas de entrega, Chatea con nosotros, Preguntas frecuentes"*. Yo esperaba ver mi carrito. Tampoco puedo juntar dos ramos distintos en un mismo pedido.
5. **No sé dónde escribir la dedicatoria.** Elegí la *"Tarjeta minimalista con sobre… perfecta para… una dedicatoria personalizada"*, pero no aparece un campo para el mensaje. Supongo que va en *"NOTAS (OPCIONAL)"*, pero no lo dice.
6. **La lista de puntos de entrega se ve sucia.** Aparecen *"Multiplaza"* y *"Multiplaza · envío $1.75"*, *"Gran Vía"* y *"La Gran Via · envío $1.75"*, y *"Las Cascadas"* sin precio. No sé cuál elegir ni si Las Cascadas tiene costo.
7. **"Ramos destacados" son los 60+ productos.** Si todo es destacado, nada lo es. El scroll en el celular es eterno.
8. **El checkbox "Necesito el pedido antes de 3 días"** no explica qué pasa si lo marco: ¿cobran extra?, ¿me contactan?

---

## Bugs y errores
| # | Dónde | Pasos | Qué pasa |
|---|---|---|---|
| B1 | `/carrusel-de-flores` (móvil y escritorio) | Abrir la URL | Sale *"El constructor de ramos no está disponible en este momento."* Es la función estrella del sitio y no funciona. Además, el hero de la portada la sigue prometiendo. |
| B2 | Header en móvil (todas las páginas) | Tocar ☰ "Menú" o "Bolso" en el centro del ícono | El contenedor vacío de notificaciones (`div.fixed.top-0.z-[100] … p-4`, el viewport de toasts) queda encima de los íconos y se traga el toque. Solo funcionó tocando el borde inferior del botón. En el iPhone se siente como que *"el menú no abre"*. **Arreglo sugerido:** `pointer-events-none` en ese viewport (y `pointer-events-auto` en cada toast), o moverlo abajo en móvil. |
| B3 | Modal → Resumen | Sueño Kitty x1 + Metrocentro | Total **$36.75**, *Anticipo (50%)* **$18.38** y *Saldo* **$18.38**. Esos dos suman **$36.76**: sobra un centavo. Con x2 + complementos pasa igual ($75.25 → $37.63 + $37.63 = $75.26). El saldo debería calcularse como total − anticipo. |
| B4 | Precio de "Amarillo Intenso" | Comparar inicio con `/flores-en-stock` | En el inicio cuesta **$4.00** y en Flores en stock **$5**. No sé cuál es el precio real. |
| B5 | `/flores-en-stock` | Mirar "Dulce Ilusion" | Aparece etiquetado como *"Lirios"* y *"Tulipanes"* a la vez. En el inicio es solo *LIRIOS*. |
| B6 | Selector "PUNTO DE ENTREGA" | Abrir el select | Hay opciones duplicadas o inconsistentes: "Multiplaza" aparece dos veces, "Gran Vía" convive con "La Gran Via" (sin tilde) y "Las Cascadas" no tiene precio de envío. |
| B7 | Resumen | Llegar al paso 3 | El teléfono se muestra como *"50370000000"*, sin "+" ni espacios. La fecha sale en formato *"2026-10-26"* mientras la del pedido dice *"21 de octubre de 2026"*. Además ya se muestra un *"Pedido #AFB-…"* antes de confirmar, y uno puede pensar que el pedido ya se hizo. |
| B8 | `/promociones` | Abrir la página | El banner *"ESPECIAL DÍA DEL NOVIO… SEPTIEMBRE"* sigue visible en octubre, con *"No hay promociones activas"*. |
| B9 | Inicio (rendimiento) | Cargar `/` en móvil | **Descarga unos 34 MB de imágenes** (132 `<img>` y solo 4 con `loading="lazy"`). Hay PNG de 2.2 a 2.7 MB (`IMG_5964.png`, `1000596736.png`, `1000564309.png`) y JPEG de 1.7 MB. Con datos móviles en El Salvador esto es lentísimo y gasta el plan. |
| B10 | Modal de producto | Inspeccionar los botones | El primer botón del modal (el de cerrar) no tiene texto ni `aria-label`. Hay 2 imágenes sin `alt`. |
| B11 | Inicio | Escribir el nombre de las categorías | Dice *"Arreglos tematicos"*, sin tilde (debería ser "temáticos"). Detalle menor, pero se nota. |

---

## Puntaje: "¿Compraría aquí y lo compartiría en IG?" → **5/10**
Los ramos son lindísimos y el checkout de 3 pasos es fácil: compraría un ramo ya hecho (Sueño Kitty) y lo subiría a mis historias. Pero vine a **armar mi propio ramo con globo y peluche**, y el constructor está apagado, no hay globos ni peluches, la promo está vencida y no hay campo de cupón. No compartiría el link del sitio todavía: se siente a medio terminar y pesa demasiado en el celular. Lo que compartiría sería la foto del ramo.

---

## Top 5 mejoras (ordenadas por impacto)
1. **Reactivar el constructor de ramos o dejar de prometerlo.** Si de verdad no puede estar disponible, cambiar el texto del hero y que la página del constructor ofrezca *"Arma tu ramo por WhatsApp"* o *"Elige un ramo y personalízalo"*. Además, agregar el constructor, Promociones y Complementos al menú ☰, que hoy no tiene ninguno de los tres.
2. **Cargar peluches y globos** (y mostrarlos en "AGREGA COMPLEMENTOS"), además de un **campo de dedicatoria** visible cuando se elige una tarjeta. Son los extras que más se venden para graduaciones y cumpleaños.
3. **Optimizar las imágenes.** Convertir los PNG/JPEG de 2 MB a WebP o AVIF de unos 150 KB, usar `loading="lazy"` y `srcset`, y mostrar en la portada 8 a 12 destacados reales en vez de los 60+. Pasar de 34 MB a menos de 3 MB cambia por completo la experiencia en el celular.
4. **Corregir el header en móvil (B2) y los números del resumen (B3, B4).** Que el menú y la bolsa respondan al primer toque, que anticipo + saldo sumen exactamente el total y que un mismo producto tenga un solo precio en todo el sitio.
5. **Darle vida a las promos.** Quitar o actualizar automáticamente los banners vencidos, crear una promo de temporada (*"Graduaciones de noviembre/diciembre"*), agregar un campo de **código de descuento** para influencers o estudiantes y limpiar la lista de puntos de entrega (sin duplicados, todos con precio).
