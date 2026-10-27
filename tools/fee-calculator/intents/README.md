# Intents

Un archivo por cada pedido de cambio, con el nombre `AAAA-MM-DD-titulo.md`. Se agregan, no se editan. La spec los enlaza en su historial.

Un intent dice el qué: objetivo, restricciones y criterios de éxito. El cómo lo resuelve la IA.

```markdown
# Intent: título del cambio

- **Fecha:** AAAA-MM-DD
- **Estado:** propuesto | aplicado | pendiente de decisión | descartado
- **Quién lo decide:** nombre

## Objetivo
Qué se quiere lograr.

## Por qué
La razón y su fuente (norma, resolución, decisión).

## Restricciones
Lo que no puede pasar.

## Criterios de éxito
Cómo sabemos que quedó bien (ejemplos de `verificar.md`).

## Qué cambia en la spec
Qué secciones se actualizan.
```

Los intents de esta carpeta son modelos del formato, con la situación real de la calculadora al 27/10/2026.
