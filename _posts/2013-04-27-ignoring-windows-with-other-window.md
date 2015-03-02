---
layout: post
title: Ignoring Windows with (other-window)
---

I feel Emacs does a great job implementing features in a keyboard-oriented environment. One of the harder 'new-agey' features to implement in the modern multi-window system is window navigation. Even with prefixes, `other-window` only goes so far. [Windmove](http://emacswiki.org/emacs/WindMove) does a nice job picking up the slack, but sometimes I'm still wishing for more.

For example, when I'm using GDB, I like to have the `*input/output*` buffer open, as a reference. Usually I don't interact with my programs by feeding them text input, so when I'm doing the window dance I just want to skip over this buffer. Emacs natively provides a way to do this, but it took me a little while to figure out how.

Install the below package after pasting it into a buffer with `M-x install-package-from-buffer`. Cycling around the frame with `C-x o` will ignore any windows marked 'unselectable'. Now we can enjoy this feature without a second thought!

{% gist 895b39bf191b21962945 %}
