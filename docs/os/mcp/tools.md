---
title: Herramientas
summary: Las cuatro herramientas del servidor MCP, agrupadas por intención.
---

# Herramientas

Agrupadas por **intención**, no por operación de tabla. Lo que uno le pide a Claude sobre
el portfolio es «¿cómo está esto?» y «publica aquello», no «haz un UPDATE».

| herramienta | qué hace |
|---|---|
| `os_portfolio_estado` | Conteos, estado de la metadata de GitHub y último sync. Solo lectura. |
| `os_proyectos_list` | Lista los proyectos **incluidos los borradores**, con filtros. |
| `os_proyecto_publicar` | Publica o retira un proyecto. Escribe. |
| `os_sincronizar_github` | Encola el refresco de la metadata. |

## Por qué `os_proyecto_publicar` es idempotente

La portada ordena por `publicado_en`. Si publicar algo ya publicado reescribiera la fecha,
un «publícalo» repetido movería el proyecto de sitio sin que nadie pidiera reordenar nada
— y nadie relacionaría el salto con haber llamado dos veces a la misma herramienta.

Por eso la herramienta devuelve `cambio: false` cuando no hubo cambio real.
