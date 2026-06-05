---
title: Conectores
description: Integraciones con APIs y fuentes de datos externas que permiten a los agentes acceder a información o servicios de terceros.
category: conectores
tags: [conectores, api, integraciones, datos]
---

# Conectores

Colección de **conectores a APIs y fuentes de datos** externas.

## ¿Qué es un conector?

Un conector es una integración que permite al agente acceder a información o realizar acciones en sistemas externos: bases de datos, APIs REST, servicios SaaS, etc. Puede ser un wrapper de API, un cliente autenticado, o una definición de herramienta para MCP.

## Cuándo usar esta categoría

- El recurso actúa como puente entre el agente y un sistema externo.
- Encapsula autenticación, transformación de datos, o lógica de llamada a API.
- No es un servidor MCP completo (para eso usa la categoría `mcp/`).

## Buenas prácticas

- Documenta las variables de entorno o credenciales necesarias sin incluir valores reales.
- Especifica los endpoints o acciones que expone el conector.
- Incluye ejemplos de request y response esperados.

## Entradas

| Nombre | Descripción | Autor | Enlace |
| --- | --- | --- | --- |
