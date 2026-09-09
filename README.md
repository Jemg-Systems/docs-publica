# docs-publica

Documentación pública y blog de **jemg.dev**. Este repo es la **fuente de verdad**:
`os.jemg.dev` hace pull, parsea el markdown y lo guarda en Postgres para servirlo.

No se edita nada desde el navegador. Se escribe aquí, se commitea, y el hub sincroniza.

## Estructura

```
blog/<AAAA-MM-DD>-<slug>.md          una entrada
docs/<proyecto>/index.md             portada del proyecto  (nivel 0)
docs/<proyecto>/<seccion>/index.md   portada de sección     (nivel 1)
docs/<proyecto>/<seccion>/<pag>.md   una página             (nivel 2)
```

Máximo **3 niveles** bajo `<proyecto>`. El sync aborta si se pasa: una jerarquía más honda
no se navega, se busca.

## Frontmatter

Docs — `title` es obligatorio, el resto tiene default:

| campo | default | efecto |
|---|---|---|
| `title` | — **obligatorio** | título de la página y del `<title>` |
| `slug` | nombre del archivo sin el prefijo `NN-` | último tramo de la URL |
| `order` | el prefijo `NN-` del archivo, o 9999 | posición entre hermanas |
| `sidebar_title` | `title` | título corto para la barra lateral |
| `summary` | vacío | tarjeta de sección, meta description, resultado de búsqueda |
| `hidden` | `false` | fuera del menú, pero accesible por URL |
| `draft` | `false` | no se publica; visible en /admin |
| `redirect_from` | vacío | rutas viejas que redirigen aquí (301) |

Blog — igual, más `date` (obligatoria, `AAAA-MM-DD`), `tags` y `project`. `project` enlaza
la entrada con la documentación de ese proyecto, y es lo que permite mostrarlas juntas.

## Renombrar sin romper enlaces

Cambiar el `slug` de una página crea la redirección **sola**: el sync compara la ruta del
archivo con el slug anterior y deja el 301. No hace falta escribir `redirect_from` a mano
salvo que la ruta vieja venga de fuera de este repo.
