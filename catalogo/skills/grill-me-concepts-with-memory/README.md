---
title: grill-me-concepts-with-memory
description: Tutor socrático con memoria persistente para Claude. Detecta el nivel del usuario, explica conceptos con fuentes verificadas, interroga con una pregunta por turno y guarda el progreso en un árbol jerárquico de markdowns.
category: skills
author: "@manfredengler"
tags: [claude, tutor, memoria, socrático, aprendizaje, interactivo]
created: 2026-06-05
updated: 2026-06-05
platform: claude.ai
---

# grill-me-concepts-with-memory

Tutor socrático con memoria persistente para Claude.ai.

## Qué hace

- Detecta el nivel del usuario (novice / intermediate / advanced) con una pregunta calibradora
- Explica conceptos de forma breve y precisa, con fuentes verificadas (`web_search`)
- Interroga con 1 pregunta por turno — nunca da la respuesta directo
- Guarda progreso en árbol jerárquico de markdowns con frontmatter:
  `INDEX.md` → `topic.md` → `concepts/{slug}.md`
- Configurable: tono (`/vibe`) y nivel de energía/motivación (`/energia`)
- Genera dashboard HTML interactivo con `/explorar`
- Encuesta de satisfacción al cerrar sesión

## Plataforma

Skill para **Claude.ai**. Se importa desde la URL raw del `SKILL.md` o se usa directamente como instrucción de sistema.

## Comandos

| Comando | Acción |
|---------|--------|
| `/help` | Lista de comandos |
| `/nivel [novice\|intermediate\|advanced]` | Ajusta dificultad |
| `/vibe [serio\|directo\|irreverente]` | Ajusta tono |
| `/energia [0-10]` | Ajusta nivel de motivación |
| `/next` | Avanza al próximo concepto |
| `/retry` | Repite preguntas fallidas |
| `/mapa` | Diagrama visual de conceptos |
| `/explorar` | Dashboard HTML de toda la memoria |
| `/stats` | Estadísticas de la sesión |
| `/fin` | Cierra sesión y genera resumen |

## Archivos

| Archivo | Contenido |
|---------|-----------|
| [`SKILL.md`](./SKILL.md) | Instrucciones principales del skill (≤100 líneas) |
| [`references/WORKFLOWS.md`](./references/WORKFLOWS.md) | Flujos de calibración, vibe, interrogación, retomar y cierre |
| [`references/MEMORY-TREE.md`](./references/MEMORY-TREE.md) | Estructura del árbol de markdowns con frontmatter |
| [`references/SCORING.md`](./references/SCORING.md) | Rúbrica 1-5 y tipos de pregunta por nivel |
| [`references/VIBE.md`](./references/VIBE.md) | Guía de tono, humor y motivación |
| [`references/EXPLORER.md`](./references/EXPLORER.md) | Spec del dashboard HTML para `/explorar` |

## Memoria generada

```
/home/claude/learning/
├── INDEX.md
└── topics/
    └── {slug}/
        ├── topic.md
        └── concepts/
            └── {concept-slug}.md
```

## Versión

`1.0.0` — creado en Claude.ai, junio 2026.
