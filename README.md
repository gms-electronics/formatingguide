# Disk Formating Guide
This guide covers an array of formatting related issues with SAS / SATA hard disk for usage in general purpose server environments. 

# Prepare a Boot ISO for formating discs
Largely speaking all instructions here should perform reasonably well in all environments. I would consider to boot from an iso though to avoid any infractions with the actions you want to perform. 
For the purpose of reformating disks  [SystemRescue (formerly known as SystemRescueCd)](https://www.system-rescue.org/) is a good choice: 
* it is lightweight
* it comes with support for most sas / raid controllers
* it comes with support for plenty of network cards
* you can easily add a package called parallel to compute multiple reformating tasks at once

## How do I use System & 


# Contained Guides
1. Change Block size from special purpose block sizes such as 520 byte to 512 / 4096 bytes
2. Remove Data Integrity Feature not supported by systems such as TrueNas

# Sources
* [Reformating 520k Drives](https://forum.level1techs.com/t/how-to-reformat-520-byte-drives-to-512-bytes-usually/133021), Level 1 Techs Forum, 2018
* [Troubleshooting Disk Format Warnings in TrueNas Scale, Truenas Forum, constantly updated](https://www.truenas.com/community/threads/troubleshooting-disk-format-warnings-in-truenas-scale.106051/) 
