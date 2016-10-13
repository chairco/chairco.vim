# chairco.vim
This is chairco's vim setting

# 安裝方式 1
安裝懶人包，從 https://github.com/chusiang/vimrc 這邊 clone 一份，然後在加目錄底下直接 make。
但要注意第一次安裝可能要註解 Makefile 裡面的 backup 檔案。

# 安裝方式 2
依照順序安裝：

## 先安裝 Neobundle, 是一套 vim 的套件管理工具

建立 bundle 目錄。
`$ mkdir -p ~/.vim/bundle`

下載 Neobundle plugin
`$ git clone git://github.com/Shougo/neobundle.vim ~/.vim/bundle/neobundle.vim`

建立 `~/.vimrc` 並新增下列程式碼
```
" Source a global configuration file if available
for CONFIG in split(glob('~/.vim/vimrc.d/*.vim'), '\n')
   exe 'source' CONFIG
endfor

" = NeoBundle (Vim plugin manager) =
filetype off                   " required!

"use git:// as bundle default protocal
"let g:vundle_default_git_proto = 'git'

if has('win32')
    set rtp+=%UserProfile%\vimfiles/bundle/neobundle.vim/
else
    set rtp+=~/.vim/bundle/neobundle.vim/
endif


call neobundle#begin(expand('~/.vim/bundle/'))

" Let NeoBundle manage NeoBundle
" Required:
NeoBundleFetch 'Shougo/neobundle.vim'

" My Bundles here:
source ${HOME}/.vim/plugin-list.vim

call neobundle#end()

" Required:
filetype plugin indent on     

"
" Brief help
" :NeoBundleList          - list configured bundles
" :NeoBundleInstall(!)    - install(update) bundles
" :NeoBundleClean(!)      - confirm(or auto-approve) removal of unused bundles

" Installation check.
NeoBundleCheck

"set wrap
source ~/.vim/vimrc.d/keymap.vim

```

執行 Vim 並在 vim 內使用 :NeoBundleInstall 安裝各個 plugin。



