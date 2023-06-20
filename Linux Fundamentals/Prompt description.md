The home directory for user is marked with a tilde ~ 

The dollar sign in this case stands for a user. As soon as we log in as root the character changes to a hash <#> and looks like this

![[user,root.png]]
The prompt can be customized using special characers and variables in the shell's configuration file (.bashrc)

.bashr is in ~/.bashrc 
![[bashrc.png]]

The prompt can be customized using special characters and variables in the shell's configuration file. For example, we can use: the \\u character to represent the current username, \\h for the hostname, and \\w for the current working directory

|Special Character|Description|
|-|-|
|\\d|Date (Mon Feb 6)|
|\\D|Date (YYYY-MM-DD)|
|\\H|Full hostname|
|\\j|Number of jobs mnageed by the shell|
|\\n|new line|
|\\r|return|
|\\s|name of the shell|
|\\t|current time 24 hours|
|\\T|current time 12 hours|
|\\@|current time|
|\\u|current username|
|\\w|full path of the current working directory|

## Getting Help

Another tool that can be usefil in the beginning is apropos

## System Information

|Command|Description|
|-|-|
|whoami| Display current username|
|id|Returns user identity|
|hostname|Sets or  print the name of current host system|
|uname|Prints basic information about the operating system name and system hardware|
|pwd|Returns working directory name|
|ifconfig|The ifconfig utility is used to assign or view an address to a network interface and/or configure network interface parameters|
|ip|Ip is a utility to show or manioulate routing. network devices, interfaces and tunnels.|
|netstate|shows network status|
|ss|utility to investigate sockets|
|ps|Shows process status|
|who|Display who is logged in|
|env|prints enviroment or sets and executes command|
|lsblk|list block devices|
|lsusb|list usb devices|
|lsof|list opened files|
|lspci|list pci devices|


### Id
Id command expands on the whoami and prints out our effective group membership and IDs.

![[id.png]]

### uname

prints system information  with man uname we can see differentss utilities of this command
![[uname.png]]
### Logging in via SSH

Secure Shell (SSH) refers to a protocol that allows clients to acces and execute commands or actions on remote computers. SSH is one of the permanently installed standard tools and is the preferred choice formany administrators to configure and maintain a computer through remote access
![[ssh1.png]]

when we use ls -l 
![[ls-l.png]]

|Column Content|Description|
|--|-|
|drwxr-xr-x|Type and permissions|
|2|Number of hard lins to the file/directory|
|cry0l1t3|Owner of the file/directory|
|htbacademy|Group owner of the file/directory|
|4096|Size of the file or the number of blocks used to store the directory information|
|Nov 13 17:37|Date and time|
|Desktop|Directory name|

Since we were in the home directory before, we can quickly jump back tothe directory we were last in
```cd -```
![[cd-.png]]
Let us return to the directory /dev/shm before and then execute the clear command to clean up our terminal
```cd /dev/shm && clear```

Another way to clean up our terminal is to use the shortcut \[Ctrl] +\[L]
We also can search through the command history using the shortcut \[Ctrl] + \[R]

## Working with files and directories
The terminal in linux is a more efficient and faster tool because you can access the files direclty with a few commands and edit and modify them selectively with regular expressions(regex)


* We can look at the whole structure after creating the parent directories with the tool tree

![[tree.png]]

* with the command mv we can move and alo rename file and directories

#### Rename File
```bash
mv info.txt information.txt
```

#### Move files to specific directory
```bash
mv information.txt readme.txt Storage/
```
 We copy the files information.txt and readme.txt into the Storage/ directory

#### Copy readme.txt
```bash
cp Storage/readme.txt Storage/local/
```

## Find files and directories
We don't have to manually browse through every single folder and check when modified for the last time. There are some tools we can use to make this work easier

### Which 
This tool returns the path to  the file or link that should be executed. This allows us to determine if specific programs like cURL, netcat, wget, python, gcc, are available on the operating system

```bash
which python
```

If the program we search for doesn't exist, no results will be displayed

### Find
Besides the function to find files and folders, this tool also contains the funtion to filter the results. We can use filter parameters like the size of the file or the date. We can also specify if we only search for files or folders
```bash
find <location><options>
```
![[findExample.png]]

|option|Description|
|-|-|
|-type f|Define the type of the searched object. In this case f stands for file|
|-name \\\*.conf | -name indicate the name of the file **use backslash** to use (\*) |
|-user root|Filters all siles whose owner is the root user|
|-size +20k|We can then filter all the located files and specify that we only want to see the files that are larger than 20KiB| 
|newermt 2020-03-03| with this option we set the date. Only files newer than the specified data will be presented|
|-exec ls -al {} \\;|This option executes the specified command using the curly brackets as placeholders for each result. The backslash escapes the next character from being interpreted by the shell because otherwise, the semicolon would terminate the command and not reach the redirection|
|2>/dev/null| This is a STDERR redirection to the null device. This redirection wnsures that no errors are displayed in the termianal. This redirection must not be an option of the find command|

### Locate
It will take much time to search through the whole system for our files and directories to perform many different searches. The command locate offers us a quiker way to search through the system. In contrast to the find command, locate works with a local database that contains all information about existing files and folders. We can update this databse with the following command
```sudo updatedb```
```locate \*.conf```

However this tool doesn't have as many filter options that we can use. So it's always worth consideering whether we can use the locate command or instead use the find command. It always depends on what we are looking for

## File Descriptors and redirections

A file descriptor (FD) in Unix/Linux operating systems is an indicator of connection maintained by the kernel to perform input/output (IO) operations. In windows- based operating systems, it's called filehandle. It's the connection generally to a file from the operating system to perform I/O operations. By default the first three file descriptors in linux are:
1. Data Stream for Input
	* STDIN - 0
2.  Data Stream for Output
	* STDOUT - 1
3. Data Stream for output that releases to an error occurring
	* STDERR - 2

### STDIN and STDOUT

Let us see an example with cat. When reunning cat, we give the running program our standard input (STDIN - FD 0), marked gree, wherein this case "SOME INPUT" is. As soon as we have confirmed our input with \[ENTER], it is returned to the terminal as standard output (STDOUT -FD 1), marked red

![[stdin-stdout.png]]

### STDOUT and STDERR
In the next example, by using the find command, we will see the standard output(STDOUT - FD 1) marked in green and standard error (STERR -FD 2) marked in red

``` find /etc/ -name shadow```

![[stdout-stderr.png]]

We can redirect the resulting errors to the "null device" which discards all data 

```find /etc/ -name shadow 2>dev/null```

### Redirect STDOUT to a file

We can redirect STDOUT to a file with the name results.txt that will only contain standard output without the standard errors
```find /etc/ -name shadow 2>dev/null > results.txt```

### Redirect STDOUT and STDERR to separate Files

Remember 
- FD 1 - STDOUT
- FD 2 - STDERR

```find /etc/ -name shadow 2> stderr.txt 1> stdout.txt```

![[stderr,stdout-Redirect.png]]

### Redirect STDIN
As we have already seen, in combination with the file descriptors, we can redirect errors and output with greater-than character(>). This also works with the lower-than sign(<). However, the lower-than sign serves as standard input (FD 0 - STDIN). These characters can be seen as "direction" in the form of an arrow that tells us "from where" and "where to" the data should be redirected. We use the cat command to use the contents of the file "stdout.txt" as STDIN

```cat < stdout.txt```

![[redirect_stdin.png]]

### Redirect STDOUT and Append to a file

If we want to append STDOUT to our existing file, we can use the double greater-than sign (>>)
```find /etc/ -name passwd >> stdout.txt 2>/dev/null```
![[append(>>).png]]

### Redirect STDIN stream to a file
We can also use the double lower-than chracters (<<) to add our standard input through a stream. We can use the so-called End-Of-File (EOF) function of a linux system file, which defines the input's end. In the next example, we will use the cat command to read our streaming input through the stream and direct it to a file called "stream.txt"

```cat << EOF >stream.txt```

### Pipes
Another way to redirect STDOT is to use pipes(|). These are useful when we want to use the STDOUT from one program to be processed by another. One of the most commonly used tools is grep
```find /etc/ -name *.conf 2>/dev/null | grep systemd```

![[pipes.png]]

The redirections works, not only once. We can use the obtained results to redirect them to another program. For the next example, we will use the tool called wc, which should count the total number of obtained results
```find /etc/ -name *.conf 2>/dev/null | grep systemd | wc -l```

![[twoPipes.png]]




















































