--- 
title: April Fools or?
layout: post
tags:
- osdev
- qt4
- dailywtf
---
What did this neanderthal think?

{% highlight c++ %}
/usr/include/qt4/QtCore/qsharedpointer_impl.h:595:43: error: field 'd' is
      uninitialized when used here [-Werror,-Wuninitialized]
    inline QWeakPointer(X *ptr) : d(ptr ? d->getAndRef(ptr) : 0), value(ptr)
                                          ^
{% endhighlight %}
