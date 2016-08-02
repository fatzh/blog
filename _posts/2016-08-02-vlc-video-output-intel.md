---
layout: post
title: "Intel graphic and VLC"
date: 2016-08-02 20:11:34 +0200
categories: linux
---

My Thinkpad X230 is equiped with an Intel graphic card. VLC works fine when
setting the following options in the **Tools > Preferences** menu:

**Video > outpute** to **OpenGL GLX video output(XCB)**  
**Input/Codecs > Hardware-accelerated decoding** to **VA-API video decoder via
X11**

This fixes the fullscreens annoying issue where the video is not actually
expanded to the size of the screen.
