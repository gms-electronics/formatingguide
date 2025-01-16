# Disk Formating Guide
This guide covers an array of formatting related issues with SAS / SATA hard disk for usage in general purpose server environments. 

# Should I boot from disk?
Largely speaking all instructions here should perform reasonably well in all linux environments. Some systems though such as TrueNas do not allow the installation of additional packages needed to fix your issues effectively. For that reason I would consider to boot from an iso to avoid any issues. For the purpose of reformating disks [ShredOS](https://github.com/PartialVolume/shredos.x86_64/) is a good choice.
* it is lightweight;
* it comes with support for most sas / raid controllers;
* it comes with support for plenty of network cards;
* it comes prebundled with the parallel package to allow you executing all procedures in this guides on multiple disks at the same time.

# How do I start?
1. Download the iso from the [ShredOS Repository](https://github.com/PartialVolume/shredos.x86_64/).
2. [Configure Telnet on ShredOS](https://github.com/PartialVolume/shredos.x86_64?tab=readme-ov-file#how-to-wipe-drives-on-headless-systems-or-systems-with-faulty-display-hardware-for-use-on-secure-lans-only) to access headless systems if neccessary,
3. Switch after the boot of ShredOS to a virtual terminal by pressing ALT + F3,
4. Execute the instructions [Change Block size](https://github.com/gms-electronics/formatingguide/blob/main/blocksizechange.md) or [Remove the Data Integrity Feature from disks](https://github.com/gms-electronics/formatingguide/blob/main/removeintegrityprotection.md).

# Contained Guides
1. [Change Block size from 3Par or EMC Storrage solution disks from 520 to 512 / 4096 bytes](https://github.com/gms-electronics/formatingguide/blob/main/blocksizechange.md)
2. [Remove the Data Integrity Feature from disks](https://github.com/gms-electronics/formatingguide/blob/main/removeintegrityprotection.md)
   
# Sources
* [Reformating 520k Drives](https://forum.level1techs.com/t/how-to-reformat-520-byte-drives-to-512-bytes-usually/133021), Level 1 Techs Forum, 2018
* [Troubleshooting Disk Format Warnings in TrueNas Scale](https://www.truenas.com/community/threads/troubleshooting-disk-format-warnings-in-truenas-scale.106051/), Truenas Forum, constantly updated
* [ShredOS](https://github.com/PartialVolume/shredos.x86_64/)

# Attributions
* Special thanks got to @PartialVolume and his tool [ShredOS](https://github.com/PartialVolume/shredos.x86_64/). It has been immensely helpful for disk sanitization for quiet some time now and is the Open Source reference in that field;
* TrueNas Community Member [Daisuke](https://www.truenas.com/community/members/daisuke.1017/) for giving the most dettailed description and solution approach;
* Wendell Wilson from Level 1 Tech who was the first one describing the problem and the solution.

