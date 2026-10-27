# Calculadora de honorarios

Versión 1. Datos verificados el 27/10/2026.

## Pedido

Crear una calculadora de honorarios para juicios civiles y comerciales de la justicia nacional con sede en CABA. Estima entre qué valores puede regular el juez los honorarios, según el monto del juicio, aplicando la escala del artículo 21 de la Ley 27.423.

- El usuario ingresa el monto del juicio en pesos.
- La herramienta convierte el monto a UMA, ubica el tramo de la escala y calcula el honorario mínimo y máximo.
- Muestra el paso a paso: UMA, tramo, porcentajes, cuenta y norma que lo respalda.
- Aclara que es una estimación y que la regulación la decide el juez.
- La UMA y la escala son valores fijos, con su fuente y su fecha de verificación a la vista.
- Se verifica con los ejemplos de `verificar.md`; si no coinciden, no se publica.

## Norma

Ley 27.423, art. 21. Rige para los juzgados nacionales civiles y comerciales de la Capital. No aplica la Ley 5.134 de la Ciudad. Fuente: texto actualizado en InfoLEG (norma 305057), verificado el 27/10/2026.

## Datos

UMA: 108.005 pesos, vigente desde el 1/9/2026. Resolución SGA 2622/26 de la Corte Suprema, 21/10/2026 (expediente 7317/2022, Acordada 31/2026). Fuente: https://www.csjn.gov.ar/documentos/descargar?ID=182918. Verificada el 27/10/2026; también figura en la tabla del CPACF. Revisar cuando se actualice.

## Escala (art. 21)

| UMA | Mín | Máx |
|---|---|---|
| hasta 15 | 22% | 33% |
| 16 a 45 | 20% | 26% |
| 46 a 90 | 18% | 24% |
| 91 a 150 | 17% | 22% |
| 151 a 450 | 15% | 20% |
| 451 a 750 | 13% | 17% |
| más de 750 | 12% | 15% |

Texto del párrafo final: los honorarios no pueden ser inferiores al máximo del grado inmediato anterior, más el incremento por aplicar al excedente la alícuota del grado siguiente.

### Cálculo

1. Monto en UMA = monto / valor de la UMA (sin redondear).
2. Hasta 15 UMA: mínimo = monto x % mínimo del tramo; máximo = monto x % máximo del tramo.
3. Desde el segundo tramo: excedente = monto - (tope en UMA del tramo anterior x valor de la UMA). Mínimo = base + excedente x % mínimo del tramo; máximo = base + excedente x % máximo del tramo.
4. La base depende de la lectura del párrafo final (ver "Decide el abogado").

## Verificar

Cada ejemplo se calcula a mano en [`verificar.md`](../../verificar.md). Si la herramienta no coincide, no está terminada.

- 1.000.000 pesos → 9,26 UMA → 220.000 a 330.000.
- 3.240.150 pesos → 30 UMA → 858.639,75 a 955.844,25.
- 6.480.300 pesos → 60 UMA → depende de la lectura del art. 21: 1.555.272 a 1.652.476,50 (lectura A) o 1.668.677,25 a 1.765.881,75 (lectura B).

## Mostrar

Paso a paso: UMA, tramo, porcentajes, cuenta y norma. "Es una estimación."

## Fuera de alcance

Etapas del proceso (pedido en el intent [`sumar-etapas-del-proceso`](intents/2026-10-27-sumar-etapas-del-proceso.md)), otros intervinientes, mínimos por tipo de proceso, UMA automática.

## Decide el abogado

Lectura del párrafo final del art. 21:

| Lectura | Qué toma como "máximo del grado anterior" | Ejemplo: 60 UMA |
|---|---|---|
| A. Tope del tramo anterior | El tope en UMA del tramo anterior por el porcentaje máximo de ese tramo (45 UMA x 26%) | 14,4 a 15,3 UMA |
| B. Acumulativa | La suma del máximo de cada tramo previo (15 x 33% + 30 x 26%) | 15,45 a 16,35 UMA |

Coinciden hasta el segundo tramo y se separan desde el tercero. **Lectura elegida: pendiente** (intent [`fijar-lectura-del-art-21`](intents/2026-10-27-fijar-lectura-del-art-21.md)). La IA no la elige: la muestra y pregunta. Cómo aplican esta cláusula los jueces en cada caso es un tema aparte, que esta herramienta no resuelve.

## Restricciones técnicas (versión 1)

- Un archivo `index.html` con CSS y JavaScript simples, sin librerías ni servidor.
- Sin diseño propio: estructura semántica.
- Todo en pesos argentinos y en español rioplatense.

## Historial

- 2026-10-27: versión inicial, a partir del pedido de arriba.
- 2026-10-27: UMA a 108.005, Resolución SGA 2622/2026. Aplicado. Intent [`actualizar-uma-res-2622-2026`](intents/2026-10-27-actualizar-uma-res-2622-2026.md).
- Propuesto, no aplicado: [`sumar-etapas-del-proceso`](intents/2026-10-27-sumar-etapas-del-proceso.md).
- Pendiente de decisión del abogado: [`fijar-lectura-del-art-21`](intents/2026-10-27-fijar-lectura-del-art-21.md).

Cada cambio nuevo se registra como un archivo en [`intents/`](intents/) y se agrega acá.
