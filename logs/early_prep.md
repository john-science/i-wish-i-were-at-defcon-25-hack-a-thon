# Early Preparation for the Hack-a-Thon

> I need to make a plan.

This is where I will organize my plan for the Hack-a-Thon. Then I will gather and collect what I need to start.


## Security

> What do I want to learn? What can I learn in a weekend?


#### Slow Loris

Okay, I heard about a fun little protocol attack that can be made against Apache servers, and I would like to try it out. Maybe I can build a little [LAMP](https://en.wikipedia.org/wiki/LAMP_%28software_bundle%29) website to test it against. I will try to implement the attack in Java before the hack-a-thon and throw the code up on GitHub [here](https://github.com/theJollySin/AttackTheBlock).


#### Penetration Testing - Kali Linux

[Kali Linux](http://www.kali.org/) is a common Linux distro used by people for penetration testing. I think it is just an [SELinux](selinuxproject.org) distro with a bunch of penetration tools pre-installed. That doesn't sound like something an expert would need, but it sounds ideal for a beginner.

[This](https://www.youtube.com/watch?v=vg9cNFPQFqM) seems like a good newbie indtroduction to Kali Linux. It is a 15-hour YouTube tutorial. Maybe I will hate it and have to find something else. We will see.


#### Penetration Testing - Metasploit

* [Metasploit Framework](https://github.com/rapid7/metasploit-framework) - popular tool for developing and testing exploit code against a remote target
* [Metasploit](https://www.goodreads.com/book/show/10545174-metasploit) - $ 20 used - popular textbook

I was watching a presentation from DefCon 23 and someone (I forget who) mentioned that the Metasploit Framework was a popular pentatration testing tool. And he said he used this textbook to teach students. The Amazon reviews say the textbook is a little out-of-date, but I can handle that.

If there is an entire textbook, maybe one weekend isn't enough time to learn my way around Metasploit. Oh well, I'll give it a try anyway.


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
* [Retro Pie](https://retropie.org.uk/download/) - and some [tutorials](https://www.youtube.com/playlist?list=PLyPLRL6HIOqqXNmP2t19y0rphpiedNwNS)

Then I need to load the bootable disk image for that OS onto my Micro SD card:

* [Official Raspberry Pi Guide](https://www.raspberrypi.org/documentation/installation/installing-images/linux.md)
* [Just use the Linux `dd` command](https://askubuntu.com/questions/179437/how-can-i-burn-a-raspberry-pi-image-to-sd-card-from-ubuntu)


#### Abandoned Idea: WiFi on the Pi

I was looking at [various](http://raspberrypihq.com/how-to-turn-a-raspberry-pi-into-a-wifi-router/) [guides](https://pimylifeup.com/raspberry-pi-wireless-access-point/) [online](https://jacobsalmela.com/2014/05/19/raspberry-pi-and-routing-turning-a-pi-into-a-router/) for turning your Raspberry Pi into a wireless router, so I can do all this wirelessly. Then I found out the RPi 3 has a built-in WiFi card. Great. Moving on.

