--- 
layout: post
tags: 
- cross-compiling
- gcc
- llvm
- metta
- Clang
title: Clangestine
---
Finally, Clang people have enabled C++11 lambda support in clang and I'm busy
hurrying my buildsystem into clang support for everything. I'm tired of
endlessly autoconfiguring and building crossgcc for a bunch of different
targets. Adding a target with some include paths set up for my OS into the
clang frontend seems like a much simpler idea.
