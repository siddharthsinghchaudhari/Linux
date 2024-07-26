# Linux Documentation
![Linux_logo](https://media.licdn.com/dms/image/D4D12AQGxLt3lZb-3FA/article-cover_image-shrink_600_2000/0/1693882752310?e=2147483647&v=beta&t=oIqV0XAIi0Wqb8-HAFjyPP8310CE2rBd5paDKSryqcY)

## Table of Contents

1. [Introduction](#introduction)
2. [Installation Process](#installation-process)
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
7. [Conclusion](#conclusion)  
8. [Reference Links](#references)

## Introduction

Linux is a powerful and versatile operating system used widely for both personal and enterprise purposes. This guide covers essential aspects of Linux system administration, focusing on managing files, users, and access permissions through the command line interface.

## Installation Process

(For Virtual Machines)
1. **Download ISO**: Obtain the installation ISO from the Ubuntu's official website. https://ubuntu.com/download/desktop
2. **Download VMware Workstation 17 player**: from official website of VMware.  https://www.vmware.com/info/workstation-player/evaluation
3. **Open the VMware workstation 17 player** and select **Create new Virtual Machine**
4. **Select the ISO file you downloade in first step**
5. **Follow through the instructions and set according to your need or go with default options**: I have given my screenshots for any reference.

**Screenshots of Installation**:
![Screenshot (380)](https://github.com/user-attachments/assets/2bf05c42-ee80-4641-9277-453f18c5d020)
![Screenshot (381)](https://github.com/user-attachments/assets/e2558c48-25f9-4b5c-b8a1-137fa2c65c5e)
![Screenshot (382)](https://github.com/user-attachments/assets/2f0b63ba-0f1d-4bda-9eb9-225c3cdd19d3)
![Screenshot (383)](https://github.com/user-attachments/assets/8a6ac079-46ec-4329-988e-c82ca5ee49e9)
![Screenshot (384)](https://github.com/user-attachments/assets/f4e4c925-92a5-4efc-9bab-d3f7d395ef4b)


## Basic Command Line Usage

### Navigating the Filesystem


- `pwd`: Print working directory.
- `cd [directory]`: Change directory.
- `ls`: List directory contents.
![Screenshot from 2024-06-26 12-58-42](https://github.com/siddharthsinghchaudhari/Linux/assets/120357061/4ee45f34-5c69-4acf-b1cb-b34ef79e28cd)

`UPDATED COMMANDS`


## File and Folder Create Command 
### 1. Touch Command
* touch command is used to create a new empty file[s]
```bash
touch F1.txt
```
```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ touch F1.txt
sidharth@Sidharth:~/Desktop/LinuxTasks$ ls
F1.txt

```

**With the help of touch command we can also create multiple files at once**
```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ touch F1 F2 F3 F4
sidharth@Sidharth:~/Desktop/LinuxTasks$ ls
F1  F1.txt  F2  F3  F4

```


### 2. vim command
* `vim` command is an editor to create or edit a text file. It is also used to open a file in vim editor
```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ vim F1.txt
```
**press "i" to insert the content into the file once the vim editor opens.**

```bash

this is written in F1.txt
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
Type  :qa  and press <Enter> to exit Vim                      1,25          All



```
**Once you are done with inserting content, press "Esc" and type ":wq" to save and quit the vim editor.**

**some common Vim commands that are useful for editing text in the vim editor**
1. Save the file (write).
```bash
:w
```
2. Quit Vim editor.
```bash
:q
```
3. Save and quit Vim editor
```bash
:wq or :x
```
4.  Quit without saving.
```bash
:q!
```

### 3. MKDIR Command
* `mkdir` (make directory) command is used for creating a new directory(Folder).
```bash
mkdir directory_name
```

```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ mkdir KEENABLE
sidharth@Sidharth:~/Desktop/LinuxTasks$ ls
F1  F1.txt  F2  F3  F4  KEENABLE

```

**we can create multiple directories at once**
```bash
mkdir d1 d2 d3 d4
```

```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ mkdir d1 d2 d3 d4
sidharth@Sidharth:~/Desktop/LinuxTasks$ ls
d1  d2  d3  d4  F1  F1.txt  F2  F3  F4  KEENABLE

```

## Cmmand to Check File/Folder's Content 
### 1. ls command
* `ls` is a shell command in linux. It is used to obtain a list of all content in the current directory.

**ls options**
1. `ls -a` (all)- It is used for list all files including hidden files.
2. `ls -s` (size)- It is used for list the biggest files first
3. `ls -l` (long)- List all the attributes of all files in the current directory including(type, size, ownership, permissions)
4. `ls -r` (reverse)- It is used for reverse the files in sort order
5. `ls -t` (time)- It is used for presents the files in the order of their modification time, the last modified placed first.

### 2. ll command
* `ll` command stands for long list files. `ll` command lists the files and directories in our current directory in a long format, providing detailed information such as file permissions, number of links, owner, group, size, and time of last modification .

### 3. cat command
* `cat` commmand is used for create files, concatinate more files together and also we can merge more than one file in a single files.
* Other features of `cat` command is that we can read the contents of a file.

**Create a file**
```bash
cat>F2.txt
```
**After this command, you can insert content in the file and press `Ctrl` + `D` to exit from the cat command**

```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ cat>F2.txt
this content is in F2.txt


```

**Read the file of content**
```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ cat F2.txt
this content is in F2.txt

```

**Concatinate the files**
```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ cat F1.txt >> F2.txt
sidharth@Sidharth:~/Desktop/LinuxTasks$ cat F2.txt
this content is in F2.txt



this is written in F1.txt

```

**Merge files contents in an another files.**
```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ cat F1.txt F2.txt > F3.txt
sidharth@Sidharth:~/Desktop/LinuxTasks$ cat F3.txt
this is written in F1.txt
this content is in F2.txt



this is written in F1.txt
```
### 4. GREP Command
* grep stands for `Global Regular Expression Print`
* `grep` command is used for search a particular string or keyword from a file and prints lines matching a pattern.
* It check line by line and print lines matching given pattern.
* we can use `grep` command anywhere like with files, searchiing for a file, directories etc.

```bash
grep String_name/keyword_name filename
```
Note: `grep command is a case sensitive command`
* For ignoring case sensative we can use `-i` command.

```bash
grep -i keyword filename
```

`If nothing matches the keyword in the file, then no output is displayed`

```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ cat F3.txt
this is written in F1.txt
this content is in F2.txt



this is written in F1.txt
sidharth@Sidharth:~/Desktop/LinuxTasks$ grep content F3.txt
this content is in F2.txt
sidharth@Sidharth:~/Desktop/LinuxTasks$ grep Content F3.txt
sidharth@Sidharth:~/Desktop/LinuxTasks$ grep -i Content F3.txt
this content is in F2.txt
sidharth@Sidharth:~/Desktop/LinuxTasks$ 

```

### 5. HEAD Command
* `head` command is used to display the starting lines of a text file.
* By default it shows first 10 lines of the file but we can specify a different number of lines using the `-n` option.

```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ cat>head.txt
1
2
3
4
5
6
7
8
9
10
11
12
sidharth@Sidharth:~/Desktop/LinuxTasks$ head head.txt
1
2
3
4
5
6
7
8
9
10

```
**For any specific number of lines**
```bash
head -n lineCount file_name
```
`or head -lineCount file_name`

```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ head -3 head.txt
1
2
3

```


### 6. TAIL Command
* The `tail` command is opposite of `head` command. It is used to display the last lines of a text file.
* By default it shows last 10 lines of the file but we can specify a different number of lines with the `-n` option same as `head` command.

```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ tail head.txt
3
4
5
6
7
8
9
10
11
12

```

**For displaying specific number of lines**
```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ tail -3 head.txt
10
11
12
```

Note: `Both head and tail are handy for quickly inspecting the beginning or end of a file, especially when dealing with log files, Large documents, or any text file with a significant amount of content.`

### 7. Less Command
* `less` command is used to display a contents of a file in an orgnized way.
* `less` command allows us to navigate forward and backward through the file.
* We can view multiple files with the help of `less` command.
```bash
less F1.txt F2.txt
```
** A new window opens with the content in the file** : Press `q` to quit the window.

```bash
less file_name
```

**Navigation Commands while using `less`**
1. `q`: For quit the page.
2. `space`: for Scroll down one page.
3. `b`: scroll up one page.
4. `enter`: scroll down one line.
5. `k`: scroll up one line.


### 8. More Command
* `more`  command in Linux used to view the contents of a file one screen at a time. It's useful for reading large files without opening them in an editor.

```bash
more file_name
```

```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ more F1.txt 
this is written in F1.txt

```

**Navigation Commands while using `more`**
* `Space:` Move to the next page.
* `Enter:` Move to the next line.
* `b:` Move back one page.
* `q:` Quit the more command.

### 9. Echo Command
* `echo` command in linux is used for displaying text and variables.

```bash
echo text_name
```

```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ echo My name is Siddharth Singh Chaudhari
My name is Siddharth Singh Chaudhari

```

**For New line** we put `\n` from where we want a new line along with `-e`.
```bash
echo -e "ContentBeforeNewLine \n ContentAfterNewLine"
```

```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ echo -e "My name is \n Siddharth Singh Chaudhari"
My name is 
 Siddharth Singh Chaudhari
sidharth@Sidharth:~/Desktop/LinuxTasks$ 

```

**For Printing the value of any variable with `echo` command.**
```bash
variable_name="value"
echo $variable_name
```

```bash
sidharth@Sidharth:~/Desktop/LinuxTasks$ a=5
sidharth@Sidharth:~/Desktop/LinuxTasks$ echo $a
5

```




`UPDATED TILL HERE`
### Managing Files

- `cp [source] [destination]`: Copy files or directories.
- `mv [source] [destination]`: Move or rename files or directories.
- `rm [file]`: Remove files.
- `mkdir [directory]`: Create a new directory.
- `rmdir [directory]`: Remove an empty directory.
- ![Screenshot from 2024-06-26 13-12-27](https://github.com/siddharthsinghchaudhari/Linux/assets/120357061/7554a881-d8a8-4a47-ae71-8645444ae60d)


## Managing Local Users and Groups

### Adding Users

- `useradd [username]`: Create a new user.
- `passwd [username]`: Set a password for a user.

![Screenshot from 2024-06-26 13-19-49](https://github.com/siddharthsinghchaudhari/Linux/assets/120357061/510ac52e-606b-48cd-95b9-3d212fe32a93)

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

## More Examples for better understanding:

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
# Add a new user named Govind
useradd Govind

# Set password for user Govind
passwd Govind

# Add user Govind to the group "sudo"
usermod -aG sudo Govind

# Delete user Govind and their home directory
userdel -r Govind

# Create a new group named developers
groupadd developers

# Add user Govind to the developers group
gpasswd -a Govind developers

# Remove user john from the developers group
gpasswd -d Govind developers
```
### Access Control Commands

```sh
# Change permissions of file1 to rwxr-xr-x
chmod 755 file1

# Change owner of file1 to user Govind
chown Govind file1

# Change owner and group of file1 to Givind and developers
chown Govind:developers file1
```
## Conclusion
This document lists some important commands used in Linux to manage file permissions and ownership. These commands are essential for maintaining security and proper access control in a Linux system. By setting the correct permissions and ownership, you can ensure that only authorized users can read, write, or execute specific files. 

Properly managing file permissions and ownership is crucial for system security and user collaboration. It ensures that files are accessible only to those who are supposed to have access, protecting sensitive data and maintaining system integrity.


## References
1. https://docs.kernel.org/
2. RHEL 124 
3. https://www.redhat.com/sysadmin/linux-user-group-management
