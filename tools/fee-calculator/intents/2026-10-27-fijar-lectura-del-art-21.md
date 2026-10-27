# Intent: fijar la lectura del párrafo final del art. 21

- **Fecha:** 2026-10-27
- **Estado:** pendiente de decisión del abogado
- **Quién lo decide:** el abogado (la IA no decide)

## Objetivo
Fijar cómo se calcula la base desde el segundo tramo: lectura A (tope del tramo anterior) o lectura B (suma de los máximos de cada tramo previo).

## Por qué
El texto dice que los honorarios no pueden ser inferiores al máximo del grado inmediato anterior, más el incremento por aplicar al excedente la alícuota del grado siguiente, y admite las dos lecturas. Se separan desde el tercer tramo (ejemplo 3 de `verificar.md`).

## Restricciones
- Hasta que se decida, la herramienta muestra las dos lecturas y no elige.
- La decisión y su fundamento quedan escritos en la spec.

## Criterios de éxito
- La spec dice cuál lectura rige y por qué.
- El ejemplo 3 de `verificar.md` queda con un solo resultado esperado.

## Qué cambia en la spec
Secciones "Decide el abogado" y "Cálculo" (paso 4).
