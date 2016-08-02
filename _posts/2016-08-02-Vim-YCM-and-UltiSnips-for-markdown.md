---
layout: post
title: "Vim and UltiSnips/YouCompleteMe for Markdown documents"
date: 2016-08-02 22:20:04 +0200
categories: vim
---

I have Vim and [YouCompleteMe](https://valloric.github.io/YouCompleteMe/)
configured and working when I write code. I also like to use the
[UltiSnips](https://github.com/SirVer/ultisnips) plugin to use snippets.

Now I wanted to be able to use custom snippets when editing my markdown document
(speciffically a small snippet to include the *Front Matter* for
[Jekkyl](https://jekyllrb.com) posts).

The first problem was that YouCompleteMe is by default deactivated for markdown
documents. The *blacklist* can be fixed in your `vimrc`:  

```
let g:ycm_filetype_blacklist = {}
```

You can also be more specific in the files that you want to include,
specifically I actually don't want YouCompleteMe to run while writing emails
(that may change actually... it can be useful sometimes). The default configuration
for the blacklist is:  

```
let g:ycm_filetype_blacklist = {
      \ 'tagbar' : 1,
      \ 'qf' : 1,
      \ 'notes' : 1,
      \ 'markdown' : 1,
      \ 'unite' : 1,
      \ 'text' : 1,
      \ 'vimwiki' : 1,
      \ 'pandoc' : 1,
      \ 'infolog' : 1,
      \ 'mail' : 1
      \}
```

Now YouCompleteMe should work in your markdown document. The problem is that it
does suggest a lot of words (so called *identifiers*) and I really just want the
snippets.

This is not currently supported by YouCompleteMe (or I haven't found it in the
doc) but there's an easy workaround. I add a `filetype` configuration file for the
markdown files : `~/.vim/ftplugin/mardown.vim` and set the minimum length of
*identifiers* to some big number (99). This way only identifiers that are longer
than 99 characters will be suggested, and this doesn't happen often.

```
let g:ycm_min_num_identifier_candidate_chars = 99
```

This configuration will only be applied to markdown files. Make sure you have
`filetype plugin indent on` activated in your `vimrc`.
