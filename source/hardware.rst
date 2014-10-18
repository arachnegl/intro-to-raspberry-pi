Getting Started
***************

Hardware Components
===================

.. image:: _static/images/rpi-tech-spec.jpg


Exercise
========

Which components do you expect to find in the following computers:

* desktop
* laptop
* mobile
* tablet

What makes the Raspberry Pi special?

Start up
========

There is no power on/off button. You simply add or remove power.

After the computer is finished loading the operating system you land in the shell.

Shell welcome message::

    Linux raspberrypi 3.12.22+ #691 PREEMPT Wed Jun 18 18:29:58 BST 2014 armv6l

    The programs included with the Debian GNU/Linux system are free software;
    the exact distribution terms for each program are described in the
    individual files in /usr/share/doc/*/copyright.

    Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
    permitted by applicable law.
    Last login: Tue Oct 14 18:43:45 2014 from 192.168.0.6
    pi@raspberrypi ~ $

The `pi@raspberrypi ~ $` is called a prompt. You type commands after the '$'.

System configuration `raspi-config`
===================================


Type::

    pi@raspberrypi ~ $ startx


and you will get::

    ┌─────────┤ Raspberry Pi Software Configuration Tool (raspi-config) ├─────────┐
    │ Setup Options                                                               │
    │                                                                             │
    │    1 Expand Filesystem             Ensures that all of the SD card          │
    │    2 Change User Password          Change password for the default          │
    │    3 Enable Boot to Desktop/ScratchChoose whether to boot into a de         │
    │    4 Internationalisation Options  Set up language and regional set         │
    │    5 Enable Camera                 Enable this Pi to work with the          │
    │    6 Add to Rastrack               Add this Pi to the online Raspbe         │
    │    7 Overclock                     Configure overclocking for your          │
    │    8 Advanced Options              Configure advanced settings              │
    │    9 About raspi-config            Information about this configura         │
    │                                                                             │
    │                                                                             │
    │                    <Select>                    <Finish>                     │
    │                                                                             │
    └─────────────────────────────────────────────────────────────────────────────┘

Exercise
========

Explore the options that you have.

What are the similarities and differences with this from Mac OSX?

.. image:: _static/images/mac-sys-prefs.png


Starting the Desktop
====================

The shell is one interface. A graphic user interface is another.

Type this to start the GUI::

    pi@raspberrypi ~ $ startx

Exercise
========

We are going to focus on using the shell (command line).

Find:

* the Terminal
* a browser
* anything else you would typically use.

Recap
=====

* The Raspberry Pi is a general purpose computer.
* However it exposes a lot that is typically hidden.
* Use `raspi-config` for a convenient way to configure your computer.
* Use `startx` to start the GUI

We will return to hardware later in the electronics section.
