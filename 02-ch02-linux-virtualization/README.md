# Chapter 2. Linux virtualization: Building a Linux working environment

## 0. Table of Contents
- [Chapter 2. Linux virtualization: Building a Linux working environment](#chapter-2-linux-virtualization-building-a-linux-working-environment)
  - [0. Table of Contents](#0-table-of-contents)
  - [1. What is virtualization?](#1-what-is-virtualization)
  - [2. Working with VirtualBox](#2-working-with-virtualbox)
    - [2.1. Working with Linux package managers](#21-working-with-linux-package-managers)

## 1. What is virtualization?

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