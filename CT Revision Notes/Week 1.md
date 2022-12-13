# Week 1 Notes

## Why computer Forensics?
- Important aspect of CyberSecurity
- Computers are either used as a tool to commit a crime or have become a target for these crimes

    - Computer Hacking 
    - Data theft
    - Terrorism
    - Murder
    - Fraud 
    - etc.

- encompasses any criminal act dealing with computers and networks

    - Hacking
    - DoS or DDoS attacks
    - Intrusion
    - Sending unsolicited or virus-causing electronic mail
    - Damage to or modifications of computer data or programs
    - Unauthorized access to computers and programs
    - etc.

- includes traditional crimes that are committed through the use of a `computer` and the `Internet`

    - Identity Theft
    - Data Theft
    - Internet Fraud
    - Counterfeit

## Objectives of Computer Forensics

- `Recover`, `analyze` and `present` computer based material to be presented as evidence
- Help to `identify` the evidence in a short time, `estimate` potential impact of malicious activity and `assess` the intent and identity of perpetrator



## Preservation

- Must preserve the `integrity` of the original evidence
- Original evidence should not be modified or damaged
- Make an image / copy of original evidence and perform the analysis
- Compare the copy with the original evidence to identify the modification or damages

### Evidence Preservation (Hashing)

- Compare hash values using either
    1. MD5
    2. SHA

## Identification

- Identifying the evidence and the location

## Extraction

- should be extracted immediately
- Volatile data can be lost at any point iin time
- extracted data compared with original and analyses

## Interpretation

- Most important for a Forensics Investigator
- Must be interpreted in a lucid (Clear) manner

## Documentation

- Maintained from the beginning of the investigation till the end

## What is Digital Evidence

- Found in hard disk drive, RAM, mobile phones, network or any external storage devices
- fragile and can be altered, damaged, or destroyed by improper handling or examination
- Failure to preserve the evidence may render it unusable or lead to an inaccurate conclusion, losing its credibility
- extremely important that the original evidence is acquired in a manner that `protects` and `preserves` the evidence
- probative information stored or transmitted in digital form that a party to a court case may use at trial
- Examples of digital evidences
    - Emails
    - Digital Photographs
    - Word processing documents
    - Instant message histories
    - Internet browser
    - histories
    - Content of Memory(RAM)

---

## Categories of Data

### Active Data
- Data that can be seen
    - Files and programs, data used by OS
    - Files in Recycle Bin

### Latent Data
- Data that exists despite being deleted
    - specialized tool required

### Archival Data
- Data in backup
    - Stored in external devices

### Persistent Data
- Data stored in local hard drive and is preserved even when power is lost

### Volatile Data
- Data in memory that is lost when computer loses power

## What is a forensic image
- Copy of original evidence
- Usually collected by a tool that perform bit-level copying from one location to another
- Common disk images
    - Expert Witness / Encase (E01)
    - Raw (DD)
    - Virtual Machine disk files (VMDK, OVF)
- Include `physical` or `logical` copy of hard drive, `memory dump` or copies of `removable media`

## Forensic Image Format
- 2 bit stream copies of evidence
- 3 types of images
    1. Complete Disk
        - Most preferred method
        - Most comprehensive
    2. Partition
        - Contains all allocation unt from an individual partition
        - Includes unallocated space and file slack in the partition
        - Does not capture all data on a drive
        - Taken only when the disk is excessively large
    3. Logical
        - Only certain files are acquired

## Drive Layout

![](/Week%201//Images/Drive%20Layout.png)  

## Traditional Image Process
- Performed on static drives
- System is turned off and booted to forensic imaging environment
- Write blocker used to prevent source media from beng modified
    - Sit between computer and storage unit
    - monitor commands issued and prevent computer from writing data to storage
    - has many interfaces

## Image Creation Tool
- Commercial Software Tool
    - Encase
    - AccessData FTK Imager
- Open Source tool
    - DC3dd
    - DCFLdd
    - dd

## Encase
- Called an image file
- extension of .E0X
- Contain bit stream image of suspect drive
    - CRC verification
    - Case identification info
    - MD5 hash
- Header information entered by examiner becomes part of evidence file
    - Cannot be changed

### Physical Layout of EnCase Evidence File
- Contains
    - Header
    - Data blocks
        - Bit by bit copy of data blocks on suspect media
    - Checksum and Hash
        - 32 bits verification
        - MD5 hash for checking of integrity

![](/Week%201//Images/Encase%20File%20Format.png)  

- CRC computed for every 64 sectors of data (32 Kbytes)
    - 1 sector = 512 bytes
- 128 bit MD5 hash is computed for entire data block
    - Exclude CRC
    - Hash verify both imaged media and evidence contain the same exact data

### How Encase file is loaded
1. Encase automatically verifies CRC and recomputes hash value for evidence file with the extension `.EXX`
2. Verification Process is successful after MD5 acquisition and verification hash values match and no CRC errors reported

## Challenges to Computer Evidence
- Growth in electronic devices and different platform
- Growth in storage size
- Finding storage to store huge evidence files
- How to maintain Authenticity and Evidence of data
    - Integrity ensured by using special hardware and tools
