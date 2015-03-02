---
layout: post
title: Scrolling Google Results in Emacs w3m
---

As my [previous post](http://ericscrosson.wordpress.com/2013/03/08/burying-the-compilation-buffer/) hinted, I have been spending more time in emacs-w3m as of late. Some of you may be stuck on the "why," as in "why use a text browser when you can use chromium," and if you haven't seen the light yet my reasons are as follows.

1. My eyes thank me.

	I use [wombat+ color theme](http://jaderholm.com/color-themes/color-theme-wombat+.el), and this means any web page can be viewed without having to manually contract my pupils. Sure, I stick to [high contrast in chrome too](https://chrome.google.com/webstore/detail/high-contrast/djcfdncoelnlbldjfhinnjlhdjlikmph), but why start the compounding process of adding (untrusted) software to improve on other not-good-enough software when I already have Emacs open?

2. Saves memory- I already have emacs open.

	When I used a MacBook... wow, it's tough thinking back to those Dark Times. But when that's all I had, my battery life under the best of conditions was a mere 2 hours. (Now, on my ThinkPad, I get an easy 12+.) I noticed that Chrome, in addition, regularly consumed 70% or more of the available memory. What is to be expected when a laptop is continually forced to update its entire supply of volatile memory..? Battery life tanks. With my MacBook, it indeed became a matter of keeping Chrome closed if I wanted my laptop to last through a single class.

3. Each page is a buffer.

	That is, each page is a [first-class citizen](https://sites.google.com/site/steveyegge2/effective-emacs). Syntax highlighting, searching, copying, editing-then-copying, copying-then-editing, and more. If you can do it in Emacs, you can now do it in Emacs on the web. Take code evaluation for example, possible straight from the browser (which is really the equivalent of a kid scraping bubble gum off the sidewalk and sticking it in his mouth, but in both situations, the convience can't be beat).

4. Nothing but text = minimal bandwidth requirements.

	My first internet connection (until 2008!) was a dial-up connection. Even though I've left those speeds behind,  sometimes bandwidth hogs are persona non grata. At UT, underlings like myself are kept in line with a paltry 500MB bandwidth limit- per week. It's all about that payday to them; thankfully, I don't have to suffer. With emacs, it's also trivial to ssh into a remote host (say, one that isn't monitored for bandwidth, at a remote location) and browse without fear of throttling, thought police, whatever.

5. Extending functionality is as easy as elisp.

	{% gist a5fbd76a3a896267583c %}
  Now, after I press `C-x j` to open a google query, I can quickly scroll through the results with `n` and `p`. This replaces my previous methods of jumping around google with [ace-jump mode](http://www.emacswiki.org/emacs/AceJump) and a modified `(next-line)` that jumped 6 lines instead of one.

I am wary of this code- I find it highly unlikely that this is the first attempt to write code that performs the same task. But it was so trivial to write, and it is so helpful, I couldn't resist. Bit by bit, emacs is conforming to my ideal working tool.
