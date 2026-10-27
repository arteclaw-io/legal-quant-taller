# ARCHITECTURE.md

Decisiones de arquitectura y camino de crecimiento. Cada decisión nueva se agrega con fecha; las anteriores no se borran.

## Decisión vigente (versión 1, 2026-10-27)

Cada herramienta es un único `index.html` con CSS y JavaScript simples, sin librerías ni servidor. Motivo: se abre en cualquier navegador, no requiere instalar nada y es fácil de revisar.

Capas dentro del archivo, de abajo hacia arriba:

1. **Norma y datos:** constantes con nombre, con fuente y fecha (por ejemplo, la UMA y la escala del art. 21).
2. **Reglas:** funciones puras que calculan a partir de los datos.
3. **Presentación:** el HTML y el código que lee el formulario, llama a las funciones y muestra el paso a paso.

La verificación vive fuera del archivo, en `verificar.md`.

## Cómo crece

Cada paso es un intent con su fecha. No se salta de nivel sin una razón escrita.

| Paso | Cambio | Cuándo conviene |
|---|---|---|
| 1 | Separar estilo y lógica en `styles.css` y `app.js` | Cuando el `index.html` se vuelve difícil de leer |
| 2 | Pruebas automáticas que ejecuten los ejemplos de `verificar.md` | Cuando hay más de una herramienta o más de un colaborador |
| 3 | Datos fijos en un archivo propio (`data/`), con fuente y fecha por registro | Cuando los valores cambian seguido (por ejemplo, la UMA) |
| 4 | Un servicio que consulte la fuente oficial y entregue el valor vigente | Cuando se quiere actualización automática de la UMA |
| 5 | Backend o API propia | Cuando hay usuarios, datos guardados o integración con otros sistemas |

Los pasos 1 a 3 siguen siendo estáticos; los pasos 4 y 5 cambian el modo de despliegue y requieren una decisión explícita acá antes de tocar código.
