nasm-indent
===========

NASM indent script for vim. Vim doesn't provide a default indent script for NASM. So here is one which follow the below rules:

1. If a line is a label (contains `:`), reset its indentation.
  ```nasm
  label: ; indent level = 0
  ```
2. If previous non-empty and not comment line is a label, increase the indenting level
  ```nasm
  label: ; indent level = 0
    mov rax, 0 ; indent level = 1
  ```
3. Otherwise, copy the indenting level of the previous non-empty and not comment line
  ```nasm
    mov rax, 0 ; indent level = 1
    mov rbx, 0 ; indent level = 1
  ```

Installation
------------

With Plugin manager (recommended):

### [dein.vim](https://github.com/Shougo/dein.vim) (my favorite)

```vim
call dein#add('DanSnow/nasm-indent.vim')
```

### [Vundle](https://github.com/VundleVim/Vundle.vim)

```vim
Plugin 'DanSnow/nasm-indent.vim'
```

### [vim-plug](https://github.com/junegunn/vim-plug)

```vim
Plug 'DanSnow/nasm-indent.vim'
```

Install from Source (not recommended)
-------------------------------------

Download the `indent/nasm.vim` and put it to the `indent` under your vim runtime directory.

License
-------

MIT
