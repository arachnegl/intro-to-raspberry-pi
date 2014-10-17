Shell 1 - Navigation
********************

Everyone is used to the current visual metaphor of interacting with a computer. Images
represent things such as files, programs, and folders. Windows act as
containers where programs live.

The command line is another way of doing much the same. Instead of using
a mouse and clicking, we type commands. It can do everything a Graphical User
Interface (GUI) can do but more.

We are going to introduce the basic of this programming language. As we
progress always keep in mind what the equivalent way of doing things would be
in the GUI.


Start up
========

start up message::

    Linux raspberrypi 3.12.22+ #691 PREEMPT Wed Jun 18 18:29:58 BST 2014 armv6l

    The programs included with the Debian GNU/Linux system are free software;
    the exact distribution terms for each program are described in the
    individual files in /usr/share/doc/*/copyright.

    Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
    permitted by applicable law.
    Last login: Tue Oct 14 18:43:45 2014 from 192.168.0.6
    pi@raspberrypi ~ $

The `pi@raspberrypi ~ $` is called a prompt. You type commands after the '$'.


`echo Hi` - Print to screen
===========================

It is a tradition in computing tutorials to teach how to print 'Hello World'.

Type this::

    pi@raspberrypi ~ $ echo "Hello World"


Location
========

You are always somewhere in the computer's filesystem. You can get lost, but its always easy to find out where you are.

Type this::

    pi@raspberrypi ~ $ li
    pi@raspberrypi ~ $
    pi@raspberrypi ~ $ ls
    Desktop  Documents  my_turtle.py  networking-lessons  ocr_pi.png  python_games  Scratch
    pi@raspberrypi ~ $ pwd
    /home/pi

Note the prompt helps you remember where you are. Here `~` represents the current users' home directory.


Users
=====

You are a user. Every user needs a name. The default users is `pi`.

If you ever forget who you are, ask::

    pi@raspberrypi ~ $ whoami


Navigation
==========

Just like we are used to navigating using our mouse and clicking on folders, we can do the same in the shell.

Type the following. At each step explain what it is doing::

    pi@raspberrypi ~ $ cd python_games
    /home/pi
    pi@raspberrypi ~/python_games $ pwd
    /home/pi/python_games
    pi@raspberrypi ~/python_games $ ls
    [... lots of files, many ending in .py ...]

Note navigation gets easier if you keep a mental image in your head of where you are. Visually, a file system is just like a tree. There is a root and the branches are folders, the files are leafs. We will install a program to help.

Note also that the prompt tells you where you are relative to the `home` directory. Your home directory is your users' home. An absolute location is the location of a file or folder in terms of the root of the computer's file system.


Building a file system
======================

Lets build a file structure to manage a music collection::

    ~ $ mkdir music
    ~ $ cd music
    ~/music $ ls
    ~ $ ls
    ~/music $ mkdir rock classical jazz
    ~/music $ ls
    classical  jazz  rock
    ~/music $ cd rock
    ~/music/rock $ ls
    ~/music/rock $ touch albums.txt
    ~/music/rock $ ls
    rock.txt
    ~/music/rock $ cat rock.txt
    ~/music/rock $ echo "Beatles - The White Album - 1968" > rock.txt
    ~/music/rock $ cat rock.txt
    Beatles - The White Album - 1968
    ~/music/rock $ cd ..
    ~/music $ pwd
    /home/pi/music


man the docs & `less`
=====================

We have seen the following commands: ls, mkdir, cat, touch, pwd

To inspect the documentation for a command try::

    ~ $ man ls

Welcome to `less`. This is what is called a pager. It's a file reader, a bit like a very lite browser for your desktop.

Some `less` commands::

  `space`        up a page,
  `w`            up a page
  `q`            exit
  `h`            help on many other commands (displayed in `less` of course)


Exercise
========

For each command we have seen inspect the man documentation. Parse the many options. Write in one sentance what it does.


Exercise
========

Complete the above music collection database. Ensure that each music category folder has its own file with at least one album example in it.

The end result should look like this::

    ~ $ tree music/
    music/
    ├── classical
    │   └── albums.txt
    ├── jazz
    │   └── albums.txt
    └── rock
        └── albums.txt


Installing software & the `tree` program
========================================

`cd` followed by `ls` to explore directories quickly becomes repetitive.
`tree` is a program that gives us a snapshot of a directory and its contents.

First we need to install it. Typically you are used to browsing for software, downloading it and then clicking on a package to install it. You may also have to answer some questions.

Things are similar in linux except the vast majority of software exist in vast centralised repositories. This is thanks to the open source nature of most Linux software.

http://www.raspbian.org/RaspbianRepository

In Linux we use `apt-get` to install new software::

  sudo apt-get install tree

Not any user can install software. The sudo part is to have permissions to install new software. You may need to enter your password.

Now we can take a look at our creation::

  tree music



Grouping commands in a file
===========================

So far we have been programming interactively, executing one command at a time. It would be useful to group commands so that they can be executed together. It would also be useful so as not to forget the useful sequence of commands.

We do this by writing commands in a file and executing that file.

Create a file named `make-jazz.sh` and insert this::

  mkdir jazz
  cd jazz
  touch albums.txt
  echo "Miles Davis - Kind of Blue - 1959" > albums.txt

To execute `make-jazz.sh` you will have to specify that it is executable::

  chomod +x make-jazz.sh

Now we should be able to run the program::

  ./make-jazz.sh

The `./` prefix indicates where to find the program to the shell. Effectively it means run the make-jazz.sh command which is here (`.`).


Exercise:
=========

Using a file, program the creation of your music collection.

Tip: You will have to put a lot of what we did above into the file.

Recap
=====

Using the command line, we have seen:

* How to locate ourselves and navigate the file system using `ls`, `pwd`, `cd`, `tree`
* Create and remove folders and files using `mkdir`, `deldir`, `touch`, `rm`
* Print stuff to the line using `echo`, `cat`
* Read files and documentation using `man`, `less`
