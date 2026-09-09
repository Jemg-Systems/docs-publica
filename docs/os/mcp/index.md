---
title: MCP
order: 3
summary: El servidor MCP local de os — administrar el portfolio desde Claude.
---

# MCP

`os` expone un servidor **MCP local** (stdio) para administrar el portfolio desde Claude
sin abrir ninguna superficie HTTP nueva.

Es local y no web a propósito: `os` no tiene Sanctum ni Passport, así que servirlo por
HTTP habría significado añadir autenticación y publicar un endpoint. Como servidor local
se arranca desde la misma máquina que ya tiene la base delante.

```bash
php artisan mcp:start os
```

Las herramientas están en **[Herramientas](/docs/os/mcp/tools)**.
