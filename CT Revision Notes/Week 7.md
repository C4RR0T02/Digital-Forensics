# Week 7 Notes

## NTFS
- Important data are allocated to `files`
- entire file system is considered a data area, and `any sector can be allocated to a file`
- consistent layout is that the first sectors of the volume contain the boot sector and boot code

## NTFS File System
- NTFS contains the following components:
    - Partition Boot Record (PBR) – similar to VBR in FAT
        - Located in first sector of NTFS partition
    - Master File Table (MFT) – similar to directory entry in FAT
    - $Bitmap – similar to FAT

![](/Week%207/Images/PBR%20Table.png)  

## MFT 
- MFT is the primary source of metadata in NTFS
    - contains information about all files and directories, such as timestamps, size in bytes, attributes, parent directory, and content.
    - Every file and directory has an entry in MFT.
- Each NTFS volume will contain its own MFT and it `can be in any position on the volume`.
- To determine MFT’s starting location, we look at byte offset 48-55 in the boot record (PBR).

## Endianness
- attribute of a system that indicates whether integers are represented from left or right or right to left

![](/Week%207/Images/Endian.png)  

![](/Week%207/Images/Little%20Endian%20Conversion%20Concept.png)  

## MFT Entry
![](/Week%207/Images/MFT%20Entry.png)  

- Header:

        Record Type – specify whether this entry is a file or directory

        Record # - integer to identify a given MFT entry

        Parent record # - record # of parent directory

        Active/Inactive flag – Deleted files/directories are marked Inactive. NTFS will replace inactive entries with new active entries to prevent MFT from growing indefinitely

- Attributes – contain metadata about a file/directory

## How to know if the record file is usable
- First 4 bytes is not `BAAD`
- No MFT record is deleted just flagged and made available to be reused

## NTFS System File

![](/Week%207/Images/NTFS%20System%20File.png)  

![](/Week%207/Images/NTFS%20System%20File%20Description.png)  

## Change Log
- Logs to track changes to directories and files
- Able to be used to reverse file system operation in the event of failure
- serve as a useful source of evidence for file system activity

## $Logfile
- tracks all transactions that change the structure of a volume.
- includes files or directory creation / copy / deletes, changes to metadata, and changes to INDX records.
- Transaction entries within $Logfile contain the same attributes that are present in the MFT.
- The log is circular and can roll over on a frequent basis, especially on system volumes.
- Like $MFT and other artifacts, FI needs to use a forensic utility that provides disk access to copy $Logfile from the system.

## NTFS Attribute
Each attribute is a varying-length stream identified by a 4-byte attribute type at offset 0x0. 

### Attribute File System
![](/Week%207/Images/Attribute%20File%20System.png)  

![](/Week%207/Images/Attribute%20Header.png)  

![](/Week%207/Images/MFT%20Attributes%20Table.png)

## Typical File Record
- $Standard_Information and one $File_Name are mandatory for all files and directories.
- If the filename is longer than 8 characters or contains special characters, Windows will also create a DOS compatible name and save this as a 2nd $File_Name attribute. 
- $Index_Root provides the header for the index
- Once the listing is too long, an $Index_Allocation attribute is used to track which clusters on disk the index will reside.

![](/Week%207/Images/NTFS%20Overview.png)  

## Analyzing TimeStamp
MFT entry for a given file have at least 2 sets of attributes containing `MACE` (Modified, Accessed, Created, Entry Modified) timestamp attributes.
One set is contained within $Standard_Information ($SI) attribute, the other is contained in $File_Name ($FN) attribute.

![](/Week%207/Images/MACE%20timestamp%20Definition.png)  

## Resident and Non-Resident Attributes
- MFT records may have attributes with a large content (such as a $Data attribute) such that all the attributes cannot be held within one base record. 
- Attributes whose content is held entirely within the attribute (be it a base or extension MFT record) are known as Resident. 
- Attributes whose content is not held entirely within the attribute are known as Non-Resident. 
- Resident attributes are set to 0, 
- Non-resident attributes are set to 1. 

## $Bitmap
- `system file` $Bitmap holds the map of logical clusters in use and not in use. This is used for finding free space when a file is allocated. 
- used for mapping MFT records in - and out - of use
- Any bit set to 1 indicates an in-use cluster or record

## $Boot file
The 16 sectors (two clusters) at logical sector zero in the active partition, containing the VBR and the bootstrap code, are defined in NTFS as the $Boot file.

