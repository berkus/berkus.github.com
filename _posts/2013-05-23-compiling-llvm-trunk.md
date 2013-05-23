--- 
title: Compiling LLVM trunk
layout: post
tags:
- compilers
- clang
- trunk
- llvm
- howto
---
Just a very simple thing to try and build Clang with polly, LLVM, libcxx, lldb and lld from trunk. Isn't it?

Using git, because cloning a git repo with full history is still faster than checking out svn repo with serf. Yay!

These instructions are not for copy-paste, they show general idea and should work with minor changes.

{% highlight console %}
$ mkdir workspace && cd workspace
$ git clone http://llvm.org/git/llvm.git
$ cd llvm/tools
$ git clone http://llvm.org/git/clang.git
$ cd clang/tools
$ git clone http://llvm.org/git/clang-tools-extra.git
$ cd ../.. # back in llvm/tools
$ git clone http://llvm.org/git/polly.git
$ git clone http://llvm.org/git/lld.git
$ git clone http://llvm.org/git/lldb.git
$ cd ../.. # back in workspace
$ git clone http://llvm.org/git/libcxx.git
{% endhighlight %}

Install cloog for polly. This is as per polly's installation instructions.

{% highlight console %}
$ ./llvm/tools/polly/utils/checkout_cloog.sh workspace/cloog-src
$ cd workspace/cloog-src
$ ./configure --prefix=/Users/berkus/Tools/cloog
$ make && make install
{% endhighlight %}

Apply some patches that I had to do to make things build nicely.

They are here:
[libc++ patch](http://llvm.org/bugs/show_bug.cgi?id=16123) |
[compiler-rt OSX patch](http://llvm.org/bugs/show_bug.cgi?id=16124) |
[lldb patch](http://llvm.org/bugs/show_bug.cgi?id=16125)

Now create a build configuration:

{% highlight console %}
$ mkdir workspace/llvm/_build_
$ cd llvm/_build_
$ cmake -G Ninja -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/Users/berkus/Tools/clang-git -DCMAKE_PREFIX_PATH=/Users/berkus/Tools/cloog/ -DCMAKE_CXX_FLAGS="-std=c++11 -stdlib=libc++" ..
{% endhighlight %}

Then build everything. This shall build around three thousand files, excluding libc++ which is built separately.

{% highlight console %}
$ ninja
{% endhighlight %}

Grab a coffee and watch ninjas in action for a while.

Now build libc++. I opted to install it to a separate directory ... TODO: figure out default clang search paths for libc++ and install there..

{% highlight console %}
$ cd workspace/libcxx/_build_
$ cmake -G Ninja -DCMAKE_INSTALL_PREFIX=/usr/local/opt/libcxx ..
$ ninja install
{% endhighlight %}

This will still need some DYLD_LIBRARY_PATH tweaking (for lldb), but in general clang should work. It will not work with OSX default libc++; that's why you need to build a fresher one.

