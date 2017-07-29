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

