---
layout: post
title: Experimenting with Tail Call Elimination
---

It should be no great secret that I have been thoroughly enjoying Mark Jason Dominus' [Higher Order Perl](http://hop.perl.plover.com/#free). I downloaded it gratis online and have found it immediately captivating.

One of the great ideas included in this manifest is a method to eliminate most recursive functions. I suppose Dominus didn't have time waiting around for slow recursive functions in already-slow Perl, so he grew crafty. And crafty means saving cycles, which I always support.

Dominus notes most recursive functions have a call stack much like this one:

```python
call gcd(48, 20)              # Call A
     call gcd(20, 8)          # Call B
     	  call gcd(8, 4)      # Call C
	       call gcd(4, 0)     # Call D
	       	    return 4
	       return 4
          return 4
      return 4
```

This code and execution path may satisfy [Euclid's algorithm](http://en.wikipedia.org/wiki/Euclidean_algorithm), but there is one glaring instance of repetition -- the return chain of identical values. Dominus takes advantage of the beautiful, flexible syntax Perl offers with the following example:

https://gist.github.com/f451bbb891572c5fba8e

This provides the same functionality as the recursive method, but without excessive pushes on the stack, or jumps when returning up the rabbit hole.

And thus, we reap benefits! With a simple paradigm shift mentally, we may conclude the same algorithm with much less overhead. I'm not sure why this is the first source I've seen preaching this technique. Many of my past teachers were advocates of recursion and the puzzles that students face learning recursive programming, and this seems to be applicable to a large number of problems.

What is the advantage of using this technique as opposed to old-fashioned, time-tested recursion? Well, in order to answer that question I wrote a script to run some benchmarking tests.

My recursive implementation of Euclid's algorithm is as follows:

https://gist.github.com/8b5dc6a15679f159f7fc

My tail call implementation is the same as the example in the first half of this article.

Running the following, in bash:

```bash
time ./recursion 120 480

real	0m0.154s
user	0m0.009s
sys	    0m0.000s
```

And the optimized function:

```bash
time ./norecursion 120 480

real	0m0.013s
user	0m0.003s
sys	    0m0.000s
```

Holy wow! With such small arguments too!

With just a little bit of cleverness, the workload is decimated. Which is a good thing! Because we wouldn't want to run *out* of precious clock cycles, would we?
