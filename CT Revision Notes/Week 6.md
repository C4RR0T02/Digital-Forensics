# Week 6 Notes

## Primary Partitioning
- Subdividing of hard disk drive
- Can have maximum 4 primary partition

## Volumes in Partition
- Partition is collection of physically consecutive sectors
- Volume is collection of logically event sector
    - volume may appear consecutive, but only logically.

## Extended Partition
- One of the 4 primary partitions may be subdivided into multiple partitions (volumes), therefore allowing 2 or more volumes to exist within one partition
- subdivided partition is referred to as an `extended partition`.

## File System
- mechanism for users to store data in a hierarchy of files and directories.
- consists of structural and user data that are organized such that the computer knows where to find them
- Windows File System
    - FAT12/16/32 (File Allocation Table)
    - NTFS (New Technology File System)
    - REFS (Resilient File System)
- Track the name of the object (file/folder).
- Track the starting cluster/allocation block of the object.
- Track the fragmentation of the object (noncontiguous allocation blocks/clusters).
- Track allocation blocks/cluster status on the volume.

## Master Boot Record (MBR)
- 512 byte boot sector
- It holds a disk's primary partition table (4-entries).
- Each partition table entry list the starting sector, the number of sectors, and the type.
- It tells the computer how the hard drive is partitioned, and how to load the operating system(s).
- It also holds the boot instructions.
- `partition entry` is 16 bytes long

## How Master Boot Code boot up device
- `Scans` the partition table for active partition.
- `Finds` the starting sector of the active partition.
- `Loads` a copy of the boot sector (in VBR) from the active partition into memory (RAM).
- `Transfer` control to the executable code in the boot sector.

## File Signature
0x55AA
- Hex value to demarcate the end of sector

## Partition Table
- The partition table holds information to identify the type, size and location of the partition, and whether it is active or not. 
- There can be either four primary or three primary and one extended partitions. Each partition table entries is 16 bytes long.

![](/Week%206/Images/Partition%20Table%20Entry.png)  

## Boot Sectors of hard disk

![](/Week%206/Images/Hard%20Disk%20Boot%20Sectors.png)  

### Windows XP Partition Layout

![](/Week%206/Images/Windows%20XP%20Partition%20Layout.png)  

### Windows 7 and later Partition Layout

![](/Week%206/Images/Windows%207%20and%20Later%20Partition%20Layout.png)  