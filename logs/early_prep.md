# Early Preparation for the Hack-a-Thon

> I need to make a plan.

This is where I will organize my plan for the Hack-a-Thon. Then I will gather and collect what I need to start.


## Linux from Scratch

* [Here](http://www.linuxfromscratch.org/lfs/view/stable/prologue/prerequisites.html) are some thoughts on prerequisites.
* [Here](http://www.linuxfromscratch.org) is the Linux From Scratch (LFS) home page.
* [Here](http://www.linuxfromscratch.org/lfs/view/development/) is the LFS book.
* [Here](http://intestinate.com/pilfs/guide.html) is the LFS page for Raspberry Pi (PiLFS).



## Raspberry Pi

If I want to try almost anything in the InfoSec / NetSec fields, I need a second computer. The cheapest solution is probably to use a Raspberry Pi (RPi) to create a little Linux server. Plus, I have been looking for an excuse to get a Raspberry Pi.


#### Hardware

After looking around, the cheapest Raspberry Pi solution was a to get the Vilros kit on Amazon. Several of these kits were a complete rip-off, but this one has only the components I would buy separately, but for cheaper than I could buy them.

Here is what I bought:

* [Vilros Raspberry Pi kit](https://www.amazon.com/gp/product/B01D92SSX6) - $50
* [32 GB Micro SD Card](https://www.amazon.com/gp/product/B06XWN9Q99) - $13

There are a couple of other things that I need, but I already have them:

* HDMI Cable
* USB Keyboard


#### Software & Setup

* [/r/raspberry_pi/](https://www.reddit.com/r/raspberry_pi/comments/41vbs8/new_persons_guide_to_the_pi_and_updated_example/) - Reddit community intro guide

The RPi uses a microSD card as its hard drive. And it can support a number of OSs (including something called Windows 10 IoT, Ha!). Because I want this process to be fast, I will pick the standard Linux distro for the RPi: Raspbian. But if the Windows OS becomes popular, that will be an important target OS to test.

Also, most people seem to start with a program called [NOOBS](https://www.raspberrypi.org/documentation/installation/noobs.md) to automate the installation of their OS.  But I would just assume do it from the command line.

First, I have to format the SD card:

* [Method using mount & mkdosfs](https://www.techwalla.com/articles/format-sd-card-linux)
* [Method using lsblk & parted](http://www.cio.com/article/3176034/linux/how-to-format-an-sd-card-in-linux.html)
* [Method using the Gnome-Disk-Utility](https://askubuntu.com/questions/44557/how-to-format-partition-sd-card)

Next I have to grab a disc image of the SO I want:

* [Raspbian](https://www.raspberrypi.org/downloads/raspbian/)
* [Kali Linux](https://www.offensive-security.com/kali-linux-arm-images/)
* [Retro Pie](https://retropie.org.uk/download/) - and some [tutorials](https://www.youtube.com/playlist?list=PLyPLRL6HIOqqXNmP2t19y0rphpiedNwNS) and [guides](https://github.com/RetroPie/RetroPie-Setup)

Then I need to load the bootable disk image for that OS onto my Micro SD card:

* [Official Raspberry Pi Guide](https://www.raspberrypi.org/documentation/installation/installing-images/linux.md)
* [Just use the Linux `dd` command](https://askubuntu.com/questions/179437/how-can-i-burn-a-raspberry-pi-image-to-sd-card-from-ubuntu)


#### Abandoned Idea: WiFi on the Pi

I was looking at [various](http://raspberrypihq.com/how-to-turn-a-raspberry-pi-into-a-wifi-router/) [guides](https://pimylifeup.com/raspberry-pi-wireless-access-point/) [online](https://jacobsalmela.com/2014/05/19/raspberry-pi-and-routing-turning-a-pi-into-a-router/) for turning your Raspberry Pi into a wireless router, so I can do all this wirelessly. Then I found out the RPi 3 has a built-in WiFi card. Great. Moving on.


## Slow Loris

Okay, I heard about a fun little protocol attack that can be made against Apache servers, and I would like to try it out. Maybe I can build a little [LAMP](https://en.wikipedia.org/wiki/LAMP_%28software_bundle%29) website to test it against. I will try to implement the attack in Java before the hack-a-thon and throw the code up on GitHub [here](https://github.com/theJollySin/AttackTheBlock).


