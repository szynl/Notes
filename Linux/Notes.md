## What is Linux?

The Linux kernel is the core component of a Linux operating system, acting as the central hub that manages communication between the hardware and software, essentially controlling all essential functions of the OS, including memory allocation, process scheduling, file system access, and device management; it is considered the most critical part of the Linux system. 

## Linux File System Directories

- **`/`**: The root directory, the top-level directory in the file system hierarchy.
- **`/bin`**: Contains essential system binaries (e.g., `ls`, `cp`, `cat`) for system operation.
- **`/boot`**: Stores bootloader files, including the Linux kernel.
- **`/dev`**: Holds device files that represent hardware devices (e.g., `/dev/sda` for a hard drive).
- **`/etc`**: Contains system configuration files and settings.
- **`/home`**: Stores user-specific data and configuration files for individual users.
- **`/lib`**: Contains essential shared libraries and kernel modules needed by system binaries.
- **`/media`**: Mount point for removable media (e.g., USB drives, CDs).
- **`/mnt`**: Temporary mount point for mounting filesystems manually.
- **`/opt`**: Holds optional software packages that are not part of the core distribution.
- **`/proc`**: A virtual directory that provides system and process information in real-time.
- **`/root`**: The home directory for the root (superuser) account.
- **`/run`**: Stores runtime data and system information that changes during boot.
- **`/sbin`**: Contains system binaries for system administration, usually requiring root access.
- **`/srv`**: Holds data for services provided by the system (e.g., web server files).
- **`/sys`**: A virtual filesystem providing information and configuration about the kernel and devices.
- **`/tmp`**: Temporary files created by programs, often cleared on reboot.
- **`/usr`**: Contains user-related programs and data, including libraries, binaries, and documentation.
- **`/var`**: Stores variable data like logs, databases, and temporary application files.

## Linux Commands

`sudo` - **superuser do**: allows permitted user to run commands with elevated commands and perform administrative tasks with root access; system verifies user is in the **sudoers file** and cache the authorisation for a short time

eg. `sudo apt update` updates all available packages

### Get Information
`man <topic>` - display **user manual** for a command
eg. `man ls` to display detailed information about the `ls` command

`ls` - **list** all files and directories in the current working directory   
`-l` - show details such as size and ownership  
`-t` - sort by last modified date  

`du <directory>` - display **disk usage** of a directory and its subdirectories in kilobytes  
`-s` - summarise total size of directories  
`-h` - display sizes in human readable format  

eg. `du -sh /path/to/directory` lists all files and subdirectories within a directory

### File Manipulation
`touch <file>` - create new file called `<file>` 

`cat <file>` - display contents of file  
`head <file>` - display first 10 lines  
`tail <file>` - display last 10 lines  

`nano <file>` - simple text editing     
`vi <file>`/`vim <file>` - for more complicated text editing

`mv <file> <new file>` - rename `<file>` to `<new file>`  
`cp <file> <new file>` - copy `<file>` to `<new file>`  

`rm <file>` - remove a file

`ln -s <file> <symbolic link name>` - create a symbolic (reference type) link which acts as a shortcut by pointing to the path   
`ln <file> <hard link name>` - create a hard (direct reference) link which effectively creates another name for the same file  

### Directory Manipulation
`mkdir <directory>` - create new directory called `<directory>`  
`pwd` - list path of the **current working directory**    

`cd <directory>` - **change directory** to `<directory>`    
`cd ..` - move up one directory level   
`cd /` - return to root directory   

`rm -rf <directory>` - remove a directory and its contents recursively  
`-f` - remove by force  
`-r` - remove recursively  

### Search
`locate <keyword>` - search for file or directory in precompiled cache, faster than `find` but less reliable  
`find <keyword>` - search for file or directory in real system, slower than `locate` but always up to date  

`grep <keyword> <file>` - search for specified keyword in file    
`grep <keyword> *` - search for specified keyword in all files in current directory  
`-i` - ignore case when searching  
`-r` - search recursively  
`-x` - print all lines where a match was found  
`-c` - count number of matches  
`-n` - show line number where a match was found  

### Process Management
`kill <pid>` - kill a process specified by its id   
`pkill <name>` - kill a process specified by its name  

`ps aux` - list all running processes  
eg. `ps aux | grep <process>` to find all running services specifically named `<process>`  

`systemctl list services` lists all the active/inactive services (e.g. cron, ssh)

`reboot` - restart system  
`shutdown -h now` - shutdown system immediately  

`cron` - schedules and automates tasks and commands  
`-l` - list all scheduled tasks in the cron table  
`-e` - edit crontab file for editing  
`-r` - deletes the cron table and removes all jobs  

```
* * * * * command_to_run
- - - - -
| | | | |
| | | | +---- Day of the week (0-7, where 0 and 7 are Sunday)
| | | +------ Month (1-12)
| | +-------- Day of the month (1-31)
| +---------- Hour (0-23)
+------------ Minute (0-59)
```
eg. `0 2 * * * /path/to/script.sh` runs `script.sh` at 2AM every day  

### Permission Management
`chown <owner> <file>` - changes owner of a file

`chmod <xxx>`  
`user | group | others`  
`r` - read permissions  
`w` - write permissions  
`x` - execute permissions  
`-` - no permissions  

| Number    | Permissions |
| -------- | ------- |
| 7  | rwx    |
| 6 | rw-     |
| 5    | r-x    |
| 4    | r--    |
| 3    | -wx    |
| 2    | -w-    |
| 1    | -x-    |
| 0    | ---    |

`chmod <xxx> <file>` - assign specified permissions to a file  
`chmod -R <xxx> <directory>` - assign permissions recursively to a directory and its subdirectories  
`-x` - remove execution permissions from a file    
`chmod <username> <file>` - change ownership of a file    

### Networking
`dig <domain>` - show DNS information of given domain  
`dig -x <host>` - perform reverse lookup for host  

`whois <domain>` - get information about a domain (e.g. whois google.com) 

`ip a` - get all ip information
`ip addr` - get ip address  
`ping <ip>` - check ping between host and given ip  

`ssh <username>@<ip>` - login as specified user on another server  

`wget <file>` - download file   

`traceroute <domain>` - trace route a packet takes when travelling from machine to host  
`telnet <domain> <port>` - connect to remote host on specified port (not really used much anymore)
