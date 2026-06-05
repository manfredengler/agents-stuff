---
title: MCP
description: Servidores y herramientas del Model Context Protocol (MCP) que extienden las capacidades del agente con acceso a contexto y herramientas externas.
category: mcp
tags: [mcp, model-context-protocol, servidores, herramientas, agentes]
---

# MCP

Colección de **servidores y herramientas Model Context Protocol (MCP)**.

## ¿Qué es MCP?

El [Model Context Protocol](https://modelcontextprotocol.io) es un estándar abierto que permite a los agentes de IA conectarse con herramientas y fuentes de contexto externas a través de servidores MCP. Un servidor MCP expone recursos, herramientas y prompts que el agente puede descubrir y utilizar.

## Cuándo usar esta categoría

- El recurso es un servidor MCP completo (con su manifiesto y lógica de herramientas).
- Expone herramientas o recursos siguiendo la especificación MCP.
- Requiere ser arrancado como proceso separado al que el agente se conecta.

## Buenas prácticas

- Incluye el archivo de manifiesto MCP (`mcp.json` o equivalente).
- Documenta todas las herramientas expuestas con sus parámetros y ejemplos.
- Especifica cómo iniciar el servidor (comando, variables de entorno requeridas).
- Indica la versión del protocolo MCP con la que es compatible.
- Si requiere credenciales externas, documenta las variables de entorno sin incluir valores reales.

## Entradas

| Nombre | Descripción | Autor | Enlace |
| --- | --- | --- | --- |
