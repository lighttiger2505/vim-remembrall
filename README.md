# Remembrall

A small pluggin to make it easier to remember mappings.

# Installation

Using [vim-plug](https://github.com/junegunn/vim-plug):

```vim
Plug 'urbainvaes/vim-remembrall'
```

# Usage

![](https://raw.github.com/urbainvaes/vim-remembrall/gif/tty.gif)

To scroll the list, use `<c-e>`, `<c-y>`, `<c-f>`, or `<c-b>`.
Adding support for a prefix can be done by adding mappings to your `.vimrc`:

```vim
" Show ',' normal mode mappings when key ',' is pressed
nnoremap <silent> , :call remembrall#remind('n', ',')<cr>

" Show ',' normal mode mappings when the key combination ',?' is pressed,
" so we don't have to wait for the timeout.
nnoremap <silent> ,? :call remembrall#remind('n', ',')<cr>

" Show visual mode mappings
vnoremap <silent> ? :call remembrall#remind('n', '')<cr>
```

Remembrall defines a mapping for the all the prefixes in the list `g:remembrall_normal_keys`,
which defaults to *c, d, g, y, ], [, >, <, =, \<Leader\>* and *\<LocalLeader\>*.
A list of suffixes can be defined with `g:remembrall_suffixes`
that will be appended to the left-hand side in the definition of the mappings.
For example, `let g:remembrall_suffixes = ["", "?"]` will cause Remembrall to define the mappings
```vim
nnoremap <silent> x :call remembrall#remind('n', ',')<cr>
nnoremap <silent> x? :call remembrall#remind('n', ',')<cr>
```
for all `x` in `g:remembrall_normal_keys`.

# Customization

| Config                | Default         | Description                            |
| ------                | -------         | -----------                            |
| `g:remembrall_window` | `topleft 30new` | Command for creating Remembrall window |
| `g:remembrall_zoom`   | `\<c-z>`        | Key to toggle zoom                     |
| `g:remembrall_accept` | `\<c-m>`        | Key to accept feed a mapping           |

# Inspiration

Some parts of the source code were inspired by [vim-peekaboo](https://github.com/junegunn/vim-peekaboo).

# License

MIT
