---
layout: post
title:  ":w with sudo from within Vim"
date:   2016-07-10 16:13:31 +0200
categories: vim
---

When editing a read only file you want to save, you can automatically sudo from
within vim to write the file. Add this to your `vimrc`:  

```
cmap w!! w !sudo tee % >/dev/null
```

This way, when editing a read-only file, you can save your change by typing
`:w!!`. You will be prompted to enter your credentials and the file will be
reloaded.
