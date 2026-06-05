---
title: Skills
description: Habilidades reutilizables que los agentes de GitHub Copilot pueden invocar para realizar tareas específicas.
category: skills
tags: [skills, agentes, copilot, reutilizable]
---

# Skills

Colección de **skills reutilizables** para agentes de GitHub Copilot.

## ¿Qué es un skill?

Un skill es una habilidad encapsulada que un agente puede invocar para realizar una tarea concreta (buscar en la web, ejecutar código, consultar una API, etc.). Se define normalmente como un archivo YAML o JSON que describe el nombre, descripción, parámetros y lógica de invocación.

## Cuándo usar esta categoría

- El recurso define una capacidad invocable por el agente (no es un plugin ni un conector).
- Es reutilizable en múltiples contextos o agentes.
- Puede combinarse con otros skills o herramientas.

## Buenas prácticas

- Documenta los parámetros de entrada y salida en el `README.md` del skill.
- Incluye al menos un ejemplo de uso.
- Mantén el scope del skill pequeño y enfocado en una sola responsabilidad.

## Entradas

| Nombre | Descripción | Autor | Enlace |
| --- | --- | --- | --- |
