" --- Sane defaults ---
set nocompatible          " break free of strict vi compatibility
syntax on                 " syntax highlighting
filetype plugin indent on " filetype-aware indentation and plugins

" --- Indentation ---
set tabstop=4              " a tab is 4 spaces wide
set shiftwidth=4           " indent/outdent by 4 spaces
set expandtab              " turn tabs into spaces
set autoindent             " copy indent from current line when starting a new one
set smartindent            " smarter autoindenting for C-like code

" --- Navigation & display ---
set number                 " show line numbers
" set relativenumber         " relative numbers above/below cursor — great for jumps (5j, 3k)
" set cursorline              " highlight current line
set scrolloff=8            " keep 8 lines visible above/below cursor when scrolling
" set nowrap                  " don't soft-wrap long lines
set showmatch               " briefly jump to matching bracket/paren

" --- Search ---
set incsearch                " show matches as you type
set hlsearch                  " highlight all matches
set ignorecase                " case-insensitive search...
set smartcase                 " ...unless you type a capital letter

" --- Usability ---
set hidden                   " allow switching buffers without saving
set wildmenu                 " visual autocomplete for command-line
set splitright                " vertical splits open to the right
set splitbelow                 " horizontal splits open below
set clipboard=unnamedplus      " use system clipboard for yank/paste

" --- Backup/swap (skip clutter files) ---
" set nobackup
" set nowritebackup
" set noswapfile

" --- Statusline (built-in, no plugin) ---
set laststatus=2
set statusline=%f\ %y\ %m%r%h%w\ [%l,%c]\ %p%%

" --- Leader key + a couple of no-plugin shortcuts ---
let mapleader = " "
nnoremap <leader>w :w<CR>
nnoremap <leader>q :q<CR>
nnoremap <leader>nn :set nu! rnu!<CR>   " toggle line numbers on/off

" --- Extras ---
autocmd FileType c setlocal cindent
autocmd FileType c nnoremap <buffer> <F5> :w<CR>:!gcc % -o %:r -Wall -Wextra -g && ./%:r<CR>
autocmd FileType c nnoremap <buffer> <F6> :w<CR>:!gcc % -o %:r -Wall -Wextra -g && gdb ./%:r<CR>

