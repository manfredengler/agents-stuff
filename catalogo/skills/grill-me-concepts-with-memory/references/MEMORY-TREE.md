---
title: Memory Tree — grill-me-concepts-with-memory
description: Estructura del árbol jerárquico de markdowns para guardar progreso de aprendizaje.
---

# Memory Tree

## Estructura de archivos

```
/home/claude/learning/
├── INDEX.md                          ← mapa de todos los temas
└── topics/
    └── {topic-slug}/
        ├── topic.md                  ← resumen del tema
        └── concepts/
            └── {concept-slug}.md    ← un concepto trabajado
```

## INDEX.md

```yaml
---
title: Learning Index
updated: YYYY-MM-DD
---
```

```markdown
# Learning Index

| Tema | Slug | Estado | Última sesión |
|------|------|--------|---------------|
| Nombre del tema | topic-slug | en-progreso / completado | YYYY-MM-DD |
```

## topic.md

```yaml
---
title: Nombre del Tema
slug: topic-slug
level: novice | intermediate | advanced
status: en-progreso | completado
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

```markdown
# Nombre del Tema

## Resumen
Descripción breve del tema.

## Conceptos
| Concepto | Slug | Score | Estado |
|----------|------|-------|--------|
| Nombre | concept-slug | 1-5 | dominado / en-progreso / pendiente |
```

## concepts/{concept-slug}.md

```yaml
---
title: Nombre del Concepto
slug: concept-slug
topic: topic-slug
level: novice | intermediate | advanced
score: 1-5
status: dominado | en-progreso | fallido
attempts: N
last_question: "texto de la última pregunta"
sources: ["url1", "url2"]
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

```markdown
# Nombre del Concepto

## Explicación
Resumen de la explicación dada en sesión.

## Notas del usuario
Observaciones relevantes del usuario durante la sesión.
```

## Reglas de escritura

- Crear `INDEX.md` en la primera sesión si no existe.
- Crear `topic.md` la primera vez que se trabaja un tema.
- Crear `concepts/{slug}.md` cada vez que se evalúa un concepto.
- Actualizar `status` y `score` en cada evaluación.
- Actualizar `updated` en `INDEX.md` y `topic.md` al final de cada sesión.
- Los slugs usan minúsculas y guiones. Ej: `programacion-orientada-objetos` → `poo`.
