> ADVERTENCIA: ¡La mayoría de los comandos distinguen entre mayúsculas y minúsculas y modificadores!
> * `w` significa presionar la tecla `W`
> * `W` significa presionar `SHIFT` y `W` juntas (¡Mayúsculas!)
> * `^` significa presionar `CTRL` ignorando mayúsculas; `^W` significa `CTRL + w` SIN MAYÚS

## Conceptos básicos

Movimiento del cursor: Teclas de flecha o `hjkl`

```
h     l
left  right

j     k
down  up
```

---

* `w` - saltar a la siguiente palabra antes de la puntuación
* `W` - saltar a la siguiente palabra
* `b` - saltar a la palabra anterior antes de la puntuación
* `B` - saltar a la palabra anterior

--

* `gg` - saltar al inicio/comienzo del archivo
* `G` - saltar al final del archivo (eof)

--

En modo VISUAL (`v`) o VISUAL-LINE `V`
* `>` - indent to the right
* `<` - indent to the left

--

Find / Fuzzy / Regex / Regular Expression
* `/` - Comienza a buscar cosas con Regex, termina con Enter
* `n` - Buscar el siguiente resultado
* `N` - Buscar resultado anterior

Replace: resalte los elementos que desea reemplazar usando el modo Visual y luego
* `:s/<findterm>/<replaceterm>`
* `:%s/<findterm>/<replaceterm>/g`

Comentar descomentar líneas:
* `:g/^#/s  :1,50s/^#/  :1,50s/^#//   :1,100s/^/# /`

Eliminar líneas en blanco:
* `:g/^$/d`

--

Folds: ( agrupación de lineas o plegado de código req: foldmethod=manual )
Plegar: in normal mode or visual mode and select
Desplegar: in FoldLine -> 2spaces or arrow right
zf zf2j = create fold            zc zC = close fold
zo zO   = open fold              zd    = delete fold

--

Modeline opts: (en inicio o final) (:help modeline)
*`# vim:ft=sh    ..   " vim: ts=2 sts=2 sw=2 et`

## Windows

* `^W` y luego las teclas de movimiento para enfocar/resaltar una ventana diferente

* `:sp` o `^W s` para abrir una nueva ventana a continuación (dividida horizontalmente)
* `:vsplit` o `^W v` para abrir una nueva ventana a la derecha (dividir verticalmente)

--

Tenga en cuenta que puede anteponerles números.
* `^W >` - amplía el tamaño de la ventana
* `^W <` - hace que el tamaño de la ventana sea más pequeño
* ??? - minimizar ventana (si es que es posible)

--

## File / Word Finder (Telescope)

`:Telescope find_files` = `<Space> sf` Buscar archivos
`:Telescope` = `<Space> sg` Buscar grep

## Embedded terminal

Cree una nueva ventana, ejecute `:terminal` y luego ingrese al modo Insertar.
Para hacer que la terminal deje de consumir su entrada, cambie a otra ventana o `CTRL + \` `CTRL + N`

--

### nvim-tree - File tree sidebar

La barra lateral debe estar enfocada. Si se cierra accidentalmente, ejecute `:NvimTreeOpen`
* `g?` - Activar o desactivar ayuda
* `a` - Crea un nuevo archivo
* Agregue un `/` adicional para crear un directorio
