# The Hack-a-Thon Post-Mortem

> What did I learn?


## Linux

It is time to dig deeper.

#### File Copying - cp vs dd

I have been using `cp` to copy files for so long I no longer think about what it is doing. But I / we can't use `cp` to overwrite a hard drive with a disk image. This is because the `cp` tool has to work *within* a filesystem. For disk image creation I used `dd`, which allowed me to overwrite the partition tables and filesystem with a disk image.

This means you can use `dd` to [create disk images](https://askubuntu.com/questions/299081/how-do-i-create-a-backup-image-of-an-sd-card#299090).


## Open Source Projects

### InfoSec Projects

> It would be cool to contribute to an open source InfoSec or Pen Testing project.

GitHub keeps a list of popular security projects [here](https://github.com/showcases/security?s=stars).

These projects are in languages I know well and might otherwise be a good place for me to start looking:

* [Metasploit Framework](https://github.com/rapid7/metasploit-framework) - pen testing
* [MozDef](https://github.com/mozilla/MozDef) - Mozilla Defense Platform
* [GRR](https://github.com/google/grr/tree/gh-pages) - Google Rapid Response forensics and investigation
* [Cuckoo](https://github.com/cuckoosandbox/cuckoo) - sandbox for malware analysis


## Minutia

Less important things I learned.


## TODO

This is just a place for things I am learning about that I will try to write down more fully later.

* The Extended Partition
* [.bashrc vs .bash_profile](https://stackoverflow.com/questions/415403/whats-the-difference-between-bashrc-bash-profile-and-environment)
* ld vs ln... whoops.


### InfoSec Terminology

I finally sorted all of these out in my head.

* **InfoSec** - A very general term for keeping all kinds of information secure.
* **NetSec** - Usually more concerned with Firewalls, VPNs, IDPs, and router-level penetrations.
* **AppSec** - Related more to software design and practices.
* **ITSec** - Inside the system: host-based security, domain controllers / auth servers, access controls systems.
* **OpSec** - The physical end of security, including social engineering defense.
