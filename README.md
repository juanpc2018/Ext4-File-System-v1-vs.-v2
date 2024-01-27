# Ext4-File-System-v1-vs.-v2</br>
BEWARE!</br>

== Ext4 filesystem ==</br>
Ext4 v1 has 32-Bit header since the Linux 10.04 era, since 2006-2008 but...</br>
Ext4 v2 has 64-Bit header since Linux 20.04 era, maybe early Linux 16.04, 18.04, dont know exacty when the change was made.</br>

Gnome Disks say Ext4 is v1,00</br>
but that cannot be possible.</br>

The problem:</br>
Not backward compatible,</br>
Has the same Name.</br>
Ext4 v2 or Ext4 64-Bit should have been called Ext5.</br>

Anyway...</br>
open/mount an Ext4v2 formatted hdd in a Ext4v1 machine,</br>
will corrupt the headers / magic numbers of the Ext4v2 hdd, </br>
making it unreadable in Linux 20.04 with Ext4v2.</br>

open/mount an Ext4 formatted hdd in a Ext4 machine,</br>
will corrupt the headers of the Ext4 hdd, making it unreadable in Linux 20.04 with Ext4.</br>

Thats how crazy it is.</br>

Example:</br>
The project [Ext2Fsb](https://en.wikipedia.org/wiki/Ext2Fsd) v0.69 was a Windows driver that allowed to R/W Ext4 v1.0 32-Bit in Windows8,1, W10.</br>
if you open Ext4 v2 / 64-Bit in Ext2fsb 0.69 will corrupt the HDD headers,Magic Numbers</br>
Will be readable Only to Windows Ext2fsb driver, </br>
imposible to read & repair in Linux 20.04</br>

Ext4 v1 was faster than NTFS, but Linux 10.04 & 10.10 did Not had Power Loss Fail Safe Security,</br>
like Apple HFS+ Journaled "circular log",</br>
if you move files in Ext4v 1 and power is lost, files are lost, Linux 10.x era.</br>
Now thats a thing of the past.</br>
Ext4 v2 does Not have that problem.</br>

Other Problem:</br>
Ext2Fsb 0.69 project was abandoned by its developer,</br>
someone resumed / forked the driver, and created an unofficial 0.70 Ext2fsb,</br>
but... its far from perfect, </br>
and requires Windows Test Mode to install,</br>
https://www.acc.umu.se/~bosse/</br>
https://www.acc.umu.se/~bosse/ext2fsd/</br>
https://www.acc.umu.se/~bosse/ext2fsd/0.70/</br>
https://github.com/bobranten/Ext4Fsd</br>

The Search for the Perfect File System continues.</br>
Linux is Bad for ExFAT,</br>
but ExFAT is the only File System that can be Read&Write in Windows & Mac without special drivers.</br>
ExFAT is a common File Format for Mac & Win.</br>
ExFAT is Not as good as NTFS,</br>
Mac can Read NTFS, Not write, unless you use one of the NTFS drivers, free and Paid from Paragon, </br>
there is a big speed difference between drivers.</br>

Windows cannot Read HFS+, unless you buy the Paragon driver, or have Bootcamp in a Mac machine.</br>
Bootcamp in a Non Mac wont Write nor Move.</br>

To solve all those problems is better to have a File Server NAS.</br>
but what to install in the file server?</br>
Wikipedia claims NTFS is far superior than HFS+, but needs constant defrag.</br>
HFS+ does Not Need Defrag, because it seems OSX does defrag every time a file is access.</br>
but there is a Software, very rare, DiskTools Pro by Macware that allows to defrag HFS+</br>

Ext4 looks nice, if only used in Linux.</br>

Linux can read & write all formats, </br>
but wikipedia claims Linux hfsplus and hfsprogs are incomplete and dangerous.</br>
the only strange thing ive seen is that: Linux HFS+ cannot be Named, and cannot be seen by Bootcamp5.x drivers.</br>
but can be Named in OSX and detected Ok.</br>

So far i have Not found a Universal File Format, </br>
thats why a File Server is the best option, with fast 10G ethernet that allows a max speed of 1200MB/s.</br>

Windows File server requires constant defrag.</br>
Linux HFS+ could be interesting if only using Linux & OSX, seems to have less issues than ExFAT in Linuxm, also Linux HFS+ is  faster.</br>
ExFAT is Not recommended, unless its an emergency, or a small drive, Not a 2TB or larger.</br>
Ext4v2 good for linux 20.x.</br>

Seems that having an External USB3.0 drive is Not a good option if need 3 operating systems.</br>
but is Ok if only using 1 operating system.</br>

a Linux file server with dedicated external USB3.0 drive?</br>

There is also the dilema of a RAID 1.</br>
for me RAID 1 does Not seem to have logic,</br>
because both redundant HDD are spinning all the time, at same time.</br>
weaaring and getting old at the same time, makes No sense to me.</br>
a Daily backup, seems too tedious, unless its automated.</br>
but the wear of the backup drive will be minimal.</br>
a backup each week, less tedious.</br>

There are different Sync Softwares,</br>
All Way Sync for Windows is very good, but i dont like NTFS Defrag.</br>
Apple has command line rsync, and there is a GUI frontend.</br>

Raid 1 Mirrired makes less sense to me today, </br>
i want to extend the life of the Backup hdd as much as possible,</br>
minimal wear, less probablility of failure, unless bad luck.</br>
If Mirror had asymetric Time...</br>

for an Online server that needs fail safe 24/7 thats another story.</br>
Raid 1 or 10 is mandatory.</br>
Or a company that cannot risk losing 1 to 24 hours of information.</br>

Cheap Solid SSD requires Anual Backup minimum.</br>
The Search continues.</br>

Ext4v2 in Windows is Not a fail safe option at this moment.</br>
Ext4v1 was, but...</br>

its like H2o molecule, every time i think about moving files directly from Linux, Windows & Mac File Systems,</br>
exactly the same.</br>
1x Hydrogen molecule cannot touch the other Hydrogen molecule directly.</br>
needs a buffer, a joiner, a barrier, emulsion, like an Oxygen molecule,</br>
thats what i think.</br>

The other option, requires FAil Safe UPS,</br>
a RAM Drive,</br>
Oxygen Molecule could be a Ram drive.</br>
with a board that allows ECC, and a very large quantity of RAM, 1TB or more.</br>
that could help move the files faster from A to B.</br>

a Ram Drive or a File Server is like the Oxygen molecule.</br>

Different File Systems repel each other like Molecules with the same charge.</br>
like water & oil, immiscible in normal conditions.</br>

¿What is the Best File System for HDD bigger than 2TB ?</br>
hard lesson ahead.</br>

Sadly Free Linux HFs+ goes crazy over 2TB HDD, just mounts 400MB.</br>
after decades still nobody has fixed hfsplus and hfsprogs</br>
why? because there is a Paid HFS+ for Linux from Paragon.</br>
claims complete file support, and comes bundle with better/faster NTFS for Linux.</br>

Ext4 v2 has Journaled, like Mac HFS+, but is Not circular, its spread all over the disk,</br>
and that makes the HDD create very weird Noises at IDLE...</br>
Formating 18TB when writing Superblocks</br>
sounds like a Waterfall,</br>
then at IDLE sounds like a Helicopter Blades, </br>
when "quiet" has constant access.</br>
there are many forums online with similar problem.</br>
so much access will kill mechanic HDD,</br>

There are 2 Theories:</br>

A) HDD Energy Efficient Disk / Head Park does Not work well, </br>
Firmware Issue or something...</br>

https://askubuntu.com/questions/141075/excessive-hard-disk-activity</br>

B) Ext4 v2 Journaling created the problem...</br>
but Gparted and Gnome Disks do Not allow to Disable Journal when formatting Ext4,</br>
like OSX that does allow to select Journaling,</br>
but Mac HFS+ Journaling is circular, does Not create crazy noises for long periods of time.</br>

https://www.hecticgeek.com/ext4-external-hard-disk-busy-at-idle-fix/</br>

https://www.linuxquestions.org/questions/linux-general-1/ext4-journaling-process-constantly-accessing-hard-drive-does-not-go-into-sleep-mode-4175686913/</br>

$ sudo ps -ef|grep jbd2</br>

root         391       2  0 10:34 ?        00:00:01 [jbd2/sda3-8]</br>
root        2188       2  0 10:34 ?        00:00:00 [jbd2/sdb1-8]</br>
root        2190       2  0 10:34 ?        00:00:00 [jbd2/sda4-8]</br>
root       21239       2  0 12:08 ?        00:00:00 [jbd2/sdc1-8]</br>
Linux       21651   21197  0 12:13 pts/1    00:00:00 grep --color=auto jbd2</br>

$ sudo iotop -obtqqq | grep sdc1</br>

12:10:17   21239 be/3 root        0.00 B/s    3.83 K/s  0.00 %  0.80 % [jbd2/sdc1-8]</br>
12:10:22   21239 be/3 root        0.00 B/s    3.83 K/s  0.00 %  0.80 % [jbd2/sdc1-8]</br>
12:10:27   21239 be/3 root        0.00 B/s    3.83 K/s  0.00 %  0.80 % [jbd2/sdc1-8]</br>
12:10:33   21239 be/3 root        0.00 B/s    7.66 K/s  0.00 %  0.81 % [jbd2/sdc1-8]</br>
12:10:38   21239 be/3 root        0.00 B/s    3.84 K/s  0.00 %  0.81 % [jbd2/sdc1-8]</br>
12:10:43   21239 be/3 root        0.00 B/s    3.83 K/s  0.00 %  0.10 % [jbd2/sdc1-8]</br>

the only way to know if the problem is A) or B)</br>
is to format again, without Journaling,</br>
Ext4 Only, No Journal.</br>

----------</br>

$ sudo mkfs -t ext4 -E lazy_itable_init=0,lazy_journal_init=0 /dev/sdc</br>

mke2fs 1.45.6 (20-Mar-2020)</br>
Found a gpt partition table in /dev/sdc</br>
Proceed anyway? (y,N) y</br>
Creating filesystem with 4394582016 4k blocks and 274661376 inodes</br>
Filesystem UUID: 176d366a-e5e7-429e-a7d5-c4baa5d3eb72</br>
Superblock backups stored on blocks: </br>
        32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208, </br>
        4096000, 7962624, 11239424, 20480000, 23887872, 71663616, 78675968, </br>
        102400000, 214990848, 512000000, 550731776, 644972544, 1934917632, </br>
        2560000000, 3855122432</br>

Allocating group tables: done </br>
Writing inode tables: done </br>
Creating journal (262144 blocks): done</br>
Writing superblocks and filesystem accounting information: done </br> 

------------</br>
DONE, problem "solved"..</br>

but Journal is awesome...</br>
https://en.wikipedia.org/wiki/Journaling_file_system</br>

if Ext4 Journal is set active, constant access will kill the HDD.</br>
if dissabled, HDD can become corrupted after a power loss or system crash.</br>

Means Ext4 is Not the best file system for drives bigger than 2TB.</br>
Wikipedia say that Ext4 is better because Journal flush the cache properly at certain points.</br>

Theory is different than real life.</br>

in OSX Journaling works Ok, No weird noises.</br>
but Linux HFS+ does Not Mount HDD bigger than 2TB, goes crazy.</br>

Win8.1 NTFS works Ok, No weird noises.</br>
Gparted cannot format 18TB with NTFS.</br>

Gparted Ext4 does Not work without Journaling.</br>
Disk "works" </br>
Ext4 (version 1.0) — Mounted at /media/Linux/blablabla-blabla-blablabla</br>


Other contenders:</br>
XFS developed by SGI in 2004 for IRIX OS.</br>

Btrfs Copy-On-Wire developed by Oracle in 2007</br>

F2FS Flash Storage developed by Samsung in 2012</br>

Ext4 v1.00 2006</br>

ExFAT Microsoft 2006</br>

https://en.wikipedia.org/wiki/Comparison_of_file_systems - </br>
https://en.wikipedia.org/wiki/List_of_file_systems</br>

UDF Unversal Disk Format</br>

Btrfs seems the best candidate to test Next.</br>
https://en.wikipedia.org/wiki/Btrfs</br>

XFS also looks very advanced for its time...</br>
and development continued in the Linux Kernet,</br>
the only problems:
https://en.wikipedia.org/wiki/XFS#Disadvantages</br>

-----</br>
5 Hours doing LuckyBackup Rsync ... OK</br>
NTFS to XFS</br>

----</br>

Alternatives:</br>

Method A) Have a Dedicated File Server.</br>
Linux, Windows, OSX.</br>

Method B) have a compatible File System across all machines,</br>
and move HDD physically.</br>

The main FS drivers ive seen:</br>
Paragon Paid.</br>
macFUSE.</br>
Ext2Fsb >0.70</br>

macFUSE can Read XFS in OSX,</br>
Paragon can Read XFS on Windows. </br>
Paragon can Read Btrfs on Windows. </br>

EaseUS claims their File Explorer in the Partition Manager allows to Read Linux File Systems,</br>
minitool is unknown.</br>
the other Partition File Recovery Softwares also unknown.</br>

The Most compatible paid driver FileSystems:</br>
APFS</br>
HFS+ for Linux and HFS+ for Windows from Paragon.</br>
Ext4 from Paragon.</br>

APFS driver for Linux, </br>
APFS driver for Windows, </br>
APFS driver dor Old OSX 10.10 Yosemite, 10.11 El Capitan, 10.12 Sierra,</br>
APFS comes in OSX HighSierra, compatible with Intel and M1.</br>

Ext2/3/4 for Windows "paid Ext2Fsb", </br>
Ext2/3/4 for OSX "paid macFUSE".</br>
Linux comes with Ext2/3/4 Native.</br>

HFS+ for Linux.</br>
HFS+ for Windos.</br>
OSX comes with HFS+ Native.</br>

the most compatible alternatives to people that do Not want a dedicated 10G SFP+ File Server..</br>

Paragon HFS+ Driver for Windows in theory could load >2TB HDD in Linux.</br>
will see.</br>

https://superuser.com/questions/429770/mount-xfs-partition-on-os-x-using-osxfuse</br>

https://github.com/osxfuse/osxfuse/wiki/List-of-macFUSE-File-Systems</br>

https://github.com/osxfuse/osxfuse/releases</br>

https://sourceforge.net/projects/fusexfs/files/releases/</br>

https://www.paragon-software.com/about/products-a-to-z/</br>


Linux comes with Free NTFS and HFS+ drivers,</br>
but Paragon claims their drivers are Faster & Better.</br>
interesting.</br>
https://www.paragon-software.com/home/ntfs-linux-professional/#</br>
https://www.paragon-software.com/home/hfs-windows/#</br>

APFS</br>
https://www.paragon-software.com/home/apfs-linux/#</br>
https://www.paragon-software.com/home/apfs-windows/#</br>

Btrfs</br>
https://www.paragon-software.com/business/btrfs-for-windows/#</br>

ReFS Windows Server</br>
https://www.paragon-software.com/business/refs-linux/#</br>
https://www.paragon-software.com/business/refs-for-windows/#</br>


Ext2/3/4 for OSX</br>
https://www.paragon-software.com/home/extfs-mac/#</br>

Ext2/3/4 for Windows</br>
https://www.paragon-software.com/business/extfs-for-windows/#</br>
https://www.paragon-software.com/home/linuxfs-windows/#</br>

Paragon Propietary SDK FileSystem</br>
https://www.paragon-software.com/paragon-file-system/#</br>

----</br>

6:30 Hours Rsync ...</br>

----</br>

7:00 Hours Rsync ...</br>

----</br>

18:00 Hours Rsync and some Files FAiled, on the Linux Free NTFS driver side.</br>

Option A) Buy the Paragon NTFS Pro driver for Linux. Rsync again should be much faster, most of the work is done.</br>

Option B) Install the NTFS 18TB HDD in Windows8.1, </br>
Share with Samba3, 10G SPF+ Direct Network, Rsync from Shared Windows HDD.</br>

----</br>
ADVISE:</br>

When moving many small HDD to a 1x large HDD, many 500MB & 1TB to 1x 18TB HDD.</br>

there are different methods:</br>

A) select all files & folders & copy as is,</br>
duplicated files & folders will be detected.</br>
good option if want to optimize space, but is risky.</br>

B) copy each HDD to a separaded folder,</br>
duplicated files & folders will be copied too and more space is required.</br>
but is safer, then copy from the same large HDD to main path to detect duplicated files & folders.</br>
double the work, more space needed, but safer.</br>
