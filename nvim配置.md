" NVIM v0.4.3 configuration
" nvim ~/.config/nvim/init.vim
```vim
  1 set nocompatible
  2 filetype plugin on
  3 syntax on
  4 set number
  5 set cursorline
  6 set wrap
  7 set showcmd
  8 set wildmenu
  9
 10 map S :w<CR>
 11 map Q :q<CR>
 12 map R :source $MYVIMRC<CR>
 13 map L :PlugInstall<CR>
 14 map U :UpdateRemotePlugins<CR>
 15 map M :MarkdownPreview<CR>
 16
 17 map sl :set splitright<CR>:vsplit<CR>
 18 map sh :set nosplitright<CR>:vsplit<CR>
 19 map sj :set splitbelow<CR>:split<CR>
 20 map sk :set nosplitbelow<CR>:split<CR>
 21
 22 map <up> :res +3<CR>
 23 map <down> :res -3<CR>
 24 map <left> :vertical resize-3<CR>
 25 map <right> :vertical resize+5<CR>
 26
 27 map tu :tabe<CR>
 28 map tn :-tabnext<CR>
 29 map ti :+tabnext<CR>
 30
 31 noremap N 5j
 32 noremap U 5k
 33
 34
 35 " markdown 的配置
 36 "let g:mkdp_auto_start = 0
 37 "let g:mkdp_auto_close = 1
 38 "let g:mkdp_refresh_slow = 0
 39 "let g:mkdp_command_for_global = 0
 40 "let g:mkdp_open_to_the_world = 0
 41 "let g:mkdp_open_ip = ''
 42 "let g:mkdp_browser = ''
 43 "let g:mkdp_echo_preview_url = 0
 44 "let g:mkdp_browserfunc = ''
 45 "let g:mkdp_preview_options = {
 46 "                       \ 'mkit': {},
 47 "                       \ 'katex': {},
 48 "                       \ 'uml': {},
 49 "                        \ 'maid': {},
 50 "                       \ 'disable_sync_scroll': 0,
 51 "                        \ 'sync_scroll_type': 'middle',
 52 "                       \ 'hide_yaml_meta': 1
 53 "                       \ }
 54 "let g:mkdp_markdown_css = ''
 55 "let g:mkdp_highlight_css = ''
 56 "let g:mkdp_port = ''
 57 "let g:mkdp_page_title = '「${name}」'
 58
 "Changing Wiki Syntax
 60 let g:vimwiki_list = [{'path': '~/vimwiki/',
 61                       \ 'syntax': 'markdown', 'ext': '.md'}]
 62
 63 "ultisnippet配置
 64 "安装插件
 65 let g:UltiSnipsExpandTrigger = '<tab>'
 66 "设置tab键为触发键
 67 let g:UltiSnipsJumpForwardTrigger = '<tab>'
 68 "设置向前跳转键
 69 let g:UltiSnipsJumpBackwardTrigger = '<S-tab>'
 70 "设置文件目录
 71 let g:UltiSnipsSnippetDirectories=["path/of/snippetDirectories"]
 72 "设置打开配置文件时为垂直打开
 73 let g:UltiSnipsEditSplit="vertical"
 74
 75 "markdown 的快捷键（可以写在init.vim for neovim,或者写在.vimrc for vim 8.1+, 或者你可以单独写在另外一个文件中，只    要在配置文件夹中引用即可）
 76 " "source ~/.vim/snippits.vim" # 引用方法：source+「文件」
 77 " 快速添加锚点
 78 autocmd Filetype markdown inoremap <buffer> <silent> ,, <++>
 79 " 寻找下一个锚点
 80 autocmd Filetype markdown inoremap <buffer> <silent> ,f <Esc>/<++><CR>:nohlsearch<CR>c4l
 81 " 寻找下一个锚点并删除锚点前的空格
 82 autocmd Filetype markdown inoremap <buffer> <silent> ,x <Esc>/<++><CR>:nohlsearch<CR>c5l
 83 " 分割线
 84 autocmd Filetype markdown inoremap <buffer> <silent> ,- ---<Enter><Enter>
 85 " 加粗
 86 autocmd Filetype markdown inoremap <buffer> <silent> ,b **** <++><Esc>F*hi
 87 " 删除线
 88 autocmd Filetype markdown inoremap <buffer> <silent> ,s ~~~~ <++><Esc>F~hi
 89 " 斜体
 90 autocmd Filetype markdown inoremap <buffer> <silent> ,p ** <++><Esc>F*i
 91 " 行内代码
 92 autocmd Filetype markdown inoremap <buffer> <silent> ,q `` <++><Esc>F`i
 93 " 代码块
 94 autocmd Filetype markdown inoremap <buffer> <silent> ,c ```<Enter><++><Enter>```<Enter><Enter>++><Esc>4kA
 95 " todo
 96 autocmd Filetype markdown inoremap <buffer> <silent> ,g - [ ] <Enter><++><ESC>kA
 97 " 下划线
 98 autocmd Filetype markdown inoremap <buffer> <silent> ,u <u></u><++><Esc>F/hi
 99 " 图片
100 autocmd Filetype markdown inoremap <buffer> <silent> ,p ![](<++>) <++><Esc>F[a
101 " 链接
102 autocmd Filetype markdown inoremap <buffer> <silent> ,a [](<++>) <++><Esc>F[a
103 " 一号标题
104 autocmd Filetype markdown inoremap <buffer> <silent> ,1 #<Space><Enter><++><Esc>kA
105 " 二号标题
106 autocmd Filetype markdown inoremap <buffer> <silent> ,2 ##<Space><Enter><++><Esc>kA
107 " 三号标题
108 autocmd Filetype markdown inoremap <buffer> <silent> ,3 ###<Space><Enter><++><Esc>kA
109 " 四号标题
110 autocmd Filetype markdown inoremap <buffer> <silent> ,4 ####<Space><Enter><++><Esc>kA
111 " 五号标题
112 autocmd Filetype markdown inoremap <buffer> <silent> ,5 #####<Space><Enter><++><Esc>kA
113 " 六号标题
114 autocmd Filetype markdown inoremap <buffer> <silent> ,6 ######<Space><Enter><++><Esc>kA
" 插入当前时间
116 autocmd Filetype markdown inoremap <buffer> <silent> ,t <C-R>=strftime("%Y-%m-%d %H:%M:%S")<CR>
117
118
119
120
121 call plug#begin()
122 Plug 'vimwiki/vimwik'
123 Plug 'connorholyday/vim-snazzy'
124 Plug 'preservim/nerdtree'
125 Plug 'iamcco/markdown-preview.vim'
126 Plug 'iamcco/mathjax-support-for-mkdp'
127 Plug 'SirVer/ultisnips'
128 Plug 'godlygeek/tabular'
129 Plug 'dhruvasagar/vim-table-mode', {'on': 'TableModeToggle' }
130 Plug 'vimwiki/vimwiki'
131 call plug#end()
```
