---
layout: post
title:  "Preview markdown files from Vim"
date:   2016-07-30 17:13:31 +0200
categories: vim
---

To preview a markdown file in Vim, use `pandoc` to do the conversion,  and `bcat` to pipe the output to a browser window. Then in `vimrc` add the following map:  

```
map <leader>m :!pandoc % <bar> bcat <CR>
```
`<bar>` is the `|` (pipe) command in vim.

This way, just y pressing `<leader>m` I can preview the converted markdown
document.
