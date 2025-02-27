# Introduction to Linux


## Introduction to Linux

1. Linux Distributions

   Linux is free software, it allows to do all sort of things with it. The main component in linux is the kernel, which is the part of the operating system that interfaces with the hardware. Applications run on top of it. 
   Distributions pack together the kernel with several applications in order to provide a complete operating system. There are hundreds of linux distributions available. In
   this lab we will be using Ubuntu as it is one of the largest, better supported, and user friendly distributions.


2. The Graphical Interface

   Most linux distributions include a graphical interface. There are several of these available for any taste.
   (http://www.howtogeek.com/163154/linux-users-have-a-choice-8-linux-desktop-environments/).
   Most activities can be accomplished from the interface, but the terminal is where the real power lies.

### Playing around with the file system and the terminal
The file system through the terminal

   Like any other component of the OS, the file system can be accessed from the command line. Here are some basic commands to navigate through the file system:

   - ``ls``: List contents of current directory
   - ``pwd``: Get the path of current directory
   - ``cd``: Change directory
   - ``cat``: Print contents of a file (also useful to concatenate files)
   - ``mv``: Move a file
   - ``cp``: Copy a file
   - ``rm``: Remove a file
   - ``touch``: Create a file, or update its timestamp
   - ``echo``: Print something to standard output
   - ``nano``: Handy command line file editor
   - ``find``: Find files and perform actions on it
   - ``which``: Find the location of a binary
   - ``wget``: Download a resource (identified by its url) from internet 

Some special directories are:
   - ``.`` (dot): The current directory
   -  ``..`` (two dots): The parent of the current directory
   -  ``/`` (slash): The root of the file system
   -  ``~`` (tilde):  Home directory
      
Using these commands, take some time to explore the Ubuntu filesystem, get to know the location of your user directory, and its default contents. 
   
To get more information about a command call it with the ``--help`` flag, or call ``man <command>`` for a more detailed description of it, for example ``man find`` or just search in Google.

   
## SSH - Server Connection

1. The ssh command lets us connect to a remote machine identified by SERVER (either a name that can be resolved by the DNS, or an ip address), as the user USER. The second command allows us to copy files between systems (you will get the actual login information in class).

   ```bash
   
   # connect
   ssh USER@SERVER
   ```

2. The scp command allows us to copy files form a remote server identified by SERVER (either a name that can be resolved by the DNS, or an ip address), as the user USER. Following the SERVER information, we add ':' and write the full path of the file we want to copy, finally we add the local path where the file will be copied (remember '.' is the current directory). If we want to copy a directory we add the -r option. For example:

   ```bash
   # copy 
   scp USER@SERVER:~/data/sipi_images .
   
   scp -r USER@SERVER:~/data/sipi_images .
   ```
   
   Notice how the first command will fail without the `-r` option

See [here](ssh.md) for different types of SSH connection with respect to your OS.

## File Ownership and permissions   

   Use ``ls -l`` to see a detailed list of files, this includes permissions and ownership.
   Permissions are displayed as 9 letters, for example the following line means that the directory (we know it is a directory because of the first *d*) *images* belongs to user *vision* and group *vision*. Its owner can read (r), write (w) and access it (x), users in the group can only read and access the directory, while other users can't do anything. For files the x means execute. 
   ```bash
   drwxr-x--- 2 vision vision 4096 ene 25 18:45 images
   ```
   
   -  ``chmod`` change access permissions of a file (you must have write access)
   -  ``chown`` change the owner of a file

## Anaconda Setup

   To download Anaconda, use the following command:
   ```bash
   ~$: wget https://repo.anaconda.com/archive/Anaconda3-2020.02-Linux-x86_64.sh
   ```
   then run the bash file:
   ```bash
   ~$: bash Anaconda3-2020.02-Linux-x86_64.sh
   ```
   press `enter` until you finish the terms and conditions and then type `yes` in all the questions. 
   
   Finally, execute ~.bashrc:
   ```bash
   ~$: source ~/.bashrc
   ``` 

### More information on

http://www.ee.surrey.ac.uk/Teaching/Unix/ 
