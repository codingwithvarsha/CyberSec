LINUX FUNDAMENTALS 1  
#part1

Linux is an operating system just like Windows.The name "Linux" is actually an umbrella term for multiple OS's that are based on UNIX (another operating system).
-- Linux was first released in 1991. And we use terminal here instead of GUI (Graphical user interface).
-- learned the first few most basic commands : 'echo' and 'whoami'.
-- learned more commands for Interacting with the File System like 'ls','cd','cat' and 'pwd'. 
These are basics commands that are used for navigation and interation.

**now the commands that we use for navigating or searching:
--the command is find and its syntax is find -name file_name - it helps to find the file with the file name that we have specified only if it exists.
we can also use find -name *.txt - it helps to list all the files ending with .txt.
--the next command grep - it can used to list the content of the file . EX:  grep "81.143.211.90" access.log.

**now we will use the commands of shell operating:
--  we use & command to operate anything in the backgroud . EX: if we want to download anything in background but want to run other commands in ther terminal.
-- we can use "&&" to make a list of commands to run for example command1 && command2. However, it's worth noting that command2 will only run if command1 was successful.
-- we can use ">" to redirect any command or info.
-- we can use ">>" allows to append the output to the bottom of the file rather than replacing the content.
______________________________________________________________________________________________________________

LINUX FUNDAMENTALS 2
#part2

--To access the ssh : a command to log in to the remote machine using SSH. The command to do so is ssh and then the username of the account, @ the IP address of the machine. EX: ssh tryhackme@MACHINE_IP 

**going back to navigation and interaction we used ls command to list the files.
--we can also use the  command "ls -a "(short for -all)to list all the hidden files in the directory.And the hidden files start with "." like .hiddenfile .and also there is one more command that is "ls --help" which list the possible options that the command accepts, provide a brief description and example of how to use it.
--we use the "man" command to give brief description about the mentioned command . EX : man ls -this will show the complete imformation about the ls and the commands realted to it.

** System interaction :-
--we use "touch" command to create a file.
--we use "mkdir" command which stands for make_directory is used in creating a folder.
--we use "cp" command which stands for copy is used to copy a file or folder.
--we use "mv" command which stands for move as the name suggests used to move a file or a folder.
--we use "rm" command which stands for remove as the name suggests used for removing a file or a folder.We can also use  -R switch alongside the name of the directory we wish to remove.
--we use "file" for determining the type of file.

**permissions:-
There are 3 types of permission in a file:
>Read
>Write
>Execute
All three permissions are granted based on the principle of least privilege. And they are given to users, groups and others.
The least privilege principle (PoLP) is a fundamental concept in information security that dictates that every user, program, or system should have only the minimum level of access necessary to perform its tasks.
--so the content of the current directory or the permission access can be seen using the "ls -lh".
--the "su" command is used for switching users in Linux.

**Common directories:-
--we use "/etc" (short for etcetera) is a commonplace location to store system files that are used by your operating system.  
--we use "/var" as this folder stores data that is frequently accessed or written by services or applications running on the system. For example, log files from running services and applications as /var/log.
--we use "/root" as this is the home directory for the "root" user.
--we use "/tmp" Short for "temporary", as it is volatile and is used to store data that is only needed to be accessed once or twice. Similar to the memory on your computer, once the computer is restarted, the contents of this folder are cleared out.
______________________________________________________________________________________________________________

LINUX FUNDAMENTALS 3
#part3

There are different types of text editor and two of them are : - nano  - VIM
nano is used to create or edit a file. While VIM is much more advanced.
--while downloading the file we use the command "wget" it allows us to download files from the web via HTTP
--SCP is a source of copying files and  scp command is (remembering that the format of SCP is just SOURCE and DESTINATION)
--we use the 'ps' command to provide a list of the running processes as our user's session and some additional information such as its status code, the session that is running it, how much usage time of the CPU it is using, and the name of the actual program or command that is being executed.

**HTTP server
"HTTPServer"= This module turns your computer into a quick and easy web server that you can use to serve your own files, where they can then be downloaded by another computing using commands such as curl and wget. 

**Managing Processes

You can send signals that terminate processes; there are a variety of types of signals that correlate to exactly how "cleanly" the process is dealt with by the kernel. To kill a command, we can use the appropriately named kill command and the associated PID that we wish to kill. i.e., to kill PID 1337, we'd use kill 1337.

Below are some of the signals that we can send to a process when it is killed:

SIGTERM - Kill the process, but allow it to do some cleanup tasks beforehand
SIGKILL - Kill the process - doesn't do any cleanup after the fact
SIGSTOP - Stop/suspend a process

**Getting Processes/Services to Start on Boot

Some applications can be started on the boot of the system that we own. For example, web servers, database servers or file transfer servers. This software is often critical and is often told to start during the boot-up of the system by administrators.

In this example, we're going to be telling the apache web server to be starting apache manually and then telling the system to launch apache2 on boot.

the use of systemctl -- this command allows us to interact with the systemd process/daemon. Continuing on with our example, systemctl is an easy-to-use command that takes the following formatting: systemctl [option] [service]

For example, to tell apache to start up, we'll use systemctl start apache2. Seems simple enough, right? Same with if we wanted to stop apache, we'd just replace the [option] with stop (instead of start like we provided)

We can do four options with systemctl:

Start
Stop
Enable
Disable

--Crontab is one of the processes that is started during boot, which is responsible for facilitating and managing cron jobs.

