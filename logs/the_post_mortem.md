# The Hack-a-Thon Post-Mortem

> What did I learn?


## Linux

It is time to dig deeper.

#### File Copying - cp vs dd

I have been using `cp` to copy files for so long I no longer think about what it is doing. But I / we can't use `cp` to overwrite a hard drive with a disk image. This is because the `cp` tool has to work *within* a filesystem. For disk image creation I used `dd`, which allowed me to overwrite the partition tables and filesystem with a disk image.

This means you can use `dd` to [create disk images](https://askubuntu.com/questions/299081/how-do-i-create-a-backup-image-of-an-sd-card#299090).


#### The Extended Partition

It turns out that most setups only allow for four standard partitions.  I have no idea why.  But if you want more than that, you use the "extended partition", which you can then carve up to your heart's content.

So the extended partition serves a purpose, because of the four-partition limit.

[Here](https://askubuntu.com/questions/151968/what-does-the-term-extended-partition-mean-is-it-safe-to-use-this-type-of-par) is a nice AskUbuntu question about it.


#### .bashrc vs .bash_profile

I never really understood *why* we have so many different bash/etc profiles.  [This](https://stackoverflow.com/a/416931/1287593) StackOverflow answer had the best summary I could find:

    /bin/bash
           The bash executable
    /etc/profile
           The systemwide initialization file, executed for login shells
    ~/.bash_profile
           The personal initialization file, executed for login shells
    ~/.bashrc
           The individual per-interactive-shell startup file
    ~/.bash_logout
           The individual login shell cleanup file, executed when a login shell exits
    ~/.inputrc
           Individual readline initialization file


## InfoSec

Early on in the planning stages of this hack-a-thon I thought I would do something more InfoSec-related. That was abandoned, but I did a lot of reading first.  Most of that I won't summarize here.

#### InfoSec Projects

> It would be cool to contribute to an open source InfoSec or Pen Testing project.

GitHub keeps a list of popular security projects [here](https://github.com/showcases/security?s=stars).

These projects are in languages I know well and might otherwise be a good place for me to start looking:

* [Metasploit Framework](https://github.com/rapid7/metasploit-framework) - pen testing
* [MozDef](https://github.com/mozilla/MozDef) - Mozilla Defense Platform
* [GRR](https://github.com/google/grr/tree/gh-pages) - Google Rapid Response forensics and investigation
* [Cuckoo](https://github.com/cuckoosandbox/cuckoo) - sandbox for malware analysis

#### InfoSec Terminology

I finally sorted all of these out in my head.

* **InfoSec** - A very general term for keeping all kinds of information secure.
* **NetSec** - Usually more concerned with Firewalls, VPNs, IDPs, and router-level penetrations.
* **AppSec** - Related more to software design and practices.
* **ITSec** - Inside the system: host-based security, domain controllers / auth servers, access controls systems.
* **OpSec** - The physical end of security, including social engineering defense.
