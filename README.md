# Ext4-File-System-v1-vs.-v2
BEWARE!

== Ext4 filesystem ==
Ext4 v1 has 32-Bit header since the Linux 10.04 era, but...
Ext4 v2 has 64-Bit header since Linux 20.04 era, maybe early Linux 16.04 18.04, dont know exacty when the change was made.

Gnomne Disks say Ext4 is v1,00
but that cannot be possible.

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

Sadly Linux HFs+ goes crazy over 2TB HDD, just mounts 400MB.
after decades still nobody has fixed hfsplus and hfsprogs

Ext4 v2 has Journaled, like Mac HFS+, but is Not circular, its spread all over the disk,
and that makes the HDD create very weird Noises at IDLE...
Formating 18TB when writing Superblocks
sounds like a Waterfall,
then at IDLE sounds like a Helicopter Blades, 
when "quiet" has constant access.
there are many forums online with similar problem.
so much access will kill mechanic HDD,

There are 2 Theories:

A) HDD Energy Efficient Disk / Head Park does Not work well, 
Firmware Issue or something...

https://askubuntu.com/questions/141075/excessive-hard-disk-activity


B) Ext4 v2 Journaling created the problem...
but Gparted and Gnome Disks do Not allow to Disable Journal when formatting Ext4,
like OSX that does allow to select Journaling,
but Mac HFS+ Journaling is circular, does Not create crazy noises for long periods of time.

https://www.hecticgeek.com/ext4-external-hard-disk-busy-at-idle-fix/

https://www.linuxquestions.org/questions/linux-general-1/ext4-journaling-process-constantly-accessing-hard-drive-does-not-go-into-sleep-mode-4175686913/

$ sudo ps -ef|grep jbd2

root         391       2  0 10:34 ?        00:00:01 [jbd2/sda3-8]
root        2188       2  0 10:34 ?        00:00:00 [jbd2/sdb1-8]
root        2190       2  0 10:34 ?        00:00:00 [jbd2/sda4-8]
root       21239       2  0 12:08 ?        00:00:00 [jbd2/sdc1-8]
Linux       21651   21197  0 12:13 pts/1    00:00:00 grep --color=auto jbd2

$ sudo iotop -obtqqq | grep sdc1

12:10:17   21239 be/3 root        0.00 B/s    3.83 K/s  0.00 %  0.80 % [jbd2/sdc1-8]
12:10:22   21239 be/3 root        0.00 B/s    3.83 K/s  0.00 %  0.80 % [jbd2/sdc1-8]
12:10:27   21239 be/3 root        0.00 B/s    3.83 K/s  0.00 %  0.80 % [jbd2/sdc1-8]
12:10:33   21239 be/3 root        0.00 B/s    7.66 K/s  0.00 %  0.81 % [jbd2/sdc1-8]
12:10:38   21239 be/3 root        0.00 B/s    3.84 K/s  0.00 %  0.81 % [jbd2/sdc1-8]
12:10:43   21239 be/3 root        0.00 B/s    3.83 K/s  0.00 %  0.10 % [jbd2/sdc1-8]


the only way to know if the problem is A) or B)
is to format again, without Journaling,
Ext4 Only, No Journal.

----------

$ sudo mkfs -t ext4 -E lazy_itable_init=0,lazy_journal_init=0 /dev/sdc

mke2fs 1.45.6 (20-Mar-2020)
Found a gpt partition table in /dev/sdc
Proceed anyway? (y,N) y
Creating filesystem with 4394582016 4k blocks and 274661376 inodes
Filesystem UUID: 176d366a-e5e7-429e-a7d5-c4baa5d3eb72
Superblock backups stored on blocks: 
        32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208, 
        4096000, 7962624, 11239424, 20480000, 23887872, 71663616, 78675968, 
        102400000, 214990848, 512000000, 550731776, 644972544, 1934917632, 
        2560000000, 3855122432

Allocating group tables: done                            
Writing inode tables: done                            
Creating journal (262144 blocks): done
Writing superblocks and filesystem accounting information: done        

------------
DONE, problem "solved"..

but Journal is awesome...
https://en.wikipedia.org/wiki/Journaling_file_system

if Ext4 Journal is set active, constant access will kill the HDD.
if dissabled, HDD can become corrupted after a power loss or system crash.

Means Ext4 is Not the best file system for drives bigger than 2TB.
Wikipedia say that Ext4 is better because Journal flush the cache properly at certain points.

Theory is different than real life.

in OSX Journaling works Ok, No weird noises.
but Linux HFS+ does Not Mount HDD bigger than 2TB, goes crazy.

Win8.1 NTFS works Ok, No weird noises.
Gparted cannot format 18TB with NTFS.

Gparted Ext4 does Not work without Journaling.
Disk "works" 
Ext4 (version 1.0) — Mounted at /media/Linux/blablabla-blabla-blablabla


Other contenders:
XFS developed by SGI in 2004 for IRIX OS.

Btrfs Copy-On-Wire developed by Oracle in 2007

F2FS Flash Storage developed by Samsung in 2012

Ext4 v1.00 2006

ExFAT Microsoft 2006

https://en.wikipedia.org/wiki/Comparison_of_file_systems - 
https://en.wikipedia.org/wiki/List_of_file_systems

UDF Unversal Disk Format

Btrfs seems the best candidate to test Next.
https://en.wikipedia.org/wiki/Btrfs

XFS also looks very advanced for its time...
and development continued in the Linux Kernet,
the only problems:
https://en.wikipedia.org/wiki/XFS#Disadvantages

-----
5 Hours doing LuckyBackup Rsync ... OK
NTFS to XFS

----

Alternatives:

Method A) Have a Dedicated File Server.
Linux, Windows, OSX.

Method B) have a compatible File System across all machines,
and move HDD physically.

The main FS drivers ive seen:
Paragon Paid.
macFUSE.
Ext2Fsb >0.70

macFUSE can Read XFS in OSX,
Paragon can Read XFS on Windows. 
Paragon can Read Btrfs on Windows. 

EaseUS claims their File Explorer in the Partition Manager allows to Read Linux File Systems,
minitool is unknown.
the other Partition File Recovery Softwares also unknown.

The Most compatible FileSystems are APFS and Ext4 from Paragon.

Paragon has developed APFS drivers for Linux, Windows, Old OSX 10.10 Yosemite, 10.11 El CApitan, 10.12 Sierra,
APFS comes Free in OSX HighSierra, is compatible with Intel and M1.

also has developed Ext2/3/4 for Windows "paid Ext2Fsb", 
and Ext2/3/4 for OSX "paid macFUSE".
Linux comes with Ext2/3/4


APFS seems the most compatible alternative to people that do Not want a Dedicated 10G SFP+ File Server..

Paragon HFS+ Driver for Windows in theory could load >2TB HDD in Linux.


https://superuser.com/questions/429770/mount-xfs-partition-on-os-x-using-osxfuse

https://github.com/osxfuse/osxfuse/wiki/List-of-macFUSE-File-Systems

https://github.com/osxfuse/osxfuse/releases

https://sourceforge.net/projects/fusexfs/files/releases/

https://www.paragon-software.com/home/linuxfs-windows/#

https://www.paragon-software.com/about/products-a-to-z/


Linux comes with Free NTFS and HFS+ drivers,
but Paragon claims their drivers are Faster & Better.
interesting.

https://www.paragon-software.com/home/ntfs-linux-professional/#

https://www.paragon-software.com/home/hfs-windows/#

APFS

https://www.paragon-software.com/home/apfs-linux/#

https://www.paragon-software.com/home/apfs-windows/#


Btrfs
https://www.paragon-software.com/business/btrfs-for-windows/#


ReFS Windows Server

https://www.paragon-software.com/business/refs-linux/#

https://www.paragon-software.com/business/refs-for-windows/#


Ext2/3/4 for OSX

https://www.paragon-software.com/home/extfs-mac/#

Ext2/3/4 for Windows

https://www.paragon-software.com/business/extfs-for-windows/#

https://www.paragon-software.com/home/linuxfs-windows/#

Paragon Propietary SDK FileSystem

https://www.paragon-software.com/paragon-file-system/#

----

6:30 Hours Rsync ...

