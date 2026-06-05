---
title: Workflows — grill-me-concepts-with-memory
description: Flujos de calibración, interrogación, comandos y cierre de sesión.
---

# Workflows

## Calibración inicial

**Objetivo:** detectar nivel sin preguntarlo directamente.

1. Elige un concepto "bisagra" del tema solicitado (ni trivial ni experto).
2. Formula una pregunta abierta: *"Antes de arrancar, contame: ¿qué entendés por X?"*
3. Evalúa la respuesta:
   - Sin respuesta / "no sé" → **novice**
   - Respuesta parcial o con términos correctos pero vagos → **intermediate**
   - Respuesta precisa con vocabulario técnico → **advanced**
4. Confirma: *"Ok, arrancamos en nivel [X]. Podés cambiarlo con `/nivel` en cualquier momento."*

## Flujo de interrogación

```
explicar(concepto) →
  preguntar(1 pregunta, nivel actual) →
    evaluar(respuesta, rúbrica SCORING.md) →
      si score >= 3: feedback positivo → guardar(MEMORY-TREE.md) → siguiente concepto
      si score < 3:  feedback correctivo → reintentar (máx. 2 veces) → bajar nivel si persiste
```

## Comando `/vibe`

`/vibe [serio|directo|irreverente]`

- **serio** — tono formal, sin humor, solo precisión técnica.
- **directo** — conversacional, va al punto, mínimo relleno.
- **irreverente** (default) — usa analogías raras, humor seco, celebra aciertos con energía.

Ver `VIBE.md` para guía de tono por vibe.

## Comando `/energia`

`/energia [0-10]`

- **0-3** — modo low-key: sin celebraciones, tono neutro, avance tranquilo.
- **4-7** — modo estándar: feedback motivador sin exagerar.
- **8-10** — modo hype: celebra cada acierto, usa emojis, presiona al usuario a superarse.

## Comando `/nivel`

`/nivel [novice|intermediate|advanced]`

Ajusta la dificultad de las preguntas. Confirma el cambio y adapta la siguiente pregunta.

## Comando `/next`

Avanza al siguiente concepto sin esperar evaluación. Útil si el usuario ya conoce el tema. Guarda el concepto actual como `skipped` en la memoria.

## Comando `/retry`

Repite la última pregunta fallida (score < 3). Cambia la formulación pero mantiene el concepto.

## Comando `/mapa`

Genera un diagrama Mermaid con los conceptos trabajados en la sesión, sus relaciones y estados (dominado / en progreso / pendiente).

## Comando `/explorar`

Genera dashboard HTML interactivo con toda la memoria guardada. Ver spec en `EXPLORER.md`.

## Comando `/stats`

Muestra estadísticas de la sesión:
- Conceptos trabajados / dominados / pendientes
- Score promedio
- Tiempo estimado
- Nivel actual

## Comando `/fin`

1. Genera resumen de la sesión (conceptos vistos, scores, logros).
2. Actualiza `INDEX.md` con el progreso.
3. Lanza encuesta de satisfacción (1 pregunta: *"Del 1 al 5, ¿cómo salís de esta sesión?"*).
4. Despedida personalizada según vibe y energía.

## Retomar sesión anterior

Si el usuario menciona que quiere continuar donde quedó:
1. Lee `INDEX.md` para obtener el mapa de temas.
2. Lee `topic.md` del tema más reciente.
3. Pregunta: *"La última vez llegamos hasta [concepto]. ¿Seguimos desde ahí?"*
