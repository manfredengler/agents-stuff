---
title: Catálogo de creaciones
description: Índice central de recursos para agentes de GitHub Copilot, organizados por categoría.
tags: [catalog, index, agentes, copilot]
---

# Catálogo de creaciones

Espacio para **archivar** y **compartir** creaciones relacionadas con agentes.

## Estructura

| Categoría | Descripción breve |
| --- | --- |
| [`skills/`](./skills/) | Skills reutilizables para agentes (Copilot, Claude, otros) |
| [`plugins/`](./plugins/) | Extensiones y plugins para VS Code / Copilot |
| [`conectores/`](./conectores/) | Conectores a APIs y fuentes de datos externas |
| [`prompts/`](./prompts/) | Plantillas de prompt orientadas al usuario |
| [`system-prompts/`](./system-prompts/) | Instrucciones de sistema para agentes |
| [`hooks/`](./hooks/) | Hooks de automatización y manejadores de eventos |
| [`mcp/`](./mcp/) | Servidores y herramientas Model Context Protocol |
| [`otros/`](./otros/) | Recursos que no encajan en las categorías anteriores |

## Reglas de organización

### Nomenclatura

- Usa **minúsculas** y **guiones** (`-`) para nombres de carpetas y archivos. Nunca espacios ni mayúsculas.
- El nombre debe ser descriptivo y único dentro de la categoría (ej. `web-search-skill`, `github-connector`).

### Estructura de cada recurso

Cada recurso debe vivir en su **propia subcarpeta** dentro de la categoría correspondiente y contener al menos:

```
catalogo/<categoria>/<nombre-del-recurso>/
├── README.md        # documentación del recurso (con frontmatter)
└── <archivos>       # código, configuración, ejemplos, etc.
```

El `README.md` de cada recurso debe incluir frontmatter con los campos obligatorios definidos en la plantilla de abajo.

### Categorización

Elige la categoría según la naturaleza principal del recurso:

| Si el recurso es… | Colócalo en |
| --- | --- |
| Una habilidad reutilizable que el agente puede invocar (Copilot, Claude, etc.) | `skills/` |
| Una extensión de VS Code o Copilot | `plugins/` |
| Una integración con una API o sistema externo | `conectores/` |
| Una plantilla de prompt para el usuario final | `prompts/` |
| Instrucciones de sistema (rol, contexto, restricciones) | `system-prompts/` |
| Un manejador de eventos o automatización | `hooks/` |
| Un servidor o herramienta MCP | `mcp/` |
| Cualquier otro tipo de recurso | `otros/` |

Si un recurso podría encajar en varias categorías, elige la más específica. Si no existe una categoría adecuada, usa `otros/` y abre una issue para proponer una nueva.

### Calidad de las entradas

- La **descripción** debe explicar *qué hace* el recurso y *para qué sirve*, en una o dos frases.
- El **enlace** debe apuntar a la carpeta o archivo principal del recurso dentro de este repositorio.
- Mantén la tabla del `README.md` de categoría ordenada **alfabéticamente** por nombre.
- No incluyas recursos externos o de terceros sin indicarlo explícitamente en la descripción.

## Cómo contribuir

1. Crea una carpeta para tu recurso: `catalogo/<categoria>/<nombre>/`.
2. Añade un `README.md` con frontmatter (ver plantilla abajo).
3. Añade una fila en la tabla del `README.md` de la categoría correspondiente.
4. Abre una PR siguiendo el formato estándar.

## Plantilla de frontmatter para recursos

```yaml
---
title: Nombre del recurso
description: Qué hace y para qué sirve, en una o dos frases.
category: skills | plugins | conectores | prompts | system-prompts | hooks | mcp | otros
author: "@usuario"
tags: [tag1, tag2]
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

## Plantilla de entrada en tabla de categoría

| Nombre | Descripción | Autor | Enlace |
| --- | --- | --- | --- |
| Ejemplo | Qué hace y para qué sirve | @usuario | [Recurso](./nombre-del-recurso/) |

