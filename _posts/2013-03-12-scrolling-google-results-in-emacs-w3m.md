---
layout: post
title: Scrolling Google Results in Emacs w3m
---

As my [previous post](http://ericscrosson.wordpress.com/2013/03/08/burying-the-compilation-buffer/) hinted, I have been spending more time in Emacs-w3m as of late. Some of you may ask "why," as in "why use a text browser when you can use chromium," and if you haven't seen the light yet my reasons are as follows:

1. My eyes thank me.

	I use [bliss color theme](https://github.com/Emacsfodder/Emacs-bliss-theme), and this allows me to view any web page without manually contract my pupils. Sure, it's possible to stick to [high contrast in chrome too](https://chrome.google.com/webstore/detail/high-contrast/djcfdncoelnlbldjfhinnjlhdjlikmph), but why start the compounding process of adding (untrusted) software to improve on other not-good-enough software when I already have Emacs open?

2. Memory efficiency- I already have Emacs open.

	When I used a MacBook, my battery life under the best of conditions was a mere 2 hours. (On my ThinkPad x230 I get an easy 12+.) I noticed that Chromium in addition to the operating system consumed 70% or more of available memory. When a computer is continually forced to update its entire supply of volatile memory, battery life understandably tanks. With my MacBook, it became a matter of keeping Chrome closed if I wanted my laptop to last through a single lecture.

3. Every page is a buffer.

	That is, each page is a [first-class citizen](https://sites.google.com/site/steveyegge2/effective-Emacs). Syntax highlighting, searching, copying, editing-then-copying, copying-then-editing, and more. If you can do it in Emacs, you can now do it in Emacs on the web. Take code evaluation for example, possible straight from the browser (which is really the equivalent of a kid scraping bubble gum off the sidewalk and sticking it in his mouth, but in both situations, convenience is paramount).

4. Minimal bandwidth requirements.

	My first internet connection (until 2008!) was a dial-up connection. Even though I've left those speeds behind, bandwidth hogs are persona non grata. UT only permits underlings like myself are a paltry 500MB bandwidth limit -- per week. Thankfully, I don't suffer with the rest of the Luddites. With Emacs, it's trivial to ssh into a remote host (say, one that isn't monitored for bandwidth, at a remote location) and browse without fear of throttling, thought police, or bandwidth consumption.

5. Emacs-Lisp extensions

	{% gist a5fbd76a3a896267583c %}

    Now, after I press `C-x j` to open a google query, I can quickly scroll through the results with `n` and `p`. This replaces my previous methods of jumping around google with [ace-jump mode](http://www.Emacswiki.org/Emacs/AceJump) and a modified `(next-line)` that jumped 6 lines instead of one.

    I am wary of this code- I find it highly unlikely that this is the first attempt to write code that performs the same task. But it was so trivial to write, and it is so helpful, I couldn't resist.

Bit by bit, Emacs is conforming to my ideal working tool.
