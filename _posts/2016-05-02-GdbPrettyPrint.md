
---
layout: post
title: GDB Pretty Printers in Python for  Lua
---

Custom GDB Pretty Printers are super useful, especially when you are hacking on someone elses code. 
For instance, at the moment and am messing with the guts of Lua. It's well written but super
terse code. A couple pretty printers later and the super efficient but higly cryptic union data structures
are unwrapped and displayed in a meaningful way as I am debugging.

Unfortunately, the documentation for writing these is spase. A couple pages of API, a couple blog posts with 
some examples, and that's it.

I'm using KDevelop as my IDE, which integrates gdb pretty well, but adds a layer of mystery to what's going 
on with your pretty printer code.

Here's a couple useful breadcrumbs:

---

The code gets loaded from:

    ~/.gdbinit

---

You can see if your python is being correctly interpreted correctly by running gdb from the command line
and looking for some python error code followed by `/home/teh/.gdbinit:11: Error in sourced command file:`
if something went wrong.

---

`try except` is your friend. KDevelop will just print exception messages in the watch list.

---

I have problems trying to prettyprint typedefs of native types. A useful workaround is to create a temporary
pointer to the value you want to inspect as the prettyprinter works for pointers to typedefs of native types.

---

The helper code by kevin funk is handy. https://github.com/krf/dotfiles/blob/master/.gdb/printers/helper.py

