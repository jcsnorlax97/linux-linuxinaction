# Chapter 1. Welcome to Linux

## 0. Table of Contents
- [Chapter 1. Welcome to Linux](#chapter-1-welcome-to-linux)
  - [0. Table of Contents](#0-table-of-contents)
  - [1. Hello Linux!](#1-hello-linux)
  - [2. Linux Basics](#2-linux-basics)
    - [2.1. UNIX Filesystem Hierarchy Standard](#21-unix-filesystem-hierarchy-standard)
    - [2.2. Navigation Commands](#22-navigation-commands)
    - [2.3. File Management Commands](#23-file-management-commands)
    - [2.4. Keyboard Tricks](#24-keyboard-tricks)
    - [2.5. Pseudo File Systems](#25-pseudo-file-systems)
    - [2.6. `sudo` command](#26-sudo-command)
  - [3. Getting Help](#3-getting-help)
    - [3.1. `man` command](#31-man-command)
    - [3.2. `info` command](#32-info-command)

## 1. Hello Linux!

- Describe Linux.
  - Linux is **free**.
  - Linux is **open source**, which means anyone can take the code base and reshape it into anything they want.
  - Linux makes it possible to do various really useful and creative things.
    - **Example**: You can **load a Linux live boot image on a USB stick**, **boot a PC whose own hard disk has been corrupted**, and then troubleshoot and fix the problem.
  - Linux was built with some of the same technology and comes with most of the same tools as the deeply mature **UNIX OS**. This adds a great deal of stability and security.
  - Linux distributions also provide **sophisticated software package management systems** that reliably install and maintain any of the thousands of free software applications available through online curated repositories.

- Describe the following terminologies.
  - **Linux Distribution**: 
    - A distribution (sometimes shortened to distro) is a customized stack of software that's packaged along with the Linux kernel and distributed with tools for installing a working version of Linux of user computers.
    - For example, Ubuntu is an all-purpose Linux distribution; Kali Linux and Parrot are Linux distributions for security or anti-hacking purposes.

## 2. Linux Basics

### 2.1. UNIX Filesystem Hierarchy Standard

- Describe why we would need an index.
  - A digital storage device like a hard drive or USB drive isn't divided into physical divisions that can be used as organizing folders (or directories, as they're known in Linux circles).
  - So, if we want our data to be reliably retrievable, we'll need some kind of index that can consistently point us to the resources we're after.

- Which is the most commonly used Linux file system?
  - The most commonly used Linux file system these days is **ext4**.
  - But Linux can also work with storage drives that were formatted using file systems from other platforms like **FAT32** and **NTFS**.

- Describe where all the files in a disk partition are kept.
  - All the files in a disk partition are kept in directories beneath the root directory, which is represented by the `/` (forward slash) character.

- How does Linux arrange its directory structure?
  - The directory structure and directory contents in Linux distributions are defined by the **Filesystem Hierarchy Standard (FHS)**.
  - In FHS, all files and directories appear under the root directory (`/`), even if they are stored on different physical or virtual devices.
  - Common top-level directories as defined by the UNIX FHS include:
    - `/etc` for program configuration files
    - `/var` for frequently changing content (such as log files)
    - `/home` for individual users to store their private files
    - `/sbin` for system binary files
    - `/bin` for user binary files
    - `/lib` for shared libraries
    - `/usr` for third-party binaries

- Describe the following terminologies.
  - **File System**: 
    - A file system is made up of data files indexed in a way that allows the perception of a **directory-based organization**.
    - A file system can be thought as a data table (or an index) that creates apparent connections between individual files and groups of files with identifiable locations on a disk.
  - **Disk Partition**:
    - A disk partition is the **logical division of a physical storage device** that can be made to work exactly like a standalone device. Partitions are common organizational tools for all modern operating systems.
  - **Top-Level Directories**:
    - Top-level Directories are those directories located directly beneath the root, such as `/etc/`, `/var/`, `/home/` and more.

### 2.2. Navigation Commands

- List the five Linux navigaton commands and briefly describe what they do.
  - `ls`: To list the names of the files and subdirectories in your current directory.
  - `pwd`: To print your **p**resent **w**orking **d**irectory.
  - `cd`: To tell the command-line interpreter to move you to the directory you specify.
  - `cat`: To print a file to the screen where it can be read, but not edited.
  - `less`: To display a small part of the complete file contents.

- Describe what `ls`, `ls /var`, `ls -l /var`, `ls -lh /var`, `ls --human-readable /var`, and `ls -R /var` do.
  - `ls`: To list the names of the files and subdirectories in your current directory.
  - `ls /var`: To list the names of the files and subdirectories in the `/var` directory.
  - `ls -l /var`: To list the names and **additional details** of the files and subdirectories in the `/var` directory, where the additonal details include file permissions, owner, group, file size, and time stamp.
  - `ls -lh /var`: To list the names and additional details of the files and subdirectories in the `/var` directory, where the additonal details include file permissions, owner, group, file size, and time stamp. Also, **the file sizes are displayed in a human-readable format** -- kilobytes, megabytes, and gigabytes, rather than bytes.
  - `ls -l --human-readable /var`: `--human-readable` is the verbose version of the same argument of `-h`. In other words, this is the same command as `ls -lh /var`.
  - `ls -R /var`: To display all subdirectories and the files and subdirectories they contain, no matter how many nested layers of directories. 

- Describe what `cd`, `cd /`, `cd ..`, and `cd /home/myusername` do.
  - `cd`: To move back to the home directory of the current logged-in user.
  - `cd /`: To move back to the root directory.
  - `cd ..`: To move one level up in the directory hierarchy.
  - `cd /home/myusername`: To move to `myusername` directory from the `home` directory.

- Describe how to scroll up and down through the file and how to exit while using `less`.
  - Scrolling Up/Down: the arrows, `PgUp`, `PgDn`, and `spacebar` keys.
  - Exit: `q` key.

- Describe the following terminologies.
  - **Shell**
    - A shell is **any user interface that interprets a user's commands**, either through a command-line interface (CLI) or a graphical user interface (GUI).
    - It can be thought as **a software layer** meant to execute all appropriately formatted commands using the underlying kernel and hardware system resources.
    - In other words, it's **the way you talk to your computer**.
    - **Bash** is probably the most popular **UNIX shell**.
  - **Relative Path**
    - A relative path is a path that is relative to your current directory location.
  - **Absolute Path**
    - An absolute path is a path that begins with the root directory (represented by a forward slash). For example, `/home` is an absolute path.

### 2.3. File Management Commands

- List the commands to create, destroy, move and copy a file.
  - `touch <args>`: to create a new file.
  - `rm <args>`: to remove a file.
  - `mv <args>`: to move a file from one directory to another directory.
  - `cp <args>`: to make a copy of a file.

- Describe the difference in between `cp file1 dir1` and `cp file1 dir2`, where `dir1` does not exist and `dir2` exists.
  - For `cp file1 dir1`, since the destination directory (`dir1`) does not exist, the destination directory argument would be used as the **filename** of the copy of `file1`. As a result, if `file1` is located in `./` directory, a new copy of `file1` would be created in the same directory, i.e. `./`. And this copy is named as `dir1`.
  - For `cp file1 dir2`, since the destination directory (`dir2`) exists, a copy of `file1` would be created inside `dir2`. This new copy will be having the same filename (`file1`).

- List the commands to create, destroy, move and copy a directory.
  - `mkdir <args>`: to create a directory.
  - `rmdir <args>`: to remove an empty directory.
  - `rm -r <args>`: to remove a directory, regardless it's empty or not.
  - `mv <args>`: to move a directory from one directory to another directory, regardless it's empty or not.
  - `cp -r <args>`: to make a copy of a directory, regardless it's empty or not.

- Briefly describe the two common wildcard characters (`*` and `?`) used for Linux file globbing. 
  - Asterisk (`*`) wildcard: this is interpreted as **zero or more characters**, i.e. a number of literal characters or an empty string.
  - Question mark (`?`) wildcard: this is interpreted as **exactly one character**.

- Briefly describe what `mv * /directories/dir1`, `mv file* /directories/dir1`, and `mv file? /directories/dir1` do.
  - `mv * /directories/dir1`: to move all contents of the current directory to `/directories/dir1`.
  - `mv file* /directories/dir1`: to move all contents of the current directory, starting with `file`, to `/directories/dir1`.
  - `mv file? /directories/dir1`: to move all contents of the current directory, starting with `file` followed by exactly one additonal character, to `/directories/dir1`. 

- Which command can we use to display inode information of a Linux file system object? For example, how do we display inode information of `file1` (a file) or `dir1` (a directory)?
  - `stat`
  - `stat file1`
  - `stat dir1`

- List the three categories of text editors.
  - Plain-text editor, e.g. gedit (or "the Text Editor" in Ubuntu), which allows us to work on documents from the GUI environment.
  - Command-line editor, e.g. nano or Pico, which allows us to edit a file from inside a terminal session.
  - **Vim**

- Describe the following terminologies.
  - **Inode**: 
    - An inode is an object used by UNIX systems to identify the **disk location** and **attributes of files** within a file system.
    - Usually there'll be exactly one inode for each file or directory.
    - When we are moving, copying, or deleting a file or directory, what we're actually doing is editing its inode attributes.
  - **File Globbing**:
    - File globbing involves using **wildcard characters** to refer to multiple files with a single command.

### 2.4. Keyboard Tricks

- Briefly describe how to do copying & pasting in a Bash shell session in a Linux Terminal.
  - Copy: Copying can be done by the `Shift + Ctrl + C` command. Note that `Ctrl + C` WON'T work!
  - Paste: Pasting can be done by the `Shift + Ctrl + V` command. Note that `Ctrl + V` WON'T work!

- Describe the following terminologies.
  - **Tab completion**:
    - Tab completion employs the `Tab` key to suggest possible completions of a partially typed command.

### 2.5. Pseudo File Systems

- Briefly describe where block devices can be found in Linux.
  - In Linux, all attached storages are organized as **block devices**.
  - All the currently available block devices can be found in the `/sys/block/` directory.

- Briefly describe what `/dev/sda`, `/dev/sdb`, `/dev/sdc`, `/dev/hda`, `/dev/sr0`, `/dev/cdrom`, and `/dev/fd0` refer to.
  - `/dev/sda`: contents within the **first storage device (SCSI Device A)** on a system. 
  - `/dev/sdb`: contents within the **second storage device (SCSI Device B)** on a system.
  - `/dev/sdc`: contents within the **third storage device (SCSI Device C)** on a system.
  - `/dev/hda`: contents within a **hard drive** on a system.
  - `/dev/sr0`: contents within a **DVD drive** on a system.
  - `/dev/cdrom`: contents within a **CD-ROM drive** on a system.
  - `/dev/fd0`: contents within a **floppy drive** on a system.
  - `/dev/loop0`: contents within a **loop device** on a system.

- Describe the following terminologies.
  - **Pseudo File Systems**:
    - Pseudo file systems are **directories** containing files with dynamic data automatically generated at or after system boot.
  - **Loop Device**:
    - A loop device is a pseudo device that allows a file to be used as though it's an actual physical device.

### 2.6. `sudo` command

- Briefly describe what `sudo` command does.
  - `sudo` command can be invoked by authorized users to gain administration permissions for individual commands.
  - For example, `cat /etc/shadow` cannot be displayed without sudo powers. To display that, we need to type `sudo cat /etc/shadow` instead.
  - By default, the user created during the initial Linux installation will haave `sudo` powers.

- Throughout this book, what would the author use for (i) commands that don't require administrator and (ii) commands that do?
  - `$` for commands that DON'T require administrator, for example `$ ls`.
  - `#` for commands that DO require administrator, for example `# nano /etc/group`.

## 3. Getting Help

### 3.1. `man` command

- Briefly describe what `man` command does.
  - `man` command allows us to view the man file of a command.

- Briefly describe how to launch search operations within man files.
  - `/` key: to get a text entry field at the bottom of the screen where we can type our search pattern.
  - `n` key: to search forward in the document for the same string until you find what you're looking for.

- Describe the following terminologies.
  - **Man file**:
    - A man file is a highly structured documentation manual.
    - When a Linux program is installed, its man file is nearly always installed with it and can be viewed from the command line by typing `man` followed by the command name, e.g. `man ls`. 

### 3.2. `info` command

- Briefly describe how to interact with the Info main menu.
  - `Up` & `Down` arrow keys: to scroll between lines.
  - `Enter` key: to move to the topic's page.
  - `u` key: to take us back up one level.
  - `q` key: to exit the Info main menu.

- Briefly how to install `info` command on Linux server distributions.
  - `sudo apt install info`
