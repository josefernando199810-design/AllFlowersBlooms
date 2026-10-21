# Resumen: 5 primeros usuarios de AllFlowersBlooms

Sitio probado: https://pure-floral-bloom.base44.app (21/10/2026). Ningún usuario confirmó pedidos ni envió datos.

| # | Usuario | Dispositivo | Nota | Informe |
|---|---|---|---|---|
| 1 | María, mamá con presupuesto $25 | iPhone | 6/10 | [01-maria-movil.md](01-maria-movil.md) |
| 2 | Carlos, regalo urgente para mañana | Laptop | 4/10 | [02-carlos-urgente.md](02-carlos-urgente.md) |
| 3 | Doña Rosa, 58, desconfía de pagar en línea | Android | 4/10 | [03-dona-rosa-confianza.md](03-dona-rosa-confianza.md) |
| 4 | Andrea, 22, quiere armar su ramo | Móvil | 5/10 | [04-andrea-personaliza.md](04-andrea-personaliza.md) |
| 5 | Luis, compras corporativas | Desktop | 4/10 | [05-luis-corporativo.md](05-luis-corporativo.md) |

**Promedio: 4.6 / 10**

## Prioridades (ordenadas por impacto)

1. **Privacidad en `/tu-pedido`:** se ven pedidos solo con un número de teléfono, sin código (Luis, Doña Rosa).
2. **Menú y bolsa no responden al tocar en móvil:** el contenedor vacío de notificaciones `div.fixed.top-0.z-[100]` tapa el encabezado. Arreglo probable: `pointer-events-none` en el contenedor (María, Andrea, posiblemente Doña Rosa).
3. **No hay WhatsApp, teléfono ni correo visibles**, aunque 3 páginas dicen "contáctanos por WhatsApp". "Nosotros" no dice quién atiende el negocio (Doña Rosa, Luis).
4. **Puntos de entrega contradictorios:** Multiplaza duplicado, "Gran Vía" / "La Gran Via", "lunes a viernes" vs "Lunes a Sabado", y se acepta un punto en un día que no opera (4 de 5 usuarios).
5. **Constructor de ramos apagado:** `/carrusel-de-flores` dice "no está disponible", pero el inicio todavía lo promete (Andrea, Luis).
6. **El pedido no sirve bien como regalo:** no hay datos del destinatario (aparece el comprador), falta el campo de dedicatoria y no hay entrega a domicilio en San Salvador (María, Carlos, Andrea).
7. **El total cambia sorpresivamente:** el envío se suma recién en el resumen; anticipo + saldo da $0.01 más que el total por el redondeo; no se explica qué pasa después de "Confirmar pedido" (María, Andrea).
8. **Urgencia:** la opción "antes de 3 días" está escondida y el resumen se contradice ("PEDIDO URGENTE" + "todos los pedidos con 3 días") (Carlos).
9. **Precios y datos inconsistentes:** "Amarillo Intenso" a $4 vs $5, productos en la categoría equivocada, una nota interna visible ("Si entrega meseta precio cambia") (todos).
10. **Contenido viejo o vacío:** banner de septiembre en `/promociones`, peluches y globos vacíos, `/complementos/tarjetas` distingue mayúsculas, "Preguntas frecuentes" sin preguntas, 404 en inglés.
11. **Rendimiento:** el inicio en móvil descarga ~34 MB (132 imágenes, solo 4 en carga diferida, PNG de 2–2.7 MB) y el catálogo aparece dos veces (Andrea, María).
12. **Accesibilidad y texto:** botones sin etiqueta, tildes faltantes ("Siguenos", "Sabado", "TEMATICOS") y teléfonos de 4 dígitos aceptados.

## Lo que gustó

- Se compra sin crear cuenta, con un flujo corto de 3 pasos.
- El total se actualiza en vivo y el botón dice "Falta: …".
- Las fotos y los nombres de los ramos temáticos.
- Las páginas cargan rápido en desktop y no hay errores de JavaScript.
