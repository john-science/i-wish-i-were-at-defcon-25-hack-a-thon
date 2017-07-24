# Early Preparation for the Hack-a-Thon

> I need a plan.

The hack-a-thon is unlikely to be successful if I don't have a plan going into it. This is where I will gather my thoughts.


## Raspberry Pi

I will be building a Linux-from-Scratch (LFS) distro on a Raspberry Pi (RPi). This will give me a lot of freedom with my RPi later, to build little LAMP servers and do some back penetration testing.

There are probably many great resources online for RPi tinkerers.  So far the [/r/raspberry_pi/](https://www.reddit.com/r/raspberry_pi/comments/41vbs8/new_persons_guide_to_the_pi_and_updated_example/) subreddit intro guide seems like a good place to start. Though the [official guide](https://www.raspberrypi.org/documentation/installation/installing-images/linux.md) also seems good.


#### Hardware

After looking around, the cheapest Raspberry Pi solution was a to get the Vilros kit on Amazon. Some Pi kits looked like complete rip-offs, but the Vitros one only has the components I would buy separately, but for cheaper than I could get them.

Here is what I bought:

* [Vilros Raspberry Pi kit](https://www.amazon.com/gp/product/B01D92SSX6) - $50
* [32 GB Micro SD Card](https://www.amazon.com/gp/product/B06XWN9Q99) - $13

There are a couple of other things that I needed, but I already had them:

* HDMI Cable
* USB Keyboard
* USB Mouse


#### Software & Setup

The first step here is to install a working Linux OS onto the Raspberry Pi, and create a partition for LFS build.

I need three partitions on my (32GB) micro SD card:

1. A partition for the LFS build - about 20GB
2. A small swap partition - about 2GB
3. A partition for the [Raspbian](https://www.raspberrypi.org/downloads/raspbian/) OS - remaining ~10GB

I will probably use `fdisk` to do the partitioning. [Here](http://tldp.org/HOWTO/Partition/fdisk_partitioning.html) is a good introduction to `fdisk`.


## Linux from Scratch

Okay, now that I have an OS on my RPi it is connected to a monitor (TV) and keyboard. I can start working through the LFS introduction and prerequisites.

* [Here](http://www.linuxfromscratch.org/lfs/view/stable/prologue/prerequisites.html) are some thoughts on prerequisites.
* [Here](http://www.linuxfromscratch.org) is the Linux From Scratch (LFS) home page.
* [Here](http://www.linuxfromscratch.org/lfs/view/development/) is the LFS book.
* [Here](http://intestinate.com/pilfs/guide.html) is the LFS page for Raspberry Pi (PiLFS).

This does not like like a short process.


## Slow Loris

Okay, I heard about a fun little protocol attack that can be made against Apache servers, and I would like to try it out. Maybe I can build a little [LAMP](https://en.wikipedia.org/wiki/LAMP_%28software_bundle%29) website to test it against. I will try to implement the attack in Java before the hack-a-thon and throw the code up on GitHub [here](https://github.com/theJollySin/AttackTheBlock).


