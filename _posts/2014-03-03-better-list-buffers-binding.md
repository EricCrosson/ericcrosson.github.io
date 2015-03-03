---
layout: post
title: Better (list-buffers) binding
---

I've finally found it! Although `list-buffers`' big brother [ibuffer](http://www.emacswiki.org/emacs/IbufferMode) has some [interesting](https://github.com/purcell/ibuffer-vc) uses, I never used it much. Each invocation was accidental and flow-crushing; tools like [midnight mode](http://emacs-fu.blogspot.com/2010/03/cleaning-up-buffers-automatically.html) reduce the need for mass buffer manipulation. [Hershal](https://github.com/hershal) gave me the bright idea of unbinding `C-x C-b`, but I never found a function fitting of the freed binding.

Until today, browsing the [EmacsWiki](http://emacswiki.org/emacs/) I discovered a [little gem](http://emacswiki.org/emacs/InteractivelyDoThings#toc6). Here she is after conforming to my configs:

{% gist 02e2059d2b3a34f0f487 %}

The symmetry with `C-x b` pleases me. Maybe I'll even swap `ido-switch-buffer` and this new defun if I use the latter more frequently.
