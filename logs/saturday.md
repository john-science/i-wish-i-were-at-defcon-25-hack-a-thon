# Saturday Hack-a-Thon Log


## 5 AM

Woke up, jazzercised, ate half a mellon.


## 9 AM - Wake, Have Coffee

Okay, I am awake for real this time. I have coffee.  And I'm ready to hit [Chapter 4](http://www.linuxfromscratch.org/lfs/view/development/chapter04/creatingtoolsdir.html).

And... most of my work from last night appears to have disappeared. Nothing is mounted and I can't find the damn `sources` directory.  Crap.

> A disaster over my morning coffee.

Okay, so I had to re-mount the stupid `$LFS` partition and swap space and everything is fine:

    $ sudo mount -v -t ext4 /dev/mmcblk0p3 $LFS
    $ sudo /sbin/swapon -v /dev/mmcblk0p4

I am pretty sure that stuff needs to get put into the `/etc/fstab` file.  But... syntax.


OKAY, NOW I am ready to start Chapter 4.  First, we create some working directories:

    $ sudo mkdir $LFS/usr
    $ sudo mkdir $LFS/tools
    $ sudo ln -sv $LFS/tools /

## 9:10 - Create the lfs user and group

And now we create a dummy user and group so that we can do this build process a bit more safely:

    $ sudo groupadd lfs
    $ useradd -s /bin/bash -g lfs -m -k /dev/null lfs

It is not in the guide, but I had to give my `lfs` user a password before I could switch users:

    $ sudo passwd lfs

Now I can move forward with giving my new `lfs` user permissions to work on the build:

    $ sudo chown -v lfs $LFS/tools
    $ sudo chown -v lfs $LFS/sources

And, finally, I log in as `lfs`:

    $ su - lfs

## 9:30AM - Keyboard Troubles

> It is impossible to type a quote (`#`) or a backslash (`\`) on that keyboard! Ugh.

I am going to go out and buy a new keyboard.

## 10:30AM - New Keyboard Broken!

> Oh no! The new keyboard is also broken!

Okay, so this is clearly a software problem. Looking online I find out that the Raspberry Pi come localized for the United Kingdom.  What weird keyboards they must have.  I was able to fix that with the NCURSES menu under:

    $ sudo raspi-config


## 110AM - Setting up the Environment

Setting up the Environment

I pretty much just followed the commands in [Section 4.4](http://www.linuxfromscratch.org/lfs/view/development/chapter04/settingenvironment.html) to create a `.bash_profile` and `.bashrc` file for the new `lfs` user.

## 11:15AM - A Temporary System

Taken from [Chapter 5 - Constructing a Temporary System](http://www.linuxfromscratch.org/lfs/view/development/chapter05/chapter05.html).

First things first, I opened up the `binutils` source and tried to find the target triple for my build:

    $ ./config.guess
    arm71-unknown-linux-gnueabihf

So, that's a mouthfull. I hope it's supported.

And the book says I need to know what glibc linker I have on my current system:

    $ readelf -l /bin/ping | grep interpreter
    /lib/ld-linux-armhf.so.3

Okay, so I am reading through the next few stages.

> Do you want live-streaming videos of me reading?!?  Oh, the excitment.

## 11:45AM - Host Requirments Review

Okay, that reading did lead to some system reconfiguration.

First off, I needed to install `bison`, which is some sort of compiler-compiler for parsing language syntaxes.  I cheated and used `apt-get`:

    $ sudo apt-get install bison
    $ sudo unlink /usr/bin/yacc
    $ sudo ln -s /usr/bin/bison /usr/bin/yacc

And for reasons I can't possibly imagine, they want me to use `gawk` instead of `awk`, fine:

    $ sudo apt-get install gawk
    $ sudo unlink /usr/bin/awk
    $ sudo ln -s /usr/bin/gawk /usr/bin/awk

Finally, they want `sh` to just be a symlink to `bash`, but the RPi comes default with `dash`. Easy fix:

    $ sudo unlink /bin/sh
    $ sudo ln -s /bin/bash /bin/sh

## High Noon - Finally Compiling Something

We start by compiling `binutils` in [Section 5.4](http://www.linuxfromscratch.org/lfs/view/development/chapter05/binutils-pass1.html).

> Success!

It took 11m33.499s to compile Binutils on my Raspberry Pi 3. So that is my 1 SBU.

Now onto GCC.

## 3pm - GCC Compile Failed

After more than two hours compiling, GCC failed to compile "all".  So, let's hope I can figure out why and it works the second time.  Otherwise this will be the longest debug turn-around time in history.

Okay, I have no idea if this will fix the problem, but I did find two errors in my config statement. I used `--disable-multi-lib` instead of `--disable-multilib`, and I misspelled `--disable-libatmoic`.  I guess my only clear option is to fix that and run this two-hour test again.

Sigh.

> Trying to make GCC again.

## 5PM - GCC Still Compiling

It is occurring to me just now that there is now way for me to compile this entire OS this weekend.  The little ARM processor in this Raspberry Pi just won't be fast enough to get it done in 48 hours.  So... that's a thing I'm learning.

## 5:15PM - It finished!

GCC finally finished compiling!  109 minutes.  Whew.  Now let's try installing it...

## 5:17PM - It installed!

Okay, GCC is in.  Time to work on the Linux kernel.

## 5:30PM - GLIBC

Okay, time to [build GLIBC](http://www.linuxfromscratch.org/lfs/view/development/chapter05/glibc.html). Apparently, this won't take as long as GCC.  But it sounds like this is a point where stuff starts to fall apart for people. Fingers crossed.

Also, I downloaded a patch for GLIBC, but it took me ages to figure out that that patch probably isn't necessary until the second build phase.

## 6:45PM - Does GLIBC Work?

So, the GLIBC `make` and `make install` seemed to go fine. And I can now use my compiled version of GLIBC to build little C programs.  BUT.  The book says that if I do this:

    echo 'int main(){}' > dummy.c
    $LFS_TGT-gcc dummy.c
    readelf -l a.out | grep ': /tools'

Than I should get something like this:

    [Requesting program interpreter: /tools/lib/ld-linux.so.2]

But I get nothing. There is no reference to my `/tools/` directory in the compiled file.

Damn.

At this point the book just says "look around for the problem".  But I am looking through my logs and there are no logs or errors anywhere.  I am at a debugging empass.  Now I just hope someone online has had the EXACT same problem before.

## 8PM - And the name of my pain is TexInfo

Okay, so, apparently I missed a requirement when installing my system.  I think.

I think the problem is that I did not have "TexInfo" installed.  See [this post](http://www.linuxquestions.org/questions/linux-from-scratch-13/linux-from-scratch-chapter-5-7-no-output-from-sanity-check-4175473971/) here for someone with a similar problem.

I guess I should have run this [version-check.sh](http://www.linuxfromscratch.org/lfs/view/development/chapter02/hostreqs.html) script at the start, and I wouldn't have had this problem.

> Sadly, this means that I have to start my build from scratch.

Or, really, it means I have to start over at [BinUtils](http://www.linuxfromscratch.org/lfs/view/stable/chapter05/binutils-pass1.html)

> There is just no way I will be able to finish this build on a Raspberry Pi in the next 36 hours.  Ain't gonna happen.
