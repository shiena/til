tmuxのオレオレ設定

* prefixをCtrl-tに変更
* キーバインドをviモードに変更
* vimでTrue Color表示対応

.tmux.conf
```
set -g prefix C-t
unbind C-b
bind C-t send-prefix

set-window-option -g mode-keys vi

set -g default-terminal "screen-256color"
set-option -ga terminal-overrides ",xterm-256color:Tc"
```

.vimrc
```
if (has('termguicolors'))
	set termguicolors
	let &t_8f = "\<Esc>[38;2;%lu;%lu;%lum"
	let &t_8b = "\<Esc>[48;2;%lu;%lu;%lum"
endif
```

tmux起動オプション
```
tmux -2
```

refs: http://qiita.com/yami_beta/items/ef535d3458addd2e8fbb
