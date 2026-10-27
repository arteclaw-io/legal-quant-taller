# Intent: fijar la lectura del párrafo final del art. 21

- **Fecha:** 2026-10-27
- **Estado:** aplicado (lectura A)
- **Quién lo decide:** decisión indicada el 27/10/2026; la confirma el abogado responsable

## Objetivo
Fijar cómo se calcula la base desde el segundo tramo: lectura A (tope del tramo anterior) o lectura B (suma de los máximos de cada tramo previo).

## Por qué
El texto dice que los honorarios no pueden ser inferiores al máximo del grado inmediato anterior, más el incremento por aplicar al excedente la alícuota del grado siguiente, y admite las dos lecturas. Se separan desde el tercer tramo (ejemplo 3 de `verificar.md`).

## Restricciones
- La lectura B queda documentada como alternativa y solo rige si un intent nuevo la adopta.
- La herramienta advierte que el juez puede aplicar la lectura B y muestra ese resultado como referencia.
- La decisión y su fundamento quedan escritos en la spec.

## Criterios de éxito
- La spec dice que rige la lectura A y por qué.
- El ejemplo 3 de `verificar.md` queda con un solo resultado esperado: $1.555.272 a $1.652.476,50.

## Qué cambia en la spec
Secciones "Decide el abogado" y "Cálculo" (paso 4).
