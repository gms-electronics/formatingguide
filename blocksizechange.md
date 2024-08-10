# Symptoms and Issue
After installing a hard disk drive, the disk is not recognized by the system despite the disk being functional and correctly seated. 

:exclamation: This guide is solely for SAS or SCSI disks and does not apply to SATA disks. 

:exclamation: An interuption of the process can destroy your disk, assure correct functioning of all other components, stable energy supply and.

:exclamation: Avoid using remote access to shells As soon as you close the shell the process might be (prematurely) terminated.

:exclamation: Study the drives you want to reformat carefully to avoid data loss.

## Strategy to reformat the block size of a physical disk for one drive

### Requierements
* [sg3_utils]([url](https://sg.danny.cz/sg/sg3_utils.html))

### Instructions
1. List disks using lsblk
2. Identify the device with the wrong block size by executing `sg_format <device>`
3. Run `sg_format -f --format --size=<512 / 4096> <device> --quick`
4. Wait till the process terminated and check by executing `sg_format <device>` again. 

## Strategy to reformat the block size of a physical disk for multiple drives at the same time

### Requierements
* [sg3_utils]([url](https://sg.danny.cz/sg/sg3_utils.html))
* [parallel]([url](https://www.gnu.org/software/parallel/))

### Instructions
1. List disks using lsblk
2. Identify the device with the wrong block size by executing `sg_format <device>`
3. Run `for i in {1..28}; do echo "sg_format --format --size=512 /dev/sg$i"; done | parallel -j40`

### Additional Information for systems using letters to denominate drives
The same command would work also with systems using a drive letter system:
`for i in {a..z}; do echo "sg_format --format --size=512 /dev/sg$i"; done | parallel -j40`

### Additional Information for formating multiple drives that are not in a sequence
Given that the nomenclation of the drives is not always sequential, for i in can be adapted to that use case:
If I want to format drives /dev/sga to /dev/sgc and the drives /dev/sge/ to /dev/sgf/ the command could look like this:
`for i in {{a..c},{e..f}}; do echo "sg_format --format --size=512 /dev/sg$i"; done | parallel -j40`
