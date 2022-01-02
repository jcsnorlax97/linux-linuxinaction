# Chapter 2. Linux virtualization: Building a Linux working environment

## 0. Table of Contents
- [Chapter 2. Linux virtualization: Building a Linux working environment](#chapter-2-linux-virtualization-building-a-linux-working-environment)
  - [0. Table of Contents](#0-table-of-contents)
  - [1. What is Virtualization?](#1-what-is-virtualization)
  - [2. Working with VirtualBox](#2-working-with-virtualbox)
    - [2.1. Working with Linux package managers](#21-working-with-linux-package-managers)
    - [2.2. Defining a Virtual Machine (VM)](#22-defining-a-virtual-machine-vm)
    - [2.3. Installing an Operating System (OS)](#23-installing-an-operating-system-os)
    - [2.4. Cloning and Sharing a VirtualBox VM](#24-cloning-and-sharing-a-virtualbox-vm)

## 1. What is Virtualization?

- Briefly describe the two approaches to virtualization mentioned in this chapter.
  - Hypervisors:
    - Hypervisors like VirtualBox provide an environment where virtual operating systems can safely **access hardward resources**.
  - Containers:
    - Lightweight containers **share their host's software kernel**.

- Briefly compare among the following three virualization technologies: Full-sized hypervisors, Type 2 hypervisors, and Container.
  - Full-sized hypervisors: 
    - Full-sized hypervisors are normally used for **enterprise-sized deployments** involving large fleets of Linux VMs.
    - Examples include Xen and KVM.
  - Type 2 hypervisors:
    - Type 2 hypervisors are perfect for **testing and experimenting with live operating systems**, one or two at a time, without the need to install them to actual PCs.
    - Their **relatively high overhead** makes them unsuitable for most production environments.
    - Examples include VirtualBox and VMware's Player. 
  - Containers:
    - Container technologies are **lightweight** and can be **provisioned and launched in mere seconds**.
    - LXC containers are particularly well suited to playing with new technologies and safely building OS software stacks.
    - Docker is currently the technology running countless dynamic, integrated fleets of containers as part of vast **microservices architectures**.

- Describe the following terminologies.
  - **Virtualization**:
    - Virtualization is the logical sharing of compute, storage, and networking resources among multiple processes, allowing each to run as if it was a standalone physical computer.
  - **Hypervisor**:
    - A hypervisor is software running on a **host machine** that **exposes system resources** to a guest layer, allowing the launching and administration of full-stack guest VMs.
  - **Container**
    - A container is a VM that, instead of full-stack, **lives on top of (and shares) the host machine's core OS kernel**.
    - Containers are extremely easy to launch and kill, according to short-term need.

## 2. Working with VirtualBox

### 2.1. Working with Linux package managers

- Briefly describe how to install VirtualBox on an Ubuntu machine.
    ```bash
    sudo apt update
    sudo apt install virtualbox
    ```

- Briefly describe how to install VirtualBox on a Fedora machine.
    ```bash
    wget http://download.virtualbox.org/virtualbox/rpm/fedora/virtualbox.repo # Add Repo
    dnf update                          # Update Index
    dnf install patch kernel-devel dkms # Install dependencies
    dnf install VirtualBox-5.1          # Install package
    ```

- Briefly describe what Package Managers do. 
  - Package Managers, which come installed with Linux by default, has a number of jobs:
    - to maintain a **local index** to **track** repositories and their contents.
    - to track the **status** of all the software that's installed on your local machine.
    - to ensure that all **available updates** are applied to installed software.
    - to ensure that **software dependencies** (other software packages or configuration parameters required by the package you're installing) are met for new applications before they're installed.
    - to handle installing and removing software packages.

- List the three package mangers mentioned in this chaper (Table 2.1) and their associated distributions. 
  - **APT**: Debian, Ubuntu, Mint Kali Linux
  - **RPM**: Red Hat Enterprise Linux, CentOS, Fedora
  - **YaST**: SUSE Linux, OpenSUSE

- Briefly describe how to search for all available packages, and to display full package information for a package.
    ```bash
    apt search sensors      # Search for all available packages with the word "sensors" in it
    apt show lm-sensors     # Display full package information of the "lm-sensors" package.
    ```

- Describe the following terminologies.
  - **Software Repository**:
    - A software repository is a location where **digital resources can be stored**. Repositories are particularly useful for **collaboration** and **distribution of software packages**.

### 2.2. Defining a Virtual Machine (VM)

- Brief compare the differences between a dynamically allocated virtual drive and a fixed-size disk.
  - Dynamically allocated virtual drive:
    - A dynamically allocated virtual drive in VirtualBox takes up only as much space on your physical drives as the VM **actually uses**.
  - Fixed-size disk:
    - A fixed-size disk takes up the **maximum space** no matter how much data is there.
    - The advantage of Fixed Size is **application performance**.

### 2.3. Installing an Operating System (OS)

- Briefly describe what else needs to be done after defining our new VM's virtual hardware profile.
  1. To download a file (in **ISO format**) containing the **image of the Linux distribution** you want to use.
  2. To **boot** the new VM using a **virtual DVD drive** containing the ISO you downloaded.
  3. To work through the **standard OS installation process**.
  4. To **boot** the VM and **launch the OS** you installed previously, which may require removing DVD from drive, like you would for a "real" physical installation.

- Briefly describe how to validate the downloaded Ubuntu ISO by doing a checksum comparison.
  - Expected ISO's Checksum:
    - Based on [Ubuntu Releases - Ubuntu 20.04.3 LTS (Focal Fossa) - SHA256SUMS](https://cdimage.ubuntu.com/releases/20.04/release/SHA256SUMS), the ISO `ubuntu-20.04.3-live-server-arm64.iso` is having a checksum value of **`d6fea1f11b4d23b481a48198f51d9b08258a36f6024cb5cec447fe78379959ce`**.
  - Downloaded ISO's Checksum:
    ```bash
    shasum -a 256 ubuntu-20.04.3-live-server-arm64.iso # Result should be `d6fea1f11b4d23b481a48198f51d9b08258a36f6024cb5cec447fe78379959ce` as well.
    ```

### 2.4. Cloning and Sharing a VirtualBox VM

- List the two related tricks mentioned in this chapter.
  1. To clone VMs for quick starts.
  2. To use the command line to share VMs across a network. 