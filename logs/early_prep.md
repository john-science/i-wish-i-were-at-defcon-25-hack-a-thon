# Early Preparation for the Hack-a-Thon

> I need to make a plan.

This is where I will organize my plan for the Hack-a-Thon. Then I will gather and collect what I need to start.


## Security

TODO


### Terminology

* **InfoSec** - A very general term for keeping all kinds of information secure.
* **NetSec** - Usually more concerned with Firewalls, VPNs, IDPs, and router-level penetrations.
* **AppSec** - Related more to software design and practices.
* **ITSec** - Inside the system: host-based security, domain controllers / auth servers, access controls systems.
* **OpSec** - The physical end of security, including social engineering defense.


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

The RPi uses a microSD card as its hard drive. And it can support a number of OSs (including something called Windows 10 IoT, Ha!). Because I want this process to be fast, I will pick the standard Linux distro for the RPi: Raspbian. But if the Windows OS becomes popular, that will be an important target OS to test.

Also, most people seem to start with a program called [NOOBS](https://www.raspberrypi.org/documentation/installation/noobs.md) to install their OS.


* [/r/raspberry_pi/](https://www.reddit.com/r/raspberry_pi/comments/41vbs8/new_persons_guide_to_the_pi_and_updated_example/) - Reddit community intro guide
* [Installing OS Images](https://www.raspberrypi.org/documentation/installation/installing-images/) - Official Guide
* [Installing OS Images - Linux](https://www.raspberrypi.org/documentation/installation/installing-images/linux.md) - Official Guide
* [Installing NOOBs and the OS](https://www.youtube.com/watch?v=6VmlfO7wL40)
* [Installing RetroPie and Gaming](https://www.youtube.com/playlist?list=PLyPLRL6HIOqqXNmP2t19y0rphpiedNwNS)


#### Abandoned Idea: WiFi on the Pi

I was looking at [various](http://raspberrypihq.com/how-to-turn-a-raspberry-pi-into-a-wifi-router/) [guides](https://pimylifeup.com/raspberry-pi-wireless-access-point/) [online](https://jacobsalmela.com/2014/05/19/raspberry-pi-and-routing-turning-a-pi-into-a-router/) for turning your Raspberry Pi into a wireless router, so I can do all this wirelessly. Then I found out the RPi 3 has a built-in WiFi card. Great. Moving on.

