# Week 2 Notes

## Investigative Process
1. Crime is suspected
2. Conduct Preliminary Assessment of the case
3. Obtain Search Warrant for seizure (if required)
4. Perform first response procedure at crime scene
    - 6 Steps
5. Perform Forensic duplication / imaging at forensic lab
6. Generate MD5 Checksum (hash) on the images
7. Prepare Chain of Custody (Start at the crime scene)
8. Store Original evidence in a secure location (in evidence bag)
9. Analyze the image copy of evidence
10. Prepare relevant forensic reports
11. Submit the report to the client
12. Attend Court and testify as expert witness (if required)

## Preliminary Assessment
- Determine occurrence of incident and impact
    - Know what to look out for at crime scene
    - List the steps take during investigation
- Access digital evidence thoroughly with respect to `scope` to determine `course of action` to take
    - Not all evidence is appropriate for admission in court
- Prioritize evidence
    - Location of evidence
    - Stability of media
- Establish how to document evidence
- Establish storage locations for electromagnetic interference
- Evaluate the necessity to provide unregulated power supply to battery-operated devices

### Relevant evidence
Evidence that proof or disprove facts in the case

### Admissible evidence
Evidence that conforms to all regulations and statues governing the nature and manner it was obtained and collected

## Preparation Stage

### What to find out
- Description of incident
- Incident manager running the incident
- Location of incident
- Details on what to be seized
- Other work to be performed (Full Search)

### What to bring
- Acquisition
    - Forensics software
    - Large Capacity storage device
    - Live response tools
    - Write-blockers
    - Drive adapters for SATA / IDE / SCSI
- Documentation
    - Digital Camera
        - Capture live data
        - Capture state of scene
    - Writing Materials
        - Notepad
        - Pencils
        - Pen
        - Markers
- Disassembly tools
    - Toolkit
        - Screw driver with multiple heads
        - wire cutter
        - pliers
    - Anti-static wrist straps
- Packaging
    - Anti-static bags
    - Evidence bags
    - Evidence tape
    - Cable ties
    - Sturdy boxes
- Others
    - Latex gloves
    - Magnifying glass
    - Uninterrupted Power Supply

## Search and Seizure
- Before evidence collection, investigator required to have permission to search or seize evidence
- Voluntary surrender
    - Occur most often when primary owner is not the suspect
    - special arrangement for business critical system to avoid disruption to business function
- Search Warrant
    - allows law enforcement officers to acquire evidence from suspect's machine without giving suspect prior notice
    - warrants can be issued for
        - floors
        - room
        - house
        - company
        - all computer 
        - part of computer
    - only open to law enforcements

## First Response Procedure
1. `Secure the scene`
    - Ensure removal of all people from where evidence is collected done by `security team`
    - Establish perimeter control, make initial entry and secure area for `search team`
        - Search team carry out search operation
2. `Conduct preliminary interviews`
    - Able to be done parallel with documenting scene
    - Enquire who was on site at time of offence
    - Conduct interview and record the location at time of entry and reason for being there
    - gather information of digital evidence
        - owner of device found at scene
        - password to access system, software, data
3. `Document the scene`
    - Field notes, sketches, video or photographs at the scene before anything is touched or removed
    - document physical scene
        - Mouse location
        - location of components found near system
    - Record condition of computer system, storage media, electronic devices
    - Take photo of monitor screen, rear of computer
    - Take photo of entire site
4. `Searching and seizing`
    - Use latex glove when handling computer evidence
    - Avoid leaving DNA on the computer evidence
    - Don't change the state of the device
5. `Bagging and tagging`
    - Bagging protect against contamination and tampering
    - Tagging provides means of associating the attached and bagged evidence with a particular location, date, time, case, event and seizure agent
        - Provide first link of chain of custody evidence
    - Label all the cables and photograph the rear of the computer with cables and tags in place.
    - Pack magnetic media in antistatic packaging.
    - Exhibit numbering should follow this format:
        - aaa/ddmmyy/nnnn/zz where
            
                ‘aaa’ is the initials of forensic analysts seizing the equipment.
                ‘ddmmyy’ is the date of seizure
                ‘nnnn’ is the sequence number of exhibits seized by ‘aaa’-starting with 001.
                ‘zz’ is the sequence number for the parts of the same exhibit.

6. `Transporting electronic evidence`
    - Keep electronic evidence collected away from magnetic sources 
        - can damage electronic evidence
    - Store evidence away from high temperature and humidity. Conditions too hot, cold or humid can damage evidence
        - Rear seat instead of car boot
    - Maintain chain of custody on evidence to be transported.

### Handling Live System
- Disconnecting power supply and network connection can destroy crucial evidence

1. Pull the power plug from wall / back of computer
    - Destroy everything in memory
    - It can crash UNIX system and corrupt evidence file
2. Perform proper shut down
    - Writes many entries to activity log file and change state of evidence
        - May become inadmissible to court
    - Computer may run procedures to cleanse log files on shutdown
        - Result in loss of crucial evidence
3. Leave system up and running
    - Run live forensic software if given the authority
    - Good option if you have a manageable number of workstations

### Identification and seizure process

![](/Week%202/Images/Evidence%20Action%20Flowchart.png)  

### Seizing internal hard disk
- If only internal hard disk is to be seized:
    - Wear an anti-static strap to ensure equipment is protected from static electricity.
    - Disassemble the case of the computer to be examined to permit physical access to the storage devices.
    - Ensure equipment is protected from magnetic fields.
- Document internal storage devices and hardware configuration:
    - Drive condition (e.g. model, geometry,  size)
    - Internal components (e.g. sound card, video card, MAC address etc.)
    - Disconnect storage devices (using the power connector or data cable from the back of the drive or from motherboard) to prevent the destruction, damage, or alteration of data.

### Chain of Custody
- Evidence predicted must exist in the same condition it was collected
- Document the chronicles every move and access of evidence
    - Court expects chain of custody to be completed without gaps
- Chain starts when evidence is collected
- Used to prove the integrity of the chain of custody
- Contains 
    - Date and time
    - Action Type
    - Personnel collecting / accessing evidence
    - Computer descriptive information
    - Disk drive descriptive information
    - Handling procedure
    - Complete description of action
    - Reason for action

## Evidence Acquisition
- evidence acquired in a manner where integrity of the evidence is protected
    - Document hardware and system configuration on the examiner system
    - Disassemble the case of the computer to be examined to permit physical access to the storage devices
    - Identify storage devices that need to be acquired
    - Document internal storage devices and hardware configuration
        - Drive condition
        - Internal components
    - Disconnect storage devices (using the power connector or data cable from the back of the drive or from the motherboard) to prevent the destruction, damage, or alteration of data
    - Whenever possible, remove the subject storage device and perform the acquisition using the examiner’s system. 
    - Ensure that the examiner’s storage device is forensically clean when acquiring the evidence.

## Documenting and Reporting
- Actions and observations should be documented
- Conclude with preparation of written report of the findings
    - Documenting steps following the analysis
    - Everything relevant to be documented and in continuous process
    - Include date, times, descriptions and results of action taken
    - include irregularities encountered and take it into consideration
    - include network topology, list of authorized users and password

## Maintaining Professional Conducts
- Consider all available facts that account to the crime scene
- Ignore external biases to maintain the integrity of fact-finding in all investigations
- Keep the case confidential
- Keep up with the latest technical changes