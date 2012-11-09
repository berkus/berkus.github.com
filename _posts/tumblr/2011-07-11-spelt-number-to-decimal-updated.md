--- 
layout: post
tags: 
title: Spelt Number to Decimal (Updated)
---
[arachneng](http://j.mearie.org/post/7462182919/spelt-number-to-decimal):

> This post is last updated in 2011-07-11 13:20 UTC.

>

> I certainly like a code obfuscation and golfing: the recent example includes
[this](http://j.mearie.org/post/1181041789/brainfuck-interpreter-in-2-lines-
of-c) and [this](http://cosmic.mearie.org/2010/12/ika5k/). The today’s project
is more like the former, where very short code takes much time to explain.
Without further ado, here it is: ([Gist](https://gist.github.com/1074852))

>

> This little program reads a spelt number from the standard input and writes
the corresponding number to the standard output. It supports numbers up to
1015-1 and still weighs only <del>256</del> **243** bytes of C, if you ignore
the backslash at the end of line which just wraps the line. (There is also a
[shorter version](https://gist.github.com/1074852#file_spokennum_short.c) that
can handle up to 19,999,999 and does not use `long long`.) The input should be
correct, although it will handle “a” and “and” correctly and ignore some
invalid words.

>

> It assumes the ASCII character set and 2’s complement representation, and
requires `int` and `long long` to be at least 32 and 64 bits long, but that’s
all they expect from the compiler. For example, it does not matter whether
`char` is signed or unsigned, EOF does not have to be -1, and so on. (Yes, I
_did_ keep it in mind while writing this program.)

>

> While I left the explanation of the BF interpreter as a reader’s exercise,
in this time I’ll give a detailed explanation of the program. Keep in mind
that there are two versions of the program; the explanation is primarily for
the longer version.

>

> [Read More](http://j.mearie.org/post/7462182919/spelt-number-to-decimal)

Yippie!
