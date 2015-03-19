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

The variable `unkillable-scratch-behavior` defines the action taken
when a kill is attempted on a buffer matching one or more of the
regexp's in `unkillable-buffers` A value of `'do-nothing` disallows
the buffer from being killed; `'bury` buries the buffer instead of
killing it; and `'kill` kills the buffer (which is the same as
disabling the mode entirely).
