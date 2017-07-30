# Sunday Hack-a-Thon Log


## 5 AM

Woke up, jazzercised, ate half a mellon.


## 7 AM - Back at It

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
