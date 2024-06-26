# Linux System Administration Guide
![Linux_logo](https://media.licdn.com/dms/image/D4D12AQGxLt3lZb-3FA/article-cover_image-shrink_600_2000/0/1693882752310?e=2147483647&v=beta&t=oIqV0XAIi0Wqb8-HAFjyPP8310CE2rBd5paDKSryqcY)

## Table of Contents

1. [Introduction](#introduction)
2. [Installation](#installation)
    - [Choosing a Linux Distribution](#choosing-a-linux-distribution)
    - [Installation Process](#installation-process)
3. [Basic Command Line Usage](#basic-command-line-usage)
    - [Navigating the Filesystem](#navigating-the-filesystem)
    - [Managing Files](#managing-files)
4. [Managing Local Users and Groups](#managing-local-users-and-groups)
    - [Adding Users](#adding-users)
    - [Modifying Users](#modifying-users)
    - [Deleting Users](#deleting-users)
    - [Managing Groups](#managing-groups)
5. [Controlling Access to Files](#controlling-access-to-files)
    - [File Permissions](#file-permissions)
    - [Changing File Permissions](#changing-file-permissions)
    - [Changing Ownership](#changing-ownership)
6. [Examples](#examples)
    - [File Management Commands](#file-management-commands)
    - [User and Group Management Commands](#user-and-group-management-commands)
    - [Access Control Commands](#access-control-commands)

## Introduction

Linux is a powerful and versatile operating system used widely for both personal and enterprise purposes. This guide covers essential aspects of Linux system administration, focusing on managing files, users, and access permissions through the command line interface.

## Installation

### Choosing a Linux Distribution
![LinuxOS_logo](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRQOanYwFsE96GOEGBggdGBVx_GQUZQ1i5uow&s)

Different Linux distributions (distros) serve different purposes. Popular choices include:

- Ubuntu: User-friendly and great for beginners.
- CentOS: Ideal for servers and enterprise environments.
- Fedora: Cutting-edge features and ideal for developers.

### Installation Process

1. **Download ISO**: Obtain the installation ISO from the distro's official website.
2. **Create Bootable Media**: Use tools like Rufus (Windows) or dd (Linux) to create a bootable USB drive.
3. **Boot and Install**: Boot from the USB drive and follow the on-screen instructions to install the Linux distribution.

## Basic Command Line Usage

### Navigating the Filesystem
![Screenshot from 2024-06-26 12-58-42](https://github.com/siddharthsinghchaudhari/Linux/assets/120357061/4ee45f34-5c69-4acf-b1cb-b34ef79e28cd)

- `pwd`: Print working directory.
- `cd [directory]`: Change directory.
- `ls`: List directory contents.

### Managing Files

- `cp [source] [destination]`: Copy files or directories.
- `mv [source] [destination]`: Move or rename files or directories.
- `rm [file]`: Remove files.
- `mkdir [directory]`: Create a new directory.
- `rmdir [directory]`: Remove an empty directory.
- ![Screenshot from 2024-06-26 13-12-27](https://github.com/siddharthsinghchaudhari/Linux/assets/120357061/7554a881-d8a8-4a47-ae71-8645444ae60d)


## Managing Local Users and Groups
![Screenshot from 2024-06-26 13-19-49](https://github.com/siddharthsinghchaudhari/Linux/assets/120357061/510ac52e-606b-48cd-95b9-3d212fe32a93)


### Adding Users

- `useradd [username]`: Create a new user.
- `passwd [username]`: Set a password for a user.

### Modifying Users

- `usermod -aG [group] [username]`: Add a user to a group.
- `usermod -l [new_username] [old_username]`: Change a user's login name.

### Deleting Users

- `userdel [username]`: Delete a user.
- `userdel -r [username]`: Delete a user and their home directory.

![Screenshot from 2024-06-26 13-20-52](https://github.com/siddharthsinghchaudhari/Linux/assets/120357061/5c89614d-5431-44f0-9b0d-60fdc3378a75)

### Managing Groups

- `groupadd [groupname]`: Create a new group.
- `groupdel [groupname]`: Delete a group.
- `gpasswd -a [username] [groupname]`: Add a user to a group.
- `gpasswd -d [username] [groupname]`: Remove a user from a group.

## Controlling Access to Files

### File Permissions

Files have three types of permissions: read (r), write (w), and execute (x). These permissions are set for three categories of users: owner, group, and others.

### Changing File Permissions

- `chmod [permissions] [file]`: Change file permissions.
  - Example: `chmod 755 [file]`

### Changing Ownership

- `chown [owner] [file]`: Change file owner.
- `chown [owner]:[group] [file]`: Change file owner and group.

## Examples

### File Management Commands

```sh
# Copy file1 to file2
cp file1 file2

# Move file1 to dir1
mv file1 dir1

# Remove file1
rm file1

# Create a directory named dir1
mkdir dir1

# Remove an empty directory named dir1
rmdir dir1

```
### User and Group Management Commands

```sh
# Add a new user named john
useradd john

# Set password for user john
passwd john

# Add user john to the group sudo
usermod -aG sudo john

# Delete user john and their home directory
userdel -r john

# Create a new group named developers
groupadd developers

# Add user john to the developers group
gpasswd -a john developers

# Remove user john from the developers group
gpasswd -d john developers
```
### Access Control Commands

```sh
# Change permissions of file1 to rwxr-xr-x
chmod 755 file1

# Change owner of file1 to user john
chown john file1

# Change owner and group of file1 to john and developers
chown john:developers file1
```
