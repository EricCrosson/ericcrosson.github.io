---
layout: post
title: Advising `desktop-save-mode'
---

I find it interesting that `desktop-save` provide means for adjusting
your desktop file location, but throws you to the wolves when it comes
to fending off `directory-not-found` errors during desktop
saves. These are the pesky errors that are more likely to pop up (and
slow down the process of) bootstrapping a new host, rather than
interfering with day-to-day work. Thankfully, solutions are also of
the examine-it-once variety:

{% gist cf2395a651045ef6364c %}

Sometimes a simple guard over the black box of an object is more
satisfying than peeling back the covers for a quick patch.
