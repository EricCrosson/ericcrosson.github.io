---
layout: post
title: M-x unkillable-scratch
---

Today package
[unkillable-scratch](https://github.com/EricCrosson/unkillable-scratch)
(available on melpa) becomes a general package for disallowing buffers
from being killed by regexps.

No longer is the `*scratch*` buffer the sole recipient of
`unkillable-scratch`'s aegis.  The variable `unkillable-buffers`
contains a list of regexps that will prevent any matching buffer from
dying during an invocation to kill-buffer.

More features will be released shortly, as they are developed.
