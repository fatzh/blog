---
layout: post
title:  "Redraw Vim screen"
date:   2016-07-05 10:12:31 +0200
categories: vim
---

To redraw the vim screen if something weired is displayed (after opening a
binary file by mistake, or scrolling with tmux open...) you don't have ot
restart Vim. Simply use the command `:redraw!`. I mapped that to `<leader>r` in
my `vimrc`.

```
map <leader>r :redraw!<CR>
```
