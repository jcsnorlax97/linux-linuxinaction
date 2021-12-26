# Chapter 1. Welcome to Linux

## 0. Table of Contents
- [Chapter 1. Welcome to Linux](#chapter-1-welcome-to-linux)
  - [0. Table of Contents](#0-table-of-contents)
  - [1. Hello Linux!](#1-hello-linux)
  - [2. Linux Basics](#2-linux-basics)
    - [2.1. UNIX Filesystem Hierarchy Standard](#21-unix-filesystem-hierarchy-standard)
    - [2.2. Navigation Commands](#22-navigation-commands)

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