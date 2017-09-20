vimの`:terminal`でgit for windowsのbashを起動する

```vim
" ~/.vimrc
function! GitBash()
    " 日本語Windowsの場合`ja`が設定されるので、入力ロケールに設定しなおす
    let l:oldlang = $LANG
    let $LANG = systemlist('"C:/Program Files/Git/usr/bin/locale.exe" -iU')[0]

    " remote連携のための設定
    let l:oldgvim = $GVIM
    let l:oldvimserver = $VIM_SERVERNAME
    let $GVIM = $VIMRUNTIME
    let $VIM_SERVERNAME = v:servername

    " git for windowsに同梱されたvimで誤作動するので$VIMと$VIMRUNTIMEを削除する
    let l:oldvim = $VIM
    let l:oldvimruntime = $VIMRUNTIME
    let l:oldmyvimrc = $MYVIMRC
    let l:oldmygvimrc = $MYGVIMRC
    let $VIM = ''
    let $VIMRUNTIME = ''
    let $MYVIMRC = ''
    let $MYGVIMRC = ''

    " ホームディレクトリに移動する
    lcd $USERPROFILE

    " :terminalでgit for windowsのbashを実行する
    terminal ++close ++curwin C:/Program Files/Git/bin/bash.exe -l

    " 環境変数とカレントディレクトリを元に戻す
    let $LANG = l:oldlang
    let $GVIM = l:oldgvim
    let $VIM_SERVERNAME = l:oldvimserver
    let $VIM = l:oldvim
    let $VIMRUNTIME = l:oldvimruntime
    let $MYVIMRC = l:oldmyvimrc
    let $MYGVIMRC = l:oldmygvimrc
    lcd -
endfunction

nnoremap <Leader>g :<C-u>call GitBash()<CR>
```

```bash
# ~/.bashrc
if [ -x $(cygpath "$GVIM\\vim.exe") -a -n $VIM_SERVERNAME ]; then
    alias vim="$(cygpath "$GVIM\\vim.exe") --servername $VIM_SERVERNAME --remote-silent"
fi
```
