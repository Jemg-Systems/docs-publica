---
title: peer
order: 2
summary: Gestor de proyectos y kanban personal, con su propio servidor MCP de solo lectura.
---

# peer

`peer.jemg.dev` es el gestor de proyectos del ecosistema: proyectos, tareas,
requerimientos e incidencias.

Expone un MCP **de solo lectura** que proyecta el histórico de proceso, para que un agente
trabajando en otro repo pueda leer en qué va todo sin volcar ruido. Ninguna herramienta de
ese servidor escribe: crear y editar va por la API v1.
