# Disk Formating Guide
This guide covers an array of formatting related issues with SAS / SATA hard disk for usage in general purpose server environments. 

# Should I boot from disk?
Largely speaking all instructions here should perform reasonably well in all linux environments. Some systems though such as TrueNas do not allow the installation of additional packages needed to fix your issues effectively. For that reason I would consider to boot from an iso to avoid any issues. For the purpose of reformating disks  [SystemRescue (formerly known as SystemRescueCd)](https://www.system-rescue.org/) is a good choice.
* it is lightweight;
* it comes with support for most sas / raid controllers;
* it comes with support for plenty of network cards;
* you can easily add a package called parallel to compute multiple reformating tasks at once.

# How do I start?
1. Download the iso from the Systemrescue website
2. If you need to handle multiple disks run `pacman -S parallel`
3. Follow the instructions you can find below.

# Contained Guides
1. [Change Block size from 3Par or EMC Storrage solution disks from 520 to 512 / 4096 bytes](https://github.com/gms-electronics/formatingguide/blob/main/blocksizechange.md)
2. [Remove the Data Integrity Feature from disks](https://github.com/gms-electronics/formatingguide/blob/main/removeintegrityprotection.md)
   
# Sources
* [Reformating 520k Drives](https://forum.level1techs.com/t/how-to-reformat-520-byte-drives-to-512-bytes-usually/133021), Level 1 Techs Forum, 2018
* [Troubleshooting Disk Format Warnings in TrueNas Scale](https://www.truenas.com/community/threads/troubleshooting-disk-format-warnings-in-truenas-scale.106051/), Truenas Forum, constantly updated
