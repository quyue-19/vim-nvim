 # Configuraiton
 ```
  1 syntax on
  2 set number                                       
  3 set cursorline                                   
  4 set wrap
  5 set showcmd 
  6 set wildmenu
  7 
  8 map S :w<CR>
  9 map Q :q<CR>
 10 map R :source $MYVIMRC<CR>
 11 
 12 map sl :set splitright<CR>:vsplit<CR>
 13 map sh :set nosplitright<CR>:vsplit<CR>
 14 map sj :set splitbelow<CR>:split<CR>
 15 map sk :set nosplitbelow<CR>:split<CR>
 16 
 17 map <up> :res +3<CR>
 18 map <down> :res -3<CR>
 19 map <left> :vertical resize-3<CR>
 20 map <right> :vertical resize+5<CR>
 21 
 22 map tu :tabe<CR>
 23 map tn :-tabnext<CR>
 24 map ti :+tabnext<CR>
 25 
 26 call plug#begin()
 27 Plug 'connorholyday/vim-snazzy'
 28 Plug 'preservim/nerdtree'
 29 Plug 'iamcco/markdown-preview.nvim', { 'do': { -> mkdp#util#install() } }                                                             
 30 call plug#end()
```
