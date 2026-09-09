---
title: Un shell que no finge
date: 2026-09-08
project: os
tags: [os, diseño]
summary: Por qué la portada de os.jemg.dev parece un escritorio pero no tiene ni un dato inventado.
---

# Un shell que no finge

La portada de `os.jemg.dev` tiene barra de estado, workspaces y un launcher que se abre
con `Mod+Space`. Parece un escritorio. La regla que la separa de un decorado es una sola:

> Ninguna pieza del cromo puede mostrar un dato que la web no posea, ni ofrecer una
> interacción que no ejecute.

De ahí salen decisiones que parecen pequeñas y no lo son.

## No hay medidor de CPU

Un navegador no conoce la CPU de la máquina. Pintarlo sería relleno, así que la barra
muestra tres cosas que sí existen: la hora del cliente, el número real de repos publicados
y cuándo corrió por última vez la sincronización con GitHub.

Cuando el sync no ha corrido nunca, la barra dice **«nunca»**. No una fecha inventada.

## Los workspaces son las categorías

No se inventaron secciones «Sobre mí» o «Contacto» para llenar los números del `1` al `4`.
Los workspaces **son** las categorías del portfolio, que ya existían y ya eran URLs:
pulsar `2` cambia la dirección, y recargar esa dirección da la misma vista.

## Los números van sin modificador

La spec decía `Mod+1..4`, como Hyprland. Se cambió al implementarlo: `Ctrl+1` cambia de
pestaña en Chrome y en Firefox, y un shell no puede romperle el navegador al visitante
para navegarse a sí mismo. Los números van solos, igual que `j` y `k`.
