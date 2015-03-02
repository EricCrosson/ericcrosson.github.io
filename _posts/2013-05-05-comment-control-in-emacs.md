---
layout: post
title: Comment Control in Emacs
---

This morning I realized I had not one or two but three(!) key bindings used solely for comment control. Comment manipulation is an important part of daily life, sure, but no single area of editing deserves so much keymap real estate. Converting the most commonly used command for commenting into a *dwim* command freed up real estate in my global keymap, but the real advantage is quicker reactions from the user since less thought goes into selecting the correct text-commenting command.

The three commands broke down my comment shuffling into the following actions:

1. Comment a region of text
2. Comment a single line
3. Insert a comment on the current line

Fortunately, Emacs comes with a terriffic set of built-in commands. From the doc string of `comment-dwim`:

> Insert or realign comment on current line; if the region is active comment or uncomment the region instead.

It looks like our little friend `comment-dwim` will preserve all of the above functionality except toggling individual lines. (Well it can- if you feel like marking a one-line region each time.) Instead of writing another command to keep up with something so trivial, lets see if we can enhance `comment-dwim` to do everything we want. Enter this piece of adivce:

{% gist 9b57a839af5efe611252 %}

This introduces a few changes into `comment-dwim`'s default behavior. Primarily, it is now possible to un/comment an individual line without a selected region. To do so, place the point at the beginning of the current line or the beginning of indentation before hitting `<kbd>M-;</kbd>`. Second, the region will stay active after un/commenting. This seemed to be the most natural behavior to me, after some experimentation.
