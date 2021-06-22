# VIM Configuration Tutorial

21.06.2021

The VIM is highly flexible and supports external plugins, making it possible to be converted from just a text editor to a integrated development environment (IDE). In the home directory $HOME, there is a directory called `.vim`, where all the settings, or plugin are stored.

The  `.vim` directory has such a structure

```
.vim/
 |-- autoload/  # loaded automatically when the function is invoked
 |-- backup/
 |-- colors/    # used by the ":colorscheme" command
 |-- plugged/   # specific for *vim-plug* plugin manager
 |-- plugin/    # for standard VIM plugin scripts
 |-- ftplugin/  # plugin specific to some file type (nameFileType.vim)
 |-- indent/    # automatically compute the indent (nameFileType.vim)
 |-- compiler/  # VIM scripts of a specific compiler by `:compiler`
 |-- keymap/    # keymap files for VIM
 |-- lang/      # languages files for VIM
 |-- macros/    # to test VIM for VI compatibility
 |-- syntax/    # for syntax highlighting
```

Afterwards, create also a `.vimrc` file in the home directory.

## Basic Settings in VIM

The comment in vim setting code is beginning with a double quote `"`. Add the following lines to the `.vimrc` file

```
" Disable compatibility with vi which can cause unexpected issues.
set nocompatible

" Enable type file detection. Vim will be able to try to detect the type of file in use.
filetype on

" Enable plugins and load plugin for the detected file type.
filetype plugin on

" Load an indent file for the detected file type.
filetype indent on
```

### The syntax highlighting is verz useful.

```
" Turn syntax highlighting on (or off).
syntax on
```

### You may also want to display line numbers on the left.

```
" Add numbers to each line on the left-hand side.
set number
```

### The followings are some more common setting that enhance the editing experience.

```
" Set shift width to 4 spaces.
set shiftwidth=4

" Set tab width to 4 columns.
set tabstop=4

" Use space characters instead of tabs.
set expandtab

" Do not save backup files.
set nobackup

" Do not let cursor scroll below or above N number of lines when scrolling.
set scrolloff=10

" Do not wrap lines. Allow long lines to extend as far as the line goes.
set nowrap

" While searching though a file incrementally highlight matching characters as you type.
set incsearch

" Ignore capital letters during search.
set ignorecase

" Override the ignorecase option if searching for capital letters.
" This will allow you to search specifically for capital letters.
set smartcase

" Show partial command you type in the last line of the screen.
set showcmd

" Show the mode you are on the last line.
set showmode

" Show matching words during a search.
set showmatch

" Use highlighting when doing a search.
set hlsearch

" Set the commands to save in history default number is 20.
set history=1000
```

### Configure the Status Bar in VIM

You can configure your Vim status bar with useful information. For example, configure the file type, total number of lines in the file, path to the file, column number, row number, percentage through file, and much more.

```
" STATUS LINE ------------------------------------------------------------ {{{

" Clear status line when vimrc is reloaded.
set statusline=

" Status line left side.
set statusline+=\ %F\ %M\ %Y\ %R

" Use a divider to separate the left side from the right side.
set statusline+=%=

" Status line right side.
set statusline+=\ ascii:\ %b\ hex:\ 0x%B\ row:\ %l\ col:\ %c\ percent:\ %p%%

" Show the status on the second to last line.
set laststatus=2

" }}}
```

where

%F – Display the full path of the current file.

%M – Modified flag shows if file is unsaved.

%Y – Type of file in the buffer.

%R – Displays the read-only flag.

%b – Shows the ASCII/Unicode character under cursor.

0x%B – Shows the hexadecimal character under cursor.

%l – Display the row number.

%c – Display the column number.

%p%% – Show the cursor percentage from the top of the file.

## Autocomplete

## Plugin Manager

An easy way to have a plugin is through a plugin manager. One plugin manager can be **[vim-plug](https://github.com/junegunn/vim-plug)**. The detail steps for installation can be found in the corresponding github repository, which can be briefly summarized to

1. download plug.vim and put it in the `autoload` directory,
2. add a vim-plug section to the `$HOME/.vimrc` configuration file,
  
  ```
  " Specify a directory for plugins
  " - For Neovim: stdpath('data') . '/plugged'
  " - Avoid using standard Vim directory names like 'plugin'
  call plug#begin('~/.vim/plugged')
  
  " Make sure you use single quotes

  " On-demand loading
  Plug 'scrooloose/nerdtree', { 'on':  'NERDTreeToggle' }

  " Initialize plugin system
  call plug#end()
  ``` 

3. list the plugins with `Plug` commands.

# License

## For Matlab Configurations

Copyright (c) 2010, Yaroslav Don
Copyright (c) 2009, Fabrice
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

    * Redistributions of source code must retain the above copyright
      notice, this list of conditions and the following disclaimer.
    * Redistributions in binary form must reproduce the above copyright
      notice, this list of conditions and the following disclaimer in
      the documentation and/or other materials provided with the distribution

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.
