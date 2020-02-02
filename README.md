# rarburn

Archive, encrypt (with RAR) and burn directory to optical media.

The main idea of this script is to run it inside an directory (for exaple 0001) with some content for backup.

This script will:

 1. Create copy of some scripts so you can easyly check and restore the archived content (inside 0001)
 2. Create file with MD5 sums for the original content (inside 0001)
 3. Archive the data (inside 0001) with RAR (nonfree) and add 12% recovery record
 4. Create file with MD5 sums (inside 0001) for the RAR archives, so you can check them with md5sum -c rar.md5
 5. Create a directory (inside 0001) with the same name (you know it 0001) as the main directory and move the data that will be burned on the CD/DVD/BD
 6. Unmount the optical drive if it is mounted by udev
 7. Burn ISO9660 image on the optical media with the same label as the main directory (0001 is dynamic, check "${PWD##*/}")
 8. Don`t eject the drive after the burning ends, mount it with udev, check the archived data, return to the main directory, report for errors and eject the CD.

You are free to modify the code and help me to improve it.

Created by georgi*dot*patsev_at_gmail|dot|com

*PS: I know that rar isn't free, but i dont want to deal with tar,p7zip and par2 simontaniously. Also i want to make a good use of my rar license.*
