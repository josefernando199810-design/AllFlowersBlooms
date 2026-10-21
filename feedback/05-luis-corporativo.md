# Feedback 05 — Luis, cliente corporativo (primera visita)

**Fecha de la prueba:** 21 de octubre de 2026
**Sitio:** https://pure-floral-bloom.base44.app
**Navegador:** Chromium (Playwright) en escritorio 1366x800; algunas páginas también a 390x844 (móvil)

## Quién soy

Soy Luis, tengo 40 años y trabajo como office manager. Estoy evaluando a AllFlowersBlooms como proveedor fijo para dos cosas:

1. **10 arreglos iguales** para un evento de la empresa.
2. **Flores para la recepción cada mes**, como pedido recurrente.

Soy detallista y desconfiado. Antes de dar los datos de la empresa necesito ver cuatro cosas: si entregan **factura (crédito fiscal o consumidor final)**, si hay **precio por volumen**, **cómo pago y a quién le pago**, y **cómo le doy seguimiento a un pedido**. También me fijo en que el sitio se vea serio: sin enlaces rotos, sin precios distintos para el mismo producto y sin páginas vacías.

> No envié nada que creara datos: ningún pedido, registro, login, chat, testimonio ni anticipo. Llegué hasta el formulario de datos del pedido y me detuve antes de confirmar. En /tu-pedido solo hice una consulta de lectura con un número inventado (70000000).

## Qué revisé

- Inicio (carrusel, catálogo completo, tarjetas, sección "Flores en stock", testimonios, footer) y el menú hamburguesa.
- Todas las páginas informativas: /informacion (abrí los 7 acordeones), /entregas, /pagos (abrí "BAC Credomatic"), /promociones, /nosotros, /redes, /recordatorio ("Cómo pedir").
- Seguimiento y anticipos: /tu-pedido, /dar-anticipo, /enviar-anticipo, /chat (sin entrar al chat).
- Flujo de compra: "Comprar" → subí la cantidad a 10 → "Continuar" → paso "Tus datos" (revisé los campos y las opciones de entrega, sin enviar).
- /flores-en-stock, /carrusel-de-flores, /complementos/tarjetas y /complementos/Tarjetas, /login (solo la vi).
- Una URL inexistente para ver la página 404.
- Las mismas páginas en ancho móvil: comparé tiempos y si había scroll horizontal.
- En cada página medí el tiempo de carga (hasta `networkidle`), los errores de consola y las respuestas HTTP con código 4xx/5xx.

## Tabla de páginas

| URL | Carga escritorio | Carga móvil | Errores consola / HTTP | Estado / comentario |
|---|---|---|---|---|
| `/` | 2.6 s | 2.3 s | 0 | OK. El catálogo carga completo. No hay datos de contacto en el footer. |
| `/informacion` | 1.5 s | — | 0 | OK, pero el contenido es muy genérico (no menciona factura, mayoreo ni cancelaciones). |
| `/entregas` | 1.6 s | 2.3 s | 0 | Carga, pero tiene **horarios y nombres contradictorios** (ver bugs). |
| `/pagos` | 2.0 s | 1.8 s | 0 | Solo transferencia a 2 bancos, a nombre de una **persona natural**, cuenta de ahorro. |
| `/promociones` | 1.9 s | 3.3 s | 0 | **Banner de "Día del Novio · Septiembre" en octubre** y debajo "No hay promociones activas". |
| `/nosotros` | 1.6 s | — | 0 | Texto bonito, pero sin dirección, teléfono, razón social ni NIT. |
| `/redes` | 1.8 s | — | 0 | Los enlaces a Instagram y Facebook funcionan (abren en pestaña nueva). Typo "Siguenos". |
| `/recordatorio` ("Cómo pedir") | 2.5 s | — | 0 | OK. |
| `/tu-pedido` | 1.7 s | — | 0 | Busca solo por teléfono (ver el tema de privacidad). |
| `/dar-anticipo` | 2.3 s | — | 0 | Hace lo mismo que /enviar-anticipo pero **sin el prefijo +503**. Página duplicada. |
| `/enviar-anticipo` | **4.0 s** | — | 0 | Lenta. Muestra "Volver" dos veces. |
| `/chat` | 1.7 s | — | 0 | Pide el teléfono para entrar. No entré. |
| `/flores-en-stock` | 1.7 s | **5.9 s** | 0 | 3 productos. Precio de "Amarillo Intenso" distinto al del inicio. |
| `/carrusel-de-flores` | 1.8 s | — | 0 | **"El constructor de ramos no está disponible en este momento."** La página no tiene contenido. |
| `/complementos/tarjetas` | 2.3 s | — | 0 | **"No hay productos disponibles en esta categoría"**, aunque sí hay tarjetas. |
| `/complementos/Tarjetas` | — | — | 0 | Aquí sí aparecen las 2 tarjetas. La ruta distingue mayúsculas. |
| `/login` | 1.2 s | — | 0 | Es el acceso de administrador. Está bien que exista, pero no aporta nada al cliente. |
| `/esta-pagina-no-existe` | 1.7 s | — | **1 (401 en `/entities/User/me`)** | La 404 sale **en inglés** ("Page Not Found", "Go Home") y con el diseño genérico de la plataforma. |

En ninguna página encontré scroll horizontal a 390 px. La mayoría de las páginas carga en menos de 2.5 s en escritorio, y eso está bien.

## Qué me convenció y qué no (pensando en pedidos corporativos)

**A favor:**
- El catálogo es amplio (más de 60 arreglos en 17 categorías) y tiene precios visibles y razonables ($12–$40 por arreglo).
- El selector de cantidad funciona y calcula bien: 10 x Royal Ride = **$300.00**, y el total estimado se actualiza al momento.
- La regla de anticipación (3 días) y la de 50% de anticipo + 50% contra entrega están claras y repetidas en varias páginas.
- Hay forma de consultar el pedido por teléfono y hay chat. Para alguien que coordina pedidos, eso ayuda.
- Sitio rápido en general, sin errores de JavaScript en las páginas reales.

**En contra (y por esto todavía no firmaría):**
- **No hay ninguna mención de factura, crédito fiscal, NIT, NRC ni razón social** en todo el sitio. Busqué en Información, Pagos, Nosotros y en el formulario: el formulario solo pide nombre, teléfono, correo, fecha, punto de entrega y notas. Sin factura no puedo pasar el gasto por contabilidad.
- **No hay precio por volumen**: 10 unidades cuestan exactamente 10 veces el precio unitario. Tampoco encontré "mayoreo", "empresas", "eventos" ni "suscripción mensual". No hay forma de dejar un pedido recurrente.
- **Solo hay puntos de encuentro (centros comerciales y parques), no entrega a domicilio u oficina.** Para flores de recepción necesito que lleguen a la oficina. La única opción parecida es "Otros departamentos ($6.00, según zona)", y es ambigua.
- **El pago es a una cuenta de ahorro personal** (BAC, a nombre de una persona natural). Para el departamento de finanzas eso es una alerta. Tampoco hay tarjeta, ni link de pago, ni pago contra factura a 15/30 días.
- **El anticipo no es reembolsable** y no hay política de cambios o cancelación para eventos (por ejemplo, si el evento se mueve de fecha).
- **No hay un teléfono, WhatsApp ni correo visible** en el footer ni en Nosotros. El sitio dice "escríbenos por WhatsApp", pero no da el número.

## Inconsistencias y bugs (con URL y pasos)

1. **El mismo producto tiene 3 precios distintos.** "Amarillo Intenso" aparece a **$4.00** en el carrusel de destacados de `/`, a **$4** en la grilla del catálogo de `/` y a **$5** en `/flores-en-stock`.
   Pasos: abrir `/`, buscar "Amarillo Intenso" en "Ramos destacados" y en el catálogo; luego abrir `/flores-en-stock`.
2. **Horario de entregas contradictorio en `/entregas`.** El encabezado dice "De **lunes a viernes**, al mediodía", pero cada punto dice "**Lunes a Sabado** 12:00–13:00". Falta la tilde en "Sábado".
3. **Puntos de entrega duplicados o inconsistentes** en `/entregas` y en el selector "Punto de entrega" del pedido:
   - "Multiplaza" aparece dos veces: una gratis entre semana y otra "Multiplaza · envío $1.75" con "Domingos 2:00pm".
   - "Gran Vía" y "La Gran Via" (sin tilde) aparecen como puntos separados.
   - El bloque de fin de semana dice "Sábados y domingos desde las 2:30 pm", pero Multiplaza y La Gran Via dicen "Domingos 2:00pm".
   - "Otros departamentos" está mezclado en medio de la lista, entre Multiplaza y La Gran Via.
   - Pasos: `/` → "Comprar" en cualquier producto → "Continuar" → desplegar "Punto de entrega".
4. **La promoción está vencida.** En `/promociones` el banner dice "ESPECIAL DÍA DEL NOVIO 🩵• SEPTIEMBRE" (hoy es 21 de octubre) y justo debajo dice "No hay promociones activas en este momento". Da la impresión de que nadie actualiza el sitio.
5. **Ruta de complementos que distingue mayúsculas.** `/complementos/tarjetas` muestra "No hay productos disponibles en esta categoría" y `/complementos/Tarjetas` muestra las 2 tarjetas. Además, el título sale en minúscula ("tarjetas"). Si alguien comparte el enlace escrito a mano, ve una página vacía.
6. **`/carrusel-de-flores` es una página vacía:** "El constructor de ramos no está disponible en este momento." Si la función está apagada, la ruta debería redirigir o explicar qué hacer en su lugar.
7. **La 404 sale en inglés** ("Page Not Found… Go Home") en una tienda que está toda en español. Además genera un error de consola `401` en `/api/apps/.../entities/User/me`. Pasos: abrir `/esta-pagina-no-existe`.
8. **Páginas de anticipo duplicadas.** `/dar-anticipo` y `/enviar-anticipo` hacen lo mismo. La primera no muestra el prefijo 🇸🇻 +503 y la segunda muestra "Volver" dos veces y tarda 4 s en cargar.
9. **Páginas clave que no están en el menú.** El menú hamburguesa solo tiene Inicio, Flores en stock, Cómo pedir, Nosotros, Información y Redes sociales. **Entregas, Pagos, Promociones y "Tu pedido" no aparecen en el menú**, y desde el inicio no encontré un enlace visible a ellas. Llegué solo porque escribí la URL.
10. **Privacidad en el seguimiento.** `/tu-pedido` muestra los pedidos con solo escribir un número de teléfono, sin código de pedido ni verificación. Si alguien conoce el número de nuestra recepcionista, puede ver nuestros pedidos. Además, con un número de 2 dígitos ("12") avisa "suele tener 8 dígitos", pero igual hace la búsqueda.
11. **Producto con categoría o precio sospechoso.** "Little Sunset" (Tulipanes) cuesta **$1.75**, el mismo valor que el costo de envío. ¿Es un error de carga? "Summer" está en TULIPANES, pero su descripción dice "un lirio amarillo grande en el centro".
12. **Detalles de texto:**
    - "BancoAgricola" sin espacio (`/pagos`).
    - "Siguenos" sin tilde (`/redes`).
    - "ARREGLOS TEMATICOS" sin tilde.
    - "Dulce Ilusion" sin tilde.
    - "Pretty pink" y "Tabebuia pink" con minúscula, a diferencia del resto de nombres.
    - "violeta suave blanco" (falta "y").
    - En los testimonios: "lindisimo", "me llego", "Esta hermoso" (se entiende si son citas textuales).
    - En el formulario solo "CORREO ELECTRÓNICO *" lleva asterisco, aunque el mensaje de validación dice que los 5 campos son obligatorios.
13. **Rendimiento en móvil.** `/flores-en-stock` tardó **5.9 s** en móvil, contra 1.7 s en escritorio, y `/promociones` tardó 3.3 s. Es la página de "entrega inmediata": justo la que debería ser más rápida.

## Puntaje

**¿Me registraría para pedidos recurrentes? 4 / 10**

El catálogo es bonito y el sitio funciona, pero para una empresa faltan cosas básicas: factura, precio por volumen, entrega en oficina, pago a una cuenta empresarial y un contacto directo visible. Los precios inconsistentes y la promoción vencida me hacen dudar de que la información esté al día. Para el evento de 10 arreglos les escribiría por WhatsApp (si encontrara el número). Para el pedido mensual, hoy no.

## Top 5 mejoras sugeridas (ordenadas por impacto)

1. **Crear una sección o página "Empresas y eventos"** y enlazarla desde el menú. Debe incluir:
   - si emiten **factura o crédito fiscal** (y qué datos piden: NIT, NRC, razón social);
   - **precios por volumen** (por ejemplo, 5% desde 10 unidades);
   - **plan mensual** con fecha fija;
   - entrega en oficina con su costo.

   En el formulario de pedido, agregar una casilla "Necesito factura" con campos de razón social y NIT.
2. **Corregir los datos de entregas y precios en un solo lugar:**
   - unificar "Gran Vía"/"La Gran Via" y eliminar el Multiplaza duplicado;
   - poner un horario coherente: lunes a viernes o lunes a sábado, no los dos;
   - poner "Otros departamentos" al final;
   - revisar que cada producto muestre el mismo precio en inicio, catálogo y stock ("Amarillo Intenso" $4 vs $5) y revisar "Little Sunset" a $1.75.
3. **Poner en el footer, en todas las páginas, el número de WhatsApp, el correo y el horario de atención**, y agregar al menú **Entregas, Pagos, Promociones y Tu pedido**. Hoy esas páginas no se encuentran navegando.
4. **Proteger el seguimiento de pedidos:** pedir teléfono + número de pedido (o un código enviado por WhatsApp) en `/tu-pedido`. Unificar `/dar-anticipo` y `/enviar-anticipo` en una sola página.
5. **Limpiar lo que se ve abandonado:**
   - quitar o actualizar el banner de septiembre en `/promociones` (o esconder la sección si no hay promociones);
   - redirigir `/carrusel-de-flores` mientras esté desactivado;
   - hacer que `/complementos/:categoria` no distinga mayúsculas;
   - traducir la página 404 al español con enlaces a Inicio y al catálogo;
   - corregir las tildes y typos de la lista anterior.

   Como extra, ofrecer una opción de pago empresarial: cuenta a nombre del negocio, link de pago con tarjeta, o pago contra factura para clientes recurrentes.
