This is my personal cheatsheet that I'm building because of my (most-likely) personal hatred towards VIM's community. Thank you vim community for the toxic, unwelcoming, unopenmindedness and egotistical behavior towards newcomers.

I just want to code using a lightweight editor that's matured enough for there to be plugins and not obsess towards the thing that I already can do with VScode but somehow "more optimized" and stuff like *pErSoNaLiZeD DeVeLoPmEnT EnViRoNmEnT*.

kickstart.nvim lacks wiki / documentation (Issue #3) while targetting newcomers to `begin your Neovim journey`.

Props to Helix editor to actually have a way better cheatsheet / docs for newcomers but sadly no plugins support yet :(

> WARNING: Most commands are case sensitive and modifier sensitive!
> * `w` means pressing `W` key
> * `W` means pressing `SHIFT` and `W` together (Capitalization!)
> * `^` means pressing `CTRL` ignoring capitalization; `^W` means `CTRL + w` WITHOUT SHIFT

## Basics

Cursor movement: Arrow keys or `hjkl`, preferrably maximalize `hjkl`

```
h     l
left  right

j     k
down  up
```

---

* `w` - jump to next word before punctuation
* `W` - jump to next word
* `b` - jump to previous word before punctuation
* `B` - jump to previous word

--

* `gg` - jump to start / beginning of file
* `G` - jump to end of file (eof)

--

On VISUAL (`v`) or VISUAL-LINE `V` mode
* `>` - indent to the right
* `<` - indent to the left

--

Find / Fuzzy / Regex / Regular Expression
* `/` - Start finding stuff with Regex, end with Enter
* `n` - Find next result
* `N` - Find previous result

Replace - Highlight things that want to be replaced using Visual mode then
* `:s/<findterm>/<replaceterm>`
* `:%s/<findterm>/<replaceterm>/g`

Comentar descomentar varias lineas:
:g/^#/s   :1,50s/^#/   :1,50s/^/#   :1,50s/^#//   :1,100s/^/# /
Elimina lineas en blanco:   :g/^$/d

Folds: ( agrupación de lineas o plegado de código req: foldmethod=manual )
Plegar: in normal mode or visual mode and select
Desplegar: in FoldLine -> 2spaces or arrow right
zf zf2j = create fold            zc zC = close fold
zo zO   = open fold              zd    = delete fold

•• Modeline opts: (en inicio o final) (:help modeline)
# vim:ft=sh    ..   " vim: ts=2 sts=2 sw=2 et

## Windows

* `^W` then movement keys to focus / highlight different window

* `:sp` or `^W s` to open new window below (split horizontally)
* `:vsplit` or `^W v` to open new window to the right (split vertically)

--

Note, you can prefix these with numbers
* `^W >` - enlarges window size
* `^W <` - make window size smaller
* ??? - minimize window (idt its even possible)

## File / Word Finder (Telescope)

`:Telescope find_files` = `<Space> sf` Search files
`:Telescope ` = `<Space> sg` Search grep


## Embedded terminal

TBH just spawn a new tab / new window on your native terminal. Its not worth it.

Make a new window, run `:terminal` then enter Insert mode.
To make the terminal stop eating your input, switch to another window or `CTRL + \` `CTRL + N`

## LSP - Intellisense, Language Server, etc

* `<SPACE>rn` - Rename Symbol, VSCode's F2 (`vim.lsp.buf.rename`)
* `<SPACE>ca` - Code Action, VSCode's CTRL + `.` (`vim.lsp.buf.code_action`)
* `<SPACE>e` - Show errors / warning / diagnostics / codelens pop up on cursor (`vim.diagnostic.open_float`)
* `<SPACE>q` - List all errors / diagnostic / warning / codelens on bottom | VSCode's Problems panel (`vim.diagnostic.setloclist`)
* `gd` - Go to Definition (`vim.lsp.buf.definition`)
* `gr` - Go to References (`require('telescope.builtin').lsp_references`)
* `K` - Show hover information (`vim.lsp.buf.hover`) 
* `gcc` - Go Comment Line
* `gcb` - Go Comment Block - Try this if you're on React / Astro

### nvim-tree - File tree sidebar

Sidebar would need to be focused. If accidentally closed, run `:NvimTreeOpen`
* `g?` - Toggle help
* `a` - Create new file
  * Append an extra `/` to create a directory