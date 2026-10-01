# Guest OS Images – TekMonks

Pre-built QCOW2 disk images for creating virtual machines in Kloudust.

## Overview

The [guest-images](https://github.com/TekMonksTeam/guest-images) repository provides ready-to-use QCOW2 images of Red Hat Enterprise Linux (RHEL) and SUSE Linux Enterprise Server (SLES).

The primary objective of this repository is to make these images easily accessible so that users can download them, upload them to Kloudust, and create and run virtual machines without having to install the operating system from scratch.

## Available OS Images

| Operating System | Version | Image Format | OS Variant |
|---|---|---|---|
| Red Hat Enterprise Linux | RHEL 9.6 | QCOW2 | `rhel9.6` |
| SUSE Linux Enterprise Server | SLES 15 SP5 | QCOW2 | `opensuse15.5` |
| SUSE Linux Enterprise Server | SLES 15 SP6 | QCOW2 | `opensuse15.6` |

### What are these images?

**QCOW2 (QEMU Copy-On-Write version 2)** is a virtual disk image format used by QEMU/KVM virtualization. It stores the virtual machine's disk and operating system data.

These images can be used as the base disks for creating virtual machines. Instead of installing an OS from an ISO file, users can upload an existing QCOW2 image and use it to provision a VM.

### OS Variant Names

The OS variant identifies the guest operating system and version to the virtualization platform. When creating a VM in Kloudust, select the exact variant corresponding to the image:

- RHEL 9.6 → `rhel9.6`
- SLES 15 SP5 → `opensuse15.5`
- SLES 15 SP6 → `opensuse15.6`

**Important:** The OS variant is a configuration value used during VM creation. It does not convert one operating system version into another.

## Downloading the QCOW2 Images

The disk images are stored using **Git Large File Storage (Git LFS)**. Git LFS keeps large binary files outside the regular Git repository data and downloads their contents when requested.

You must have Git and Git LFS installed to download the actual QCOW2 files.

### Step 1: Install Git

On Ubuntu or Debian-based Linux systems:

```bash
sudo apt update
sudo apt install git
```

Verify the installation:

```bash
git --version
```

### Step 2: Install Git LFS

On Ubuntu or Debian-based Linux systems:

```bash
sudo apt install git-lfs
```

Initialize Git LFS:

```bash
git lfs install
```

Verify that Git LFS is available:

```bash
git lfs version
```

For other operating systems, follow the [official Git LFS installation guide](https://docs.github.com/en/repositories/working-with-files/managing-large-files/installing-git-large-file-storage).

### Step 3: Clone the Repository

Run the following command to clone the repository:

```bash
git clone https://github.com/TekMonksTeam/guest-images.git
```

Enter the repository directory:

```bash
cd guest-images
```

If Git LFS was installed and initialized before cloning, Git should download the LFS-managed files during checkout.

### Step 4: Download the Actual QCOW2 Files

If the images have not been downloaded, run:

```bash
git lfs pull
```

This downloads the Git LFS objects for the currently checked-out revision.

To check which files are managed by Git LFS:

```bash
git lfs ls-files
```

To list the downloaded files:

```bash
ls -lh
```

The QCOW2 images should now be available in your local repository directory.

### Alternative: Clone First, Download LFS Files Later

If you cloned the repository before installing Git LFS, or the clone contains only LFS pointer files, run:

```bash
git lfs install
git lfs pull
```

**Note:** QCOW2 images can be large. Ensure that you have sufficient disk space and a stable internet connection before downloading them.

## Creating a VM in Kloudust

Once you have downloaded the required QCOW2 image, follow these steps to create and run a virtual machine.

### Steps
-  Log in to Kloudust as Admin

-  Add the QCOW2 Image (for OS Varients, refer to the above OS Varients list)

- Create the Virtual Machine

- Start and Access the VM 


## Important Notes

- **🔑 Red Hat and SUSE Accounts:** To get started with your RHEL or SLES virtual machine, you may need an account with the respective vendor. If you don't have one, create a free account on the official website:
  - **Red Hat:** https://www.redhat.com/
  - **SUSE:** https://www.suse.com/

- **👤 Creating Your VM User:** Once your VM is running, follow the guest OS setup process to create your own username and password. Your Red Hat or SUSE account is used for vendor services and subscriptions; it does not automatically become your VM's login account.

## Repository

GitHub: [https://github.com/TekMonksTeam/guest-images](https://github.com/TekMonksTeam/guest-images)

