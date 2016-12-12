tmuxのオレオレ設定

* prefixをCtrl-tに変更
* キーバインドをviモードに変更
* vimでフルカラー表示対応

```
set -g prefix C-t
unbind C-b
bind C-t send-prefix

set-window-option -g mode-keys vi

set -g default-terminal xterm-256color
set -g terminal-overrides 'xterm:colors=256'
```

