# Sunday Hack-a-Thon Log


## 5 AM

Woke up, jazzercised, ate half a mellon.


## 7 AM - Back at it

The GCC `make` succeeded.  Now for `make install` and to try Linux API headers again.


## 7:15 AM - glibc

Okay, I am trying glibc again. Which me luck.

I also just found out that (I think) I can do `make -j 4` and run the build in parallel.

1. I didn't know GCC allowed for parallel compiles!
2. This cheap little Raspberry Pi can run the glibc build in parallel!

Okay, I'm going for a run while this works.

## 8 AM - SUCCESS!

Success! This time glibc compiled and when I run this little test:

  echo 'int main(){}' > dummy.c
  $LFS_TGT-gcc dummy.c
  readelf -l a.out | grep ': /tools'

I get the appropriate feedback:

    [Requesting program interpreter: /tools/lib/ld-linux.so.2]

On to the standard C++ libraries

Success again!


## 8:30 AM - BinUtils - Pass 2

Let's try this. I'm feeling pretty confident.

But first... what am I re-building BinUtils already?


## 8:45 AM - GCC - Pass 2

On a roll this morning. We'll see if it holds out.

Pass 2 for GCC is running...

> It worked! I tested with a dummy program and it worked!

So we're doing a LOT better than yesterday.


## Noon - Into the Core

Well, GCC took FOREVER to compile, but here we are.

## 12:10 PM - Expect

* Now to install Expect, which appears to be a suite of testing tools for the build.

## 12:15 PM - DejaGNU

A testing framework

## 12:20 PM - Moving Along

Actually, these next few seem like small fry, and things are really clipping along.

So I am starting with the Check install [here](http://www.linuxfromscratch.org/lfs/view/development/chapter05/check.html), and I will report back in a bit.


## 2:30 PM - Chapter 5 Complete!

Okay, Chapter 5 is complete.  I now have a working (albeit temporary) OS for my build.

I estimate it will take about 12-20 hours for all of the compiling and building in Chapter 6.  I think,   And that's if everything is automated; it would be much slower if I did it by hand. Obviously.

So, no, I can't actually complete this hack-a-thon in the 48-hour weekend.  It's going to spill over into tomorrow.

I have a couple of options:

  * plunge ahead and take tomorrow off of work
  * plunge ahead and do it piece-meal after work throughout the coming week
  * stop now, and reflect on what I've actually learned. Focus on the learning.
  * something in between

Okay, well, I guess I will opt for something in between.  Most of the [Chapter 6](http://www.linuxfromscratch.org/lfs/view/development/part3.html) will just be building more packages in the right order.  There are run scripts for that.  I didn't want to use them, but they will at least afford me the opportunity to finish the build and make the LFS system bootable.  And I can do some learning there.

> Either I won't finish this project due to time or I use the stupid run scripts.  Sigh.

I guess I will try the RPi3 run script for chapter 6.


## 3:30 PM - Or... Not

Okay, after an hour of working through chapter 6 I thought I was to the point to run the PiLFS chapter 6 run script.  But there are problems.  Namely, after a `chroot` command, the terminal no longer knows where `/bin/bash` is.  So... I can't run the bash script.

Okay, let's look at this again.


## 4 PM - Chapter 6 - False Start Number 3. Ha.

Okay, I had to create a password for the root user on my Raspberry Pi.  Then the automated script for sections 6.7 through 6.70 died hard.  I think because I didn't clear out some of my old `build` directories. Looking into it.

Okay, I cleared out all my old build directories.  Trying again...


## 6PM - All those tar commands

Chapter 6 is still chugging away, building the final OS.

But all of those tarred packages got me thinking: I really hate memorizing all those tar flag.  And I am just terrible at:

![XKCD on tar](https://imgs.xkcd.com/comics/tar.png)

So I am just going to write a little script to do all of that for me.  Never again will I have to deal with all those annoying tar flags (that is, after I full understand all of them to write this script).  And the project will be known as:

# [StupidZip](https://github.com/theJollySin/StupidZip)


## 6PM - Tuesday

Okay, I got the LFS built, but I am several steps away from booting into it. Shame.  I left off [here](http://www.linuxfromscratch.org/lfs/view/development/chapter07/introduction.html).

One day I'll come back.
