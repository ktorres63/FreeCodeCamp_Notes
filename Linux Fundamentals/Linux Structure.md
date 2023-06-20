## Philosphy 
|Principle|Description|
|-|-|
|Everything is a file|All configuration files for the various services running on the Linux opertaing system are stored in one or more text files|
|Small, single-purpose programs|Linux offers many differnt tools that we willwork with, which can be combined to work together|
|Ability to chain programs together to perform complexx tasks|The integration and combination of different tools enable us to carry out many larrge and complex tasks, such as processing or filtering specific data results.|
|Avoid captive user interface|Linux is designed to work mainly with the shell(or terminal),which gives the user greater control over the operating system|
|Configuration data stored in a text file|An examplepf such a file is the /etc/passwd file, wich stores all users registered on the system|

## Components
|Component|Description|
|---|---|
|Bootloader|A piece of code that rund to guide the booting process to start the operating system. Parrot Linux uses the GRUB bootloader|
|OS Kernel| The kernel is the main component of an operating system. It manages the resources for system's I/O devices at the hardware level
|Daemons|Background services are called "daemons" in linux. Their purpose is to ensure that key functions such as scheduling, printing, and multimedia are working correclty. These small programs load after we booted or log into the computer|
|OS Shell|The operating system shell or the command language interpreter( also known as the command line) is the interface between the OS and the user. This interface allows the user to tell the OS what to do. The most commonly used shells are bash, Tcsh/Csh,Ksh,Zsh and fish|
|Graphic server|This provides a graphical sub-system(server) called "X" or "X-server" that allows graphical programs to run locally or remotely on the X-windowing system|
|Window Manager|Also known as a graphical user interface(GUI). There are many options,include GNOME,KDE,MATE, Unity and Cinnamon. A desktop environment ussually has several applications, including file and web browsers. These allow the user to access and manage the essential and frequently accessed features and services of an operating system|
|Utilities|Applications or utilities are programs that perform particular function for the user or another program|

## Linux Architecture 
|Layer|Description|
|-|-|
|Hardware|Peripheral devices such as the system's RAM, hard drive,CPU and others|
|Kernel|The core of the linux operating system whose function is to virtualize and control common computer hardware resources like CPU allocated memory, accesed data, and others. The kernel gives each process its own virtual resources and prevents/mitigates conflicts between different processes|
|Shell|A command line interface (CLI) also known as a shell that a user can enter commands into to execute the kernel's functions|
|System Utility|Makes available to the user all of the opreating system's functionality|
## File System Hierarchy 
The linux operating system is structured in a three-like hierarchy and is documented in the filesystem hierarchy standard (FHS)

![[hierarchy.png]]


|Path|Description|
|-|-|
|/|The top-level directory is the root filesystem and contains all of the files required to boot the operating system before other filesystems are mounted as well as the files required to boot the other filesystems. After boot, all of the other filesystems are mounted at standard mount points as subdirectories of the root|
|/bin|Contains essential command binaries|
|/boot|Consist of the static bootloader, kernel executable, and files required to boot the Linux OS|
|/dev|Contains device files to facilitate access to every hardware device attached to the system|
|/etc|Local system configuration files. Configuration files for installed applications may be saved here as well|
|/home|Each user on the system has a subdirectory here for storage|
|/lib|Shared library files that are required for system boot|
|/media|External removable media devices such as USB drives are mounted here|
|/mnt|Temporary mount point for regular filesystems|
|/opt|Optional files such as third-party tools can be saved here|
|/root|The home directory for the root user|
|/sbin|This directory contains executables used for system adimnistration (binary system files)|
|/tmp|The operating sytem and many programs use this directory to sore temporary files. This directory is generally cleared upon system boot and may be deleted at other times without any warring|
|/usr|Contains executables, libraries, man files, etc
|/var| This directory contains variable data files such as log files, email in boxes, web application related files, cron filess, and more|


