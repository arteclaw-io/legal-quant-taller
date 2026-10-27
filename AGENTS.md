# AGENTS.md

Reglas del proyecto para cualquier IA. Este archivo es el contrato de trabajo y crece con el proyecto (ver "Cómo crece este archivo").

## Proyecto

Herramientas jurídicas pequeñas, verificables y mantenibles. Cada herramienta vive en `tools/<herramienta>/` con su spec, sus cambios registrados y su verificación.

```text
AGENTS.md              reglas del proyecto (este archivo)
ARCHITECTURE.md        decisiones de arquitectura y cómo crece el proyecto
verificar.md           ejemplos calculados a mano (la vara común)
tools/<herramienta>/
  SPEC.md              la fuente de verdad de la herramienta
  intents/             un archivo por cada cambio, con fecha
  index.html           la herramienta
tools/_template/       esqueleto para una herramienta nueva
```

## Cómo trabajamos (spec primero)

1. Antes de construir, leé la `SPEC.md` de la herramienta. Si no existe, ayudame a escribirla antes de escribir código.
2. Proponé un plan en pasos chicos y esperá mi aprobación.
3. Construí un paso por vez y mostrá cada cambio.
4. Verificá con `verificar.md`. Si no coincide, no está terminado.
5. Si algo cambia, cambiá primero la spec y registrá el cambio en `intents/`. No toques el resultado a mano. La versión inicial no lleva intent: es el Pedido de la spec.

## Principios de desarrollo

- **La spec manda.** El código se puede regenerar desde la spec; la spec no se deduce del código.
- **Cambios chicos y verificables.** Un cambio por intent. Después de cada uno, correr la verificación.
- **Datos separados de la lógica.** Valores fijos (UMA, escalas, porcentajes) como constantes con nombre al comienzo del script, cada una con su fuente y fecha de verificación. Nunca mezclados dentro de las fórmulas.
- **Funciones puras para el cálculo.** La cuenta vive en funciones que reciben datos y devuelven un resultado, sin tocar la página. La interfaz solo llama a esas funciones y muestra el resultado.
- **Sin dependencias que no se pidieron.** Ni librerías, ni servidores, ni frameworks. Si un cambio los necesita, proponelo primero en `ARCHITECTURE.md` y esperá aprobación.
- **Trazabilidad.** Todo valor y toda regla se pueden rastrear a una norma, una resolución o una decisión escrita.

## Verdad, fuentes y decisiones

- Todo valor fijo indica su fuente y su fecha de verificación. No inventes valores ni fechas: si falta uno, preguntame.
- Si una norma admite dos lecturas, mostralas y preguntame: la decisión jurídica es mía.
- La herramienta aclara que es una estimación y que la decisión la toma el juez o el profesional.
- Todo en pesos argentinos. Nunca pidas ni guardes datos personales o de clientes.

## Convenciones

- Contenido y explicaciones al usuario en español rioplatense; nombres de archivos, carpetas y código en inglés.
- Archivos de intents: `AAAA-MM-DD-titulo-en-minusculas.md`.
- Para ver una página en Codespaces no uses `file://`: serví la carpeta con `python3 -m http.server 8000 --directory tools/<herramienta>` y abrí la pestaña Puertos.

## Cómo crece este archivo

- Una regla nueva entra solo si evita un error que ya ocurrió o fija una decisión ya tomada. Se agrega con fecha y motivo en una línea.
- Si una herramienta necesita reglas propias (por ejemplo, otro stack), creá `tools/<herramienta>/AGENTS.md`. El archivo más cercano a lo que se edita tiene prioridad sobre este.
- Si cambia la arquitectura, se registra en `ARCHITECTURE.md` y recién después se ajusta este archivo.
