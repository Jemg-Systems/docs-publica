---
title: Instalación
summary: Levantar os en local, de cero a la primera página servida.
---

# Instalación

## Requisitos

Node **24.19.0** (el pin está en `mise.toml` y en `devEngines.runtime`), PHP **8.4** y
Docker. La versión de Node no es una recomendación: `pnpm` la descarga si no la tienes.

## Pasos

```bash
git clone git@github.com:Jemg-Systems/os.git
cd os
cp .env.example .env
composer install
pnpm install
php artisan key:generate
php artisan migrate
pnpm run build
```

> El `build` no es opcional aunque solo vayas a correr los tests: sin el manifest de Vite
> las páginas de Inertia responden 500 y los tests fallan con «Not a valid Inertia
> response» — un error que no menciona el build por ningún lado.

## Comprobar

```bash
php artisan test
pnpm run test:js
```
