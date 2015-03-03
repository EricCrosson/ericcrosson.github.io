---
layout: post
title: Adios, Dvorak
---

Right when my typing skills were improving from 'noob,' my sister started using the Dvorak keyboard layout. She said she was terrible at QWERTY, and relearning from scratch the muscle memory required by typing was easier than breaking old habits. That's as may be, but it sure is inconvenient. I have considered to make the switch before, but have never gotten past the first couple half-hours of typing tutorials. My sister has admitted to being plagued by the simple task of driving another computer; as her Dvorak skills sharpened her QWERTY went down the drain.

I reexamined my desire to use another keyboard layout, instead asking what deficiencies I found with QWERTY. The only real grievance I could muster was that the delimeters used in programming, ({[ ]}), were awful far from home sweet home and demanded the contortion of one's fingers. I recently devised a method to provide home-row delimeters, if not everywhere at least right where it helps the most. Whipping up a bit of emacs lisp*,

{% gist 54cb70705fd64d9e67d6 %}

These anonymous functions grant me the ability to insert any delimeter of my liking, quick as a snap. If you remap the cantankerous Caps Lock with a much more functional Ctrl, that is.

Edit:

Before I posted this, I looked at the duplicated code with disdain. I tried to diminish the sizable block I had written, but couldn't get it down any more without loss of structure. I was convinced there was a better way in this language I've been growing increasingly fond of, trouble was, I didn't know how to create it. I decided it was time to sit down and read the manual.

I noticed that Paul Graham, the author of a [captivating article](http://www.paulgraham.com/avg.html) I was reading, had mentioned writing a book on [Common Lisp](http://www.amazon.com/ANSI-Common-LISP-Paul-Graham/dp/0133708756). How can that not be a sign? I obtained a copy of his book and shortly came across this passage.

> Donald Knuth called his classic series The Art of Computer Programming. In his Turing Award Lecture, he explained that this title was a conscious choice—that what drew him to programming was "the possibility of writing beautiful programs."

> Like architecture, programming has elements of both art and science. A program has to live up to mathematical truth in the same way that a building has to live up to the laws of physics. But the architect's aim is not simply to make a building that doesn't fall down. Almost always the real aim is to make something beautiful.

> Some programmers feel, like Donald Knuth, that this is also the real aim of programming. Almost all Lisp hackers do. The spirit of Lisp hacking can be expressed in two sentences. Programming should be fun. Programs should be beautiful. That's the spirit I have tried to convey in this book.

> Paul Graham

This appeals to me, but I will elaborate on ideas in a different post. For now, this is what I've learned from ANSI Common Lisp. Lisp has the ability, like some other languages, to write code that will be expanded before evaluation. These snippets are macros, and add another layer of abstraction to Lisp. Instead of explicitly writing code three times, I expand the actions I want to perform with one common macro. The result looks something like this:

{% gist ea5a6f5df84ad897216b %}

The macro churns out code defined by the macro's parameters, which in this case allow for enough flexibility to throw in the "-&gt;" symbol. I've been looking for a nice way to do this, since my initial attemps with abbrev-mode ended in failure. This solution is scalable and personal enough to find a steady home in my config files. Even though it doesn't look like it, this code can still fit on one line and is 80-char compliant, so it comes out to be shorter and more extensible than the former solution.

* Well, that's not *exactly* verbatim from my .emacs, but we'll get to that in a [later post](http://todo.org).
