# NCQ


NCQ is a hardware enabled stack for optimizing the path of a hard drive on a disk. Sometimes it can break older badly built sata drivers.

### How to disable

It is enabled in the kernel by default, Add this to your kernal params to disable it

    libata.force=noncq


#### Refs:

 - https://en.wikipedia.org/wiki/Native_Command_Queuing
 - https://wiki.archlinux.org/index.php/Solid_state_drive#Resolving_NCQ_errors