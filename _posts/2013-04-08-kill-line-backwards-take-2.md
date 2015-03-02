---
layout: post
title: Kill Line Backwards -- Take 2
---

Over at [Emacs Redux](http://emacsredux.com), Bozhidar Batsov has been shredding it up with post after post. Today he posted his take on how to quickly access a [reverse kill-line](http://emacsredux.com/blog/2013/04/08/kill-line-backward/). I immediately took his advice and remapped the (redundant) `C-Backspace` to `(kill-line 0)`, but was a little unsatisfied with its behavior. This is undoubtedly because of my new appreciation for `kill-whole-line`, which I feel makes `C-k` behave a lot more reasonably. Isn't the goal fewer keystrokes after all? To mimic this hungry behavior with our new `backwards-kill-line` let's make some modifications. Since `(kill-line 0)` can't interpret numerical prefixes, I'd like to add that convenience on my own.

{% gist 1dc0bccadab44220ec3b %}

Code documentation makes Emacs possible. so check out the doc string for a feel of what this command does. In the true Emacs spirit, the kill-ring stores killed text for later yanking.
