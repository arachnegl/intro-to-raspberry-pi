Shell 2 - Files
***************

Computers fundamentally only process 0s and 1s. In order for them to be useful we need to find ways to represent things that are relevant to us.

Files are the basic unit of storage. When we save to file, the information persists even after the power is switched off.

There are many types of files and many different ways to represent types of things that are relevant to us. Examples are images, videos, sound files...

We are going to look at one of the ways to represent text.

The `nano` editor
=================

There are many editors available. Perhaps the most common is Microsoft Word. Nano is much more basic.

We use simple editors as we are working at a lower level of abstraction than those typically provided by document editors such as Windows or Open Office.

launch nano::

    namo


The list of nano commands are at the bottom. `^` signifies the Ctrl key. Exit is denoted as `^X` this translates to `Ctrl + X`.


Exercise
========

Create a file named `file`, enter some text and save it.


Deleting files & directories
============================

Here are some commands to delete::

  rm my_file
  rmdir my_dir


Text as ASCII
=============

Computers need some way of representing roman characters. An industry standard which has been in use for quite some time is ASCII.

You can get some documenation on ASCII by typiing::

    man ascii

Lets create a file and use `hexdump` to inspect it::

    echo "hi" > file
    hexdump -C file
    00000000  68 69 0a                                          |hi.|
    00000003


Exercise
========

What do the numbers 68 69 0a represent?
Map them to characters using `man ascii` as reference


Compiling C programs
====================

C is a programming language. Most Linux software is written in it.

We will touch very briefly on how to compile a C file. The goal is just to give a flavour of whats going on. We don't want any hidden magic.

Run through with outputs as comments::

    cd /opt/vc/src/hello_world
    ls                            # Makefile  world.c
    nano world.c
    make
    ls                            # hello_world.bin  Makefile  world.c
    ./hello_world.bin             # Hello world!

Exercise
========

Using `less` read the README file in `/opt/vc/src/`.

Find other programs that you'd like to compile and run.

`hello_teapot` and `hello_video` are recommended.

run `hexdump` on some to ensure they are just ASCII files.

Do poke around!


Recap
=====

We know how to:

* edit files with `nano`
* rename or delete files and directories with `mv`, `rm`, `rmdir`
* inspect a file almost at its lowest level
* we have a notion of how to represent characters in binary
* we can compile C programs
