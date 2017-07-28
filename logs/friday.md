# Friday Hack-a-Thon Log


## 4 PM

Just got home from work.

> First things first: back up my hard drives.

## 4:20 PM

Okay, I've decided to just install Raspbian on my Raspberry Pi 3 micro SD card and I will try to re-partition the hard drive after.

First, I need to format my 32GB micro SD card. To start, I need it's name:

    $  mount
    /dev/sda1
    ...
    /dev/mmcblk1p1

Before I can format it, I need to unmount it:

    $ unmount /dev/mmcblk1p1

Whoops `unmount` command not found. I probably should have installed it, but instead I just hit "eject" on the disk from the GUI.  Same deal.

Now I just need to format it:

    $ mkdosfs -I -F32 /dev/mmcblk1p1

(Why, you may ask, did I choose the FAT32 file system? Good question. I have no idea.)



Here are a couple  guides for re-partitioning the SD card:

* [a StackOverflow answer](https://raspberrypi.stackexchange.com/questions/499/how-can-i-resize-my-root-partition)
* [AdaFruit post](https://learn.adafruit.com/resizing-raspberry-pi-boot-partition/edit-partitions)


## 11:37 PM

Drunk.  I think my Raspberry Pi just ordered a pizza from Russia.
