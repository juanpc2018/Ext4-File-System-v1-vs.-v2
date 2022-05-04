# Ext4-File-System-v1-vs.-v2
BEWARE!

== Ext4 filesystem ==
Ext4 v1 has 32-Bit header since the Linux 10.04 era, but...
Ext4 v2 has 64-Bit header since Linux 20.04 era, maybe early Linux 16.04 18.04, dont know exacty when the change was made.

The problem:
Not compatible,
Has the same Name.
Ext4v2 should have been called Ext5.
but people installing linux maybe would had second thoughts installing Ext5.

Anyway...
opening an Ext4v2 formatted hdd in a Ext4v1 machine,
will corrupt the headers of the Ext4v2 hdd, making it unreadable in Linux 20.04 with Ext4v2.

opening an Ext4 formatted hdd in a Ext4 machine,
will corrupt the headers of the Ext4 hdd, making it unreadable in Linux 20.04 with Ext4.

Thats how crazy it is.

Example:
The project Ext2fsb 0.69 was a Windows driver that allowed to R&W Ext4 in Windows8,1, W10.
if you open Ext4v2 in Ext2fsb0.69 will corrupt the HDD headers,
Will be readable Only to Windows Ext2fsb driver, 
imposible to read & repair in Linux 20.04

Ext4v2 is much better, 
Ext4v1 was faster than NTFS, but Linux 10.04 & 10.10 did Not had Power Loss Fail Safe Security,
like Apple HFS+ Journaled "circular log",
if you move files in Ext4v1 and power is lost, files are lost, in Linux 10.x era.
Now thats a thing of the past.
Ext4v2 does Not have that problem.

Other Problem:
Ext2Fsb 0.69 project was abandoned by its developer,
someone resumed / forked the driver, and created an unofficial 0.70 Ext2fsb,
but... its far from perfect.
requires Windows Test Mode,
https://www.acc.umu.se/~bosse/
https://www.acc.umu.se/~bosse/ext2fsd/
https://www.acc.umu.se/~bosse/ext2fsd/0.70/

https://github.com/bobranten/Ext4Fsd

The Search for the Perfect File System continues.
Linux is Bad for ExFAT,
but ExFAT is the only File System that can be Read&Write in Windows & Mac without special drivers.
ExFAT is a common File Format for Mac & Win.
ExFAT is Not as good as NTFS,
Mac can Read NTFS, Not write, unless you use one of the NTFS drivers, free and Paid from Paragon, 
there is a big speed difference between drivers.

Windows cannot Read HFS+, unless you buy the Paragon driver, or have Bootcamp in a Mac machine.
Bootcamp in a Non Mac wont Write nor Move.

To solve all those problems is better to have a File Server NAS.
but what to install in the file server?
Wikipedia claims NTFS is far superior than HFS+, but needs constant defrag.
HFS+ does Not Need Defrag, because it seems OSX does defrag every time a file is access.
but there is a Software, very rare, that allows to defrag HFS+

Ext4 looks nice, if only used in Linux.

Linux can read & write all formats, 
but wikipedia claims Linux hfsplus and hfsprogs are incomplete and dangerous.
the only strange thing ive seen is that: Linux HFS+ cannot be Named, and cannot be seen by Bootcamp5.x drivers.
but can be Named in OSX and detected Ok.

So far i have Not found a Universal File Format, 
thats why a File Server is the best option, with fast 10G ethernet that allows a max speed of 1200MB/s.

Windows File server requires constant defrag.
Linux HFS+ could be interesting if only using Linux & OSX, seems to have less issues than ExFAT in Linuxm, also Linux HFS+ is the fastest.
ExFAT is  Not recommended, unless is an emergency, or a small drive, Not a 2TB or larger.
Ext4v2 good for linux 20.x.

Seems that having an External USB3.0 drive is Not a good option if need 3 operating systems.
but is Ok if only using 1 operating system.

a Linux file server with dedicated external USB3.0 drive?

There is also the dilema of a RAID 1 .
for me RAID 1 does Not seem to have logic,
because both redundant HDD are spinning all the time, at same time.
weaaring and getting old at the same time, makes No sense to me.
a Daily backup, seems too tedious, unless its automated.
but the wear of the backup drive will be minimal.
a backup each week, less tedious.

There are different Sync Softwares,
All Way Sync for Windows is very good, but i dont like NTFS Defrag.
Apple has command line rsync, and there is a GUI frontend.

Raid 1 Mirrired makes less sense to me today, 
i want to extend the life of the Backup hdd as much as possible,
minimal wear, less probablility of failure, unless bad luck.
If Mirror had asymetric Time...

for an Online server that needs fail safe 24/7 thats another story.
Raid 1 or 10 is mandatory.
Or a company that cannot risk losing 1 to 24 hours of information.

Cheap Solid SSD requires Anual Backup minimum.
The Search continues.

Ext4v2 in Windows is Not a fail safe option at this moment.
Ext4v1 was, but...

its like H2o molecule, every time i think about moving files directly from Linux, Windows & Mac File Systems,
exactly the same.
1x Hydrogen molecule cannot touch the other Hydrogen molecule directly.
needs a buffer, a joiner, a barrier, emulsion, like an Oxygen molecule,
thats what i think.

The other option, requires FAil Safe UPS,
a RAM Drive,
Oxygen Molecule could be a Ram drive.
with a board that allows ECC, and a very large quantity of RAM, 1TB or more.
that could help move the files faster from A to B.

a Ram Drive or a File Server is like the Oxygen molecule.

Different File Systems repel each other like Molecules with the same charge.
like water & oil, immiscible in normal conditions.

¿What is the Best File System for HDD bigger than 2TB ?
hard lesson ahead.
