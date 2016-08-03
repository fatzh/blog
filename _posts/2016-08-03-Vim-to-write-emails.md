---
layout: post
title: "Emails formatting in Vim and Mutt"
date: 2016-08-03 19:32:40 +0200
categories: mutt, vim
---

I use vim to write my emails in mutt and just noticed that the nice 80 char
formatting looks pretty bad when you read the email on a mobile.

This can be fixed by using the *flowed* format option in your `.mutrc`:

```
set text_flowed = yes
```

Also change your formatting option in vim, for the filetype `mail` by setting
the following option in your `.vimrc` or `~/.vim/ftplugin/mail.vim`:

```
setlocal fo+=aw
```

For more info on the `fo` option, that's the `formatoption` settings and the
different options can be seen in the vim help:

```
:help formatoptions
:help fo-table
```

To write emails, my current vim config set the text width to 80 chars,
automatically wraps and activates the spell checker.

```
autocmd FileType mail setlocal textwidth=80 wrap spell fo+=aw
```
