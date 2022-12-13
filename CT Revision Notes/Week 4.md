# Week 4 Notes

## Folder Structure of Windows OS
- Able to determine Windows version

![](/Week%204/Images/Folder%20Structure.png)  

## Root Folder
- Named after User's login name
- folders containing user document and environment and configuration in subfolder
    - Application Data
    - Cookies
    - Desktop
    - Favorites

## Determine Last Logout Time
- NTUSER.DAT
    - Registry file
    - Every user has one
- Modified when the user logs out or shut down
- Registry viewer is required

## Recycle Bin
1. File gets deleted
2. Individual index file beginning with $I gets created followed by a random set of numbers and the original extension
    - Stores the location of the original file before deletion
3. The deleted file name is renamed to a file beginning with $R and the same set of random number and the original extension
    - Renamed original file
    - Stores original data

There is a `Security Identifier` to access the recycle bin

## Low Folders
- protect system against malware 
- runs at the lowest possible level privilege
- must access both to have complete investigation

## Cookies
- cookie can be used for
    - Authentication
    - Storing site preferences
    - Shopping cart contents
    - The identifier for a server-based session
- Each cookie is contained in 1 file
- The total collection of cookie files is under the management of index.dat
- The index.dat file contains dates, and the cookie itself contains internal dates.
    - The internal dates of a cookie describe when it was last modified by the website and its expiration date.
        - decode using cookie decoder (CookieView)

## Temporary Internet Files (TIF)
- Mainly for Internet Explorer.
- Store files that are downloaded and cached from the Internet.
- Useful to track user’s web browsing history, including web mail (Gmail).
- files use SQLite database format

## Recent Folders
- Contains link files that links to recently accessed files, folders, and applications.

## My Documents / Documents
Default location where all compliant applications store user-generated data.

## Sent To Folder
- Contains within this folder are the options that  a user has when the user right-click on an object and choose Send To

## Temp Folder
- Contains temporary files created by Windows as various programs are running and different processes are taking place.
- They are often exact copies of files stored elsewhere on the computer. At other times they are exact duplicates of files which are waiting their turn to be processed by the computer.

## Desktop Folder
- Contain content placed intentionally by user
- Public folder can be used by anyone to conceal data

