---
layout: post
title:  "Vim encryption"
date:   2016-07-04 09:02:02 +0200
categories: vim
---

I use the built-in encryption method of Vim to save some files. By default the
encryption algorithm is fairly weak (zip), this can be changed by setting `blowfish2`
in your `vimrc`:  

```
set cm=blowfish2
```

More info `:help cryptmethod`.
