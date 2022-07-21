# **BASIC SYNTAX OF BASH**

>command [-options] [arguments]

# **HELP WITH LINUX**
>man {command}
```v
man pages
//manuals for any command in linux
*not every command will be found
```

# **BASIC BASH COMMANDS**
>echo {arguments}
```v
ex:
echo whats up
returns: "whats up"

// Commonly used to send information to the user in a script
ls
list
//list directory contents

ls -i
inode
//print the index number of each file

ls -lh
//list directory contents and use  long listing format in human readable form

ls - la 
//List D in long format w/ Hidden -

ls /var/log
//list d contents of /var/

ls -la /var/log
//list d contents of /var/ in long format w/hidden -
```

>**pwd**
```v
//displays the current d you are working on
```

>**cd**
```v
//changes your current d
```

>cd /var/log
```v
//changes current d to /var/log where system files are
```

>cd /etc
```v 
//changes to /etc
```
>**touch**
```v
//updates timesstamp/creates file
```
>touch file1
```v
//updates the timestamp of file. creates a file if it doesn't exist.
```
>cp
```v
//copies - or d to another location
```
>cp file1 file2
```v
//copies the file1 to file2
```
>mkdir
```v
//creates a d
```
>mkdir newdir
```v
//makes new d called newdir
```
# **FILE VIEWING COMMANDS**
>cat file1
```v
//show contents
```
>less file1
```v
//view contents formatted to screen
```
>tail -f less file1
```v
//allows you to view the end of a file

//-f allows for you to read file as it grows
```
# **FILE EDITING COMMANDS**
>vim file1
```v
 //open powerful text editor
 ```
 >vi gastelo.txt
 ```v
 //allows you to open a new txt file in the name of gastelo.txt and edit how you fit. save it and produce it with :
   
      
      cat gastelo.txt
```
>nano file1

```v
//opens user friendly text editor
```
>gedit
```v 
//requires desktop enviro & needs to start manually via apps
```
# **POWER MANAGEMENT COMMANDS**
>shutdown -h 
```v
//shuts down no time delay
```
>shutdown -h -t 90 
```v
//shuts down in 90 sec
```
>shutdown -r
```v
//reboots the system with no timed delay
```
>sleep 180
```v
//stalls prompt for the amount of seconds specified
```
# **SUPERUSER COMMANDS**
>su -
```v
//"substitute user" switches creds
```
>su - root
```v
//switches credentials to the root user
```
# **sudo COMMAND**
>sudo [options] {command}
```v
//enables admin to delegate specific commands to specific users, w/out full privileges on server.
```
>/etc/sudoers
```v
//delegation is done in sudoers file via VISUDO editor
```
# **sudoedit COMMAND**  
>sudoedit [options]{command}
```v
//permits user to edit a file w/ own creds
```
# **visudo COMMAND**
>visudo [options]
```v
//a saftey net like editor, checking your work after and giving you an option IF it detects a problem. PRETTY COOL

visudo -c
//check sudoers file for errors

visudo -f
//edit check sudoers file in diff location

visudo -s
//check sudoers in strict mode

visudo -x {file name}
//output sudoers file to the specified file in javascript Object Notation(JSON)format
```
# **useradd COMMAND**
>useradd
```v
//used to create user accounts

useradd -c "User one" user1 
//sets the comment field
getent
useradd -e 2019/12/31
//sets expiration

useradd -s /bin/ksh
//sets user default shell

useradd -D 
//view default configs for new users

//acount is stored /etc/passwd

//acount is config to options set in   /etc/login.defs

//account's home dir is /home/<user1>

//acount home directory is populated using files from /etc/skel directory
```
# **adduser COMMAND**
>adduser gasteloj
```v
//adds user differently than the useradd which doesn't make you enter password right away.Wants more detail.
```
# **passwd COMMAND**
```v
//used by root to set or reset any user

//etc/passwd

//stores user account info. All accounts

//etc/shadow

//modern storage location for hashed passwords & additional account info
```
# **chage COMMAND**
>chage [options] {user1}
```v
//used to control password expiration, expiration warnings, inactive days, and other info.

chage -E 2022/12/31 user1
//sets account to expire

chage -l user1  
//list passwrd aging info

chage -M 90 user1  
//sets max days of validity

chage -m 1 user1  
//sets min days until changed

chage -W 5 user1  
//# of days before expiration
```
# **usermod COMMAND**
>usermod [options] {user1}
```v
//modify settings for reg users

usermod -c "User One" user1
//sets comment field

usermod -e 2020/12/31 user1
//sets account expiration

usermod -aG sales-group user1
//adds user to a group

usermod -l user99 user1
//changes the user's login name
```
# **LOCK USER LOGIN**
```v
//utilize if user leaves company or security breach or whenever someone takes a long leave of absence.

passwd -l user1 or 
usermod -L user1
Locks

passwd -u user1
passwd -U user1
unlocks
```
# **userdel COMMAND**
>userdel [options] {user1}
```v
//used to delete accounts

userdel -r {user1}

//used to delete all traces of account
```
# **GROUP ACCOUNTS**
>/etc/group
```v
//is a storage location for groups
```
# **groupadd COMMAND**
>groupadd [options] {TeamA}
```v
//creates a group

groupadd -g 123 sales
//assign a group ID

groupadd -f sales
//exit with a sucess status if group exist

groupadd -o -g sales
//create group with non-unique group ID
```
# **groupmod COMMAND**
>groupmod [options] {TeamA}

```v
//used to change groups attributes

groupmod -g 123 sales
//change group ID

groupmod -n newsales sales
//rename group
```
# **groupdel COMMAND**
>groupdel [options] {TeamA}

```v
//delete groups from the /etc/group
```
>**delgroup COMMAND**
```v
//allows you to delete group from system
```
# **ACCOUNT QUERYING**
>**whomami**
```v
//displays current user
```
>**who**

>who [options]

>who -u
```v
//used to see how long users been idle
 users were active last 24hrs, old= inactive over 24 hours
```
**w**


>w [options] {user1}
```v
//displays current users currently logged on into system and their transactions.
```
>**last**

>last [options]
```v
//displays history of user login actions
```
>**id**

>id [options] {user1}

```v
//display user ID and Group ID
```
>**top**
```v
//gives you a look a different processes running on system.
```
>**/etc/profile**
```v
// provides system-wide enviroment variables
```
>**/etc/profile.d/**
```v
//serves as a strorage location for scripts
```
>**/bashrc**

>/etc/bashrc
```v
// provides system-wide bash settings
```
>**grep**

>cat /etc/passwd | grep gastelojallday

>grep {file name}
```v
//grep searches for that specific word(s)

//used for searching within the files
```
>**Find**
```v
// is used for filename search
```

> **PERMISSIONS**
```v
//Permissions are access rights asssigned to users, which enable them to access or modify certain files and directories.
```

> ls  -l
```v
//commmand gives you a long list of directories in your current working directory.
```

>**Permission ATTRIBUTES**
```v
//define exactly what a user is allowed to do with a particular file or directory.

//R access and view contents

//W save changes, create, rename, delete

//X run a script, execute file 
```


>**PERMISSION CONTEXTS**
```v
//permission attributes are applied to one of several contexts including users and entities.

//Owner(u) owner of file

//Group(g)file or directory group

//Other(o) all other users
```
```v
>PERMISSION STRING

//contains 11 characters
x-xxx-xxx-xxx-x

-/or d type of object file or directory
user permissions(2-4)
group permissions(5-7)
other permissions(8-10)
```
#  **chmod COMMAND**
>chmod [options] {mode} {file/directory name}

```v
//enables you to modify the permissions of file or directory
 chmod -c 
//report changes 

chmod -f
//hide most error messages

chmod -v
//displays a diagnostic entry for every file processed

chmod -R
//modify permissions of files and directories recursively.
```
# **SYMBOLIC mode**
>chmod {access context} {operators}{permissions attributes} {file/directory names}

>chmod u+rw, g+rw myfile

```v
Permission contexts: u/g/o/  a(all three)
operators: +/-/=
attributes: r/w/x

//Examples:

chmod g+r file1
//gives group read permission to file

chmod o-r file1
//recovers read for others

chmod go+rw file1
//gives group and others read and write
```
# **ABSOLUTE MODE & KEY MATRIX**

```v
chmod {number} {file /directory name}

chmod 764 file1-rwxrw-r--
chmod 700 file1-rwx------
chmod 640 file1-rw-r-----

//other chmod mode, uses octal(base-8) to dicatate permissions:
```
```
7 rwe

6 rw-

5 r-e

4 r--

3 -we

2 -w-

1 --e
```
# **umask COMMAND**
>umask {number}
```v
//default umask : 022

//alters default permissions on newly created files and directories.(temp)

//change bashrc file if you want to change it permenantely
```
# **chown COMMAND**
>chown {user1} {file/directory name}
```v
//changes the owner but NOT group

chown {user1} {group name} {file/directory name}

//changes owner and the group

chown {user1} {file/directory name}

//changes the owner and group.

chown :{TeamA} {file/directory name}
```

# **chgrp COMMAND**
>chgrp {TeamA} {file/directory name}
* syntax

>chgrp staff /u
* change the group of /u to "staff"

>chgrp -hR staff /u

* change the group of /u and subfules to "staff"
```v
//CHANGE GROUP OWNERSHIP
change the group of each FILE to GROUP

-c changes
//like verbose but report only when a change is made

-f silent
//supress most error messages

-v verbose
//output a diagnostic for every file processed
   
   dereference
   //affect the referent of each symbolic link

-h no-dereference
//affect symbolic links instead of any referenced file
   
   no-preserve-root
   //do not treat '/' specially
   
   preserve-root
   //fail to operate recursively on '/'
   
   reference=RFILE
   //use RFILE's group rather than specifying a GROUP value

-R recursive
//operate on files and directories recursively

-H 
//if a command line argument is a symbolic link, traverse it

-L 
//traverse every symbolic links

-P 
//do not traverse any symbolic links(default)
```
# **SUID AND SGID PERMISSIONS**

### **SUID**
>chmod u+s {file names}

>chmod 4### {file names}
```v 
//is the permission that allows a user to have similar permission as the owner of the file.
setting up the SUID on a file
```

### **SGID**
>chmod g+s {file names}

>chmod 2### {directory names} 
```v
//is the permission that allows a user to have similar permissions as the group owner of the file.

//SGID can also be set on directories.

**subdirectories will inherit the SGID permissions.
setting up the SGID on a directory
```
# **STICKY BIT**
>chmod + t {directory names}

>chmod 1## {directory names}
```v
//a special permission that makes sure even with read, write permission that you can't delete a file without owner permission

//t or T could be assigned in either fashion

to clear the stick bit, 
use - or 0
```
# **FILE ATTRIBUTES**
```v
//files come with attributes that let the system know how to interact with them
only allowing files to be open for writing, so you can't overwrite them

//set the file to be automatically compressed

//save the file if it is deleted, providing an oppurtunity to be recovered

// Make the file immutable
*making file immutable is a feature that says, nothing can modify the file but by root user.

//highly recommended for important files or files that wont likely need to be changed soon

//immutablable files have a lowercase i which indicates the immutable flag is set
```
# **lsattr COMMAND**
>lsattr [options] {file/ directory names}
```v
//is used to list the attributes of a file or directory
[options]
lsattr -R 
//recursively list the attributes 

lsattr -a
//list all files in directories

lsattr -d
//list directories like files, instead of listening their contents

lsattr -v
//List the version number of the file
```
# **chattr COMMAND**
>chattr [-R] [-v{version}] [+-{attributes}] {file/directory names}
```v
//used to change the attributes of a file or directory
```
# **ACCESS CONTROL LISTS**
```v
//a list of permissions attached to an object

//using ACLs , you would be able to grant different levels of access to different users, groups, and even processes.
```
# **getfacl COMMAND**
>getfacl {option} {file}
```v

//used to retrieve the Access control files and directories

//displays the file name, owner, the group, and the Access control List.
-a access
//display file access control list only

-d default
//display the default access control list

-c omit-header
//do not display content header

-e all-effective
//print all effective rights

-E no-effective
//print no effective rights

-s skip-base
//skil files that only have the base entries

-R recursive
//recurse into subdirectories

-L logical
//logical walk, follow symbolic links

-P physical
//physical walk, do not follow symbolic links

-t tabular
//use tabular output format

-n numeric
//print numeric user/group identifiers

-p absolute-names
//don't strip leading '/' in pathnames

-v version
//print version and exit

-h help
//this help text
```
# **setfacl COMMAND**
>setfacl [-bR] [-mx{acl_spec}] {file/directory names}
```v
//usd to change permissions associated with the ACL of a file or directory.

setfacl -R
//recursively set ACL options for D and their contents

setfacl -s
//set the ACL of an object

setfacl -m
//modify the existing ACL of an object

setfacl -x
//remove entries from an existing ACL

setfac1 -b
//remove all extended ACL entries(not including standard permissions)
```

# **TROUBLESHOOT PERMISSION ISSUES**
```v
//Troubleshooting is the recognition, diagnosis, and resolution of problems
```

## **TROUBLESHOOTING MODELS**
```v

//troubleshooting strategy is a plan of action for identifying the causes and resolving the effects of a system-related issue.

1)IDENTIFY THE PROBLEM
-Gathering information
-Duplicating the problem, if possible
-Questioning users to gain experiential information
-Identifying the symptoms

2)ESTABLISH A THEORY OF PROBABLE CAUSE.
-Questioning the obvious
-Considering multiple approaches
-Looking for not just a cause, but the root cause

3)TEST THE THEORY TO DETERMINE THE CAUSE
-when the theory is confirmed, determine the next steps to resolve the problem
-If the theory is not confirmed, establish a new theory or escalate the issue

4)establish a plan of action to resolve the problem, while identifying the potential effects of your plan

5)implement the solution, or escalate the issue.

6)Verify full system fucntionality and, if applicable, implement preventative measures

7)Document your findings, actions and the outcomes
```
## **GROUP MEMBERSHIP TROUBLESHOOTING**
>groups {username}
```v
//lets you see and verify what groups a particular user is member of
```
>lid {file}
libuser-lid {file}
```v
//can retrieve all members of a group, including members whose primary group is the group being searched for.
```

# **MANAGING STORAGE**
```
First task of managing storage is to partition a storage device and format the partition with a file system.
```

# **Create Partitions**
___
## **Storage devices**

```v

Hard disk drive(HDD)

//electromechanical devices that use magnetic storage technology to store data.

Solid-state-drive(SSD)

//non-mechanical solid-state technology to store data

USB thumb drive

//portable storage device that uses flash memory technology to store data in small amounts.

External storage drive

//portable storage drives that uses one of several technology types. Usually through a peripheral.
```
# BLOCK VS CHARACTER DEVICES
___
>Linux refers to devices as either block or character devices.
```v
BLOCK DEVICES

//storage devices(HDD,SSD,USB thumb drive,External storage drive)that can be read from and written to in blocks of data.

CHARACTER DEVICES

//devices like keyboards, mice,serial ports,etc that can be read from and written to in streams of data.
```
# FILE SYSTEMS

>A **file system** is a data structure that is used by an operating system to store, retrieve, organize, and manage files and directories on storage devices.

# TYPES OF FILE SYSTEMS
```v
(FAT) File allocation Table

// an older file system that is compatible with many different operating systems, including all versions of unix, windows, and macOS.

(ext2) 

//used to be the native Linux file system of some older releases

(ext3)

//improved version of ext2. if system is abrupted by a shutdown, ext3 is much faster in recovering data and ensures data integrity

(ext4)

//one of two default file system for Linux distros. it is backwards compatible with the ext2 and ext3 file systems.

(xfs)

//64-bit, high-performance journaling file system that provides fast recovery and can handle large files accurately.
```
>## **NFTS**
>**New Technology File Systems**
```v
//a proprietary file system created by Microsoft as the primary file system for Windows.
   - file and folder level security
   - file encryption
   - drive compression
   -scalability to very large drives and files.
```
# **NETWORK FILE SYSTEM**
___
>Server Message Block(SMB)
```v
//SMB protocol provides users shared access files and other resources across a local area network(LAN)
```
>Common Internet File System(CIFS)
```v
//CIFS is a specific implementation of SMB that is rarely in use.
```
>Network FIle System(NFS)
```v
//NFS offers similar functionality to SMB, but protocols are not compatible
```
# INODES
___
>**Index node (idnode)**
```v
//is an object that stores metadata about a file or directory on a file system.

//Each inode on a file system is identified by a unique integer called an inode number
```
>ls -i
```v
//list the inode numbers
```

# **JOURNALING**
```V
//is a method by which a file system records changes that have not yet been made to the file system itself in an unexpected interruption.
```
>**Phases of JOURNALING**
```v
//describe all the changes that must be made to the drive

//a process makes each change as and when it is entered in the journal

//If the system shuts down, pending changes are performed when it is rebooted.

//incomplete entries in the journal are discarded
```
# **VIRTUAL FILE SYSTEM**
```V
//Software interface that sits between teh kernel and real file systems. VFS translates a real file system's details to the kernal , so it is identical to any other file system.

//This Greatly increases interoperability between the system and running software because the user and these applications can work with the file system without knowing its underlying structure.
```
>Real file systems
```v
//xfs, ext4 are some examples
```
>Virtual file systems
```v
//proc, devtmpfs,debugfs
```
## **FILE SYSTEM LABELS**
>e2label /dev/{dev/{device name} {partition number} {label name}

>xfs_admin -L {Label name} /dev/ {device name} {partition number}
```v
//system labels may be up to 16 characters long and can be displayed or changed using:
e21label
//for ext#
xfs_admin for
//XFS file systems
```
# **PARTITIONS**
```V
//a section of the storage of drive that logically acts as a seperate drive.

//partitions allow you to convert a large drive to smaller manageable chunks leading to better organization of information. 

//a partition must be formatted and assigned a file system before data can be store on it

//The size of each partition can vary but cannot exceed the total free space

//Data of different types can be stored in spereate locations on the drive, such as seperating systems files from user-accessible files.
```
# **TYPES OF PARTITIONS**

>**PRIMARY**
```V
// a partition that can contain one file system or logical drive and is sometimes referred to as a volume.
```
>**EXTENDED**
```v
//extended partition can contain several file systems, which are referred to as logical drives
```
>**LOGICAL**
```v
//part of a physical drive that has been partitioned and allocated as ann independent unit and functions as a seperate drive.
```
#  **THE fdisk UTILITY**

>fdisk [options] {device name}
>fdisk /dev/sda
```v
//is a menu-driven program that is used to create, modify, or delete partitions on a storage drive.
-b {sector size}
//specify the number of drive sectors

-H {heads}
//specify the number of drive heads

-S {sectors}
//specifiy the number of sectors per track

-s {partition}
//Print the partition size in blocks

-l  
//List partition tables for devices
```
>**INSIDE FDISK MENU OPTIONS
```V
n
//Create a new partition.
d
//Remove a partition
p
//List the existing partitions
w
//write the changes to drive and exit the utility
q
//Cancel the changes made and exit the utility.
```

# **GNU PARTED**
>parted [options] {device name}
```v
//is a utility that can manage partitions, particularly used to create , destroy, and resize partitions.
```
>**GNU PARTED MENU OPTIONS**
```v
//interactive options menu

select
//Choose which device or partition to modify

mkpart
//create a partition with a specified file system type

print
//list the partition table

resizepart
//Modify the end position of a partition

rm
//modify the end position of a partition

quit
//Exit the GNU Parted utility
```
# **THE partprobe COMMAND**
>partprobe [options] {device name}
```v
//used to update the kernel with changes in the partition table. its good for after created the fdsisk.
It is good for when you cannot read the partition table during fdisk and you don't want to reboot machine. you'd issue THIS COMMAND to update the table.
```
# **THE mkfs COMMAND**
>mkfs [options] {device name}
>mkfs.ext4 /dev/sda6
```v
//is used to build a Linux file system on a device

-v
//verbose output, where the output message will keep changing constantly as the program is processing

-V
//verbose output, including all file system-specific commands that are executed.

-t {fs type}
//specify the type of file system to be built

fs-options
//Pass file system-specific options to the file system builder

-c
//Check device for bad blocks 

-l
//read the list of bad blocks for a specified file
```

# **fstab file**
```v
//a configuration file that stores information about storage devices and partitions and where and how the partitions should be mounted.

//it consist of a number of lines , one for each file system

Device or Partition name
//specifies the name of the device or file system to mount

Default mount point
//indicates where the file system is to be mounted

File system type
//specifies the type of file system used by the device or partition

Mount options
//specifies a set of comma-sperated options that will be activated when the file system is mounted

dump options
//indicates if the dump utility should back up the file system

fsck options
//specifies the order in which the fsck utility should check file systems
```
>**THE crypttab FILE**

> /etc/cryptab
```v
//purpose of file is to store information about encrypted devices and partitions that must be unlocked and mounted on system boot. 
```

# **THE STORAGE DEVICE SETUP PROCESS**
(EVERYTHING ALL TOGETEHER)
```V
1.
// Partition the storage device using a tool like fdisk or parted.
2.
// Format the partition with a file system using the mkfs tool.
3.
//add the formatted partition to the fstab file so that itis configured by the system on boot
```

# **The /dev/DIRECTORY**
```v
//contains files that represent and support devies attached to the system.
```
>**Naming convention**
```v
//for storage devices naming convention is typcially expressed in three parts.

   * sd
   //refers to a specific type of controller that device is using.

   * a
   //referes to the first whol drive. the second whole drive would be b.

   * 1
   //referes to the first partition ont his drive. second partition would be 2
```
# **THE /dev/disk/by- IDENTIFIERS**

>/dev/disk/by-id
```v
//refers to an identifier based on the device's hardware serial number/
```
>/dev/disk/by-path
```v
//refers to an identifier based on the shortest physical path to the device
```
>/dev/disk/by-uuid
//refers to an identifier based on the universally unique identifier(UUID)that was assigned to the device.



