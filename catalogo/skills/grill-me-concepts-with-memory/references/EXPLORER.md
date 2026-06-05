---
title: Explorer — grill-me-concepts-with-memory
description: Especificación del dashboard HTML interactivo generado por el comando /explorar.
---

# Explorer (`/explorar`)

## Qué genera

Un archivo HTML autocontenido (`explorer.html`) con un dashboard interactivo que visualiza toda la memoria de aprendizaje guardada en `/home/claude/learning/`.

## Estructura del dashboard

### Header

- Título: "Learning Explorer"
- Subtítulo: fecha de generación + total de conceptos guardados
- Botón: "Exportar JSON"

### Panel principal — árbol de temas

Lista todos los temas en `INDEX.md` como cards expandibles:

```
[▶ Tema A]  [en-progreso]  [12 conceptos]  [última sesión: 2026-05-30]
  └─ Concepto 1  [dominado] [score: 5]
  └─ Concepto 2  [en-progreso] [score: 3]
  └─ Concepto 3  [pendiente]
```

### Panel de estadísticas

- Total de temas / conceptos
- Score promedio global
- Gráfico de barras: distribución de scores (1-5)
- Gráfico de progreso: dominados vs en-progreso vs pendientes

### Panel de búsqueda

Input de texto para filtrar conceptos por nombre, tema o estado.

## Especificaciones técnicas

- **Un solo archivo HTML** — sin dependencias externas. Todo CSS y JS inline.
- **CSS:** variables para temas claro/oscuro. Toggle en el header.
- **JS:** vanilla, sin frameworks. Lectura del JSON embebido en el HTML.
- **Responsive:** funciona en mobile y desktop.
- **Colores de estado:**
  - dominado → verde (`#22c55e`)
  - en-progreso → amarillo (`#eab308`)
  - pendiente → gris (`#6b7280`)
  - fallido → rojo (`#ef4444`)

## Proceso de generación

1. Leer `INDEX.md` para obtener lista de temas.
2. Leer cada `topic.md` y sus `concepts/*.md`.
3. Construir objeto JSON con toda la estructura.
4. Generar HTML con el JSON embebido como `const data = {...}`.
5. Guardar como `/home/claude/learning/explorer.html`.
6. Informar al usuario la ruta del archivo generado.

## Ejemplo de JSON embebido

```json
{
  "generated": "2026-06-05",
  "topics": [
    {
      "title": "Programación Orientada a Objetos",
      "slug": "poo",
      "level": "intermediate",
      "status": "en-progreso",
      "concepts": [
        {
          "title": "Encapsulamiento",
          "slug": "encapsulamiento",
          "score": 5,
          "status": "dominado",
          "attempts": 1
        }
      ]
    }
  ]
}
```
