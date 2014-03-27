# Introduction
This is a short course aimed at getting you more comfortable using bash on the Raspberry Pi.  

If you are relatively new to the Raspberry Pi, the chances are that you've never heard of "bash" and are already wondering what this tutorial is /really/ about.  Fear not, "bash" is simply the command line tool with which you can interact with your Raspberry Pi (or other computer).  You access it simply by running one of the various "Terminal" application (e.g. LXTerminal).  

You should start a terminal now so that you can follow along with this course. When a terminal is started you will be presented with a bash prompt, similar to that below:

>   pi@raspberrypi ~ #

This is the default prompt, it shows your username and the name of the computer that you're using, it also shows which directory you are in, but more on that later. Ultimately, this prompt indicates that "bash" is ready to start running your commands.

# Part 1

You are probably used to the concept of files and directories that your computer uses to store information. At the very top is the root directory, below that can be further directories.  Any directory can contain further sub-directories, or files. This might all sound rather confusing at first, but all will become clear as we explore further. Lets get started.

### pwd

This command means "Print Working Directory". It displays your current directory location. You will notice that you location starts with a '/' character.  If you are in the "root" (top) directory, that is all you will see.  Typically, however, you will be in a directory further down than that.  You will therefore see a series of directory names, each separated by a '/' character. We call this a complete directory "Path" because it describes your location all the way down from the top-level directory.

### cd

This command means "Change Directory". It allows you to change your current directory location. You may move down to a further sub-directory, up to a higher directory, or even select somewhere else entirely.

### mkdir

This command allows you to make a new directory.

### rmdir

This command removes, or deletes, a directory.  The directory must be empty (not contain any sub-directories or files).

*Do exercise 1.*

# Part 2

### ls

This command lists the contents of the current directory. By default, 'ls' will show you the directories and files that are stored in your current directory. However, you can also give it the name of a directory to list. In common with many of the commands, 'ls' can be given additional "options".  These 'options' can be used to request more detailed information about the directory contents. There is always a space between the command itself and the options. The two most common options are '-l' which shows detailed information for each file, such as its size, and '-a' which tells 'ls' to include *all* files (by default files starting with a '.' are considered 'hidden'). Often both of these options are use together, as '-al'.

### cat

The command 'catalogues' (displays) the contents of a file. Note that it will attempt to work on whatever file it is given, if the file is not human readable (what we consider to be 'binary' data) you will get gobbledy gook out.

### cp

This command copies one or more files.  The general syntax is "cp source destination". A useful option is '-R which, if the source is a directory will recursively copy all of the contents below that location to the destination.

### mv

This command moves a file from one location to another. Like the 'cp' command, the general syntax is 'mv source destination'. The destination may be a different directory or the same directory. This is also effectively a rename command since it can be used to change either the location (directory) or the name of the file, or both. Note that you can 'move' directories or files with this command.

### rm

This command removes (deletes) a file. It has a very useful option '-r' which indicates that the file (or directory) removal is to be recursive though all sub-directories). This makes it very quick to delete a lot of data, but take care not to remove files that you want to keep.

*Do exercise 2.*

# Part 3

### find

This is a very powerful command for locating files that match a certain criteria.  This criteria can be based on the file name, type, or age.

### grep

This is a very powerful command for searching through the contents of files. It is useful for identifying files that contain certain information.

### tar

This command is used to create a bundle of files into a single item (an archive), or to extract files from the archive. It is common within Linux (the Operating System used by the Raspberry Pi) to use these archives as a means of exchanging a large number of files in one go.

### gzip, zip unzip

These commands are used to create or extract a compressed "zip" of files. "gz" files are zip files that use a different compression algorithm.

*Do exercise 3.*

# Part 4 - Processes

### top

This command presents a continuously updating list of the processes running on the system.  By default these are sorted according to how much CPU (processing capacity) they are using.

### ps

This command lists the processes that are running on the computer.

### kill

This command terminates a process.  It can be useful to stop a process that is consuming a lot of CPU power.  However, it should be used with care, as the process might be critical to the operation of your computer.

*Do exercise 4.*

# Part 5 - Networking

It is very likely that you will use you Raspberry Pi in a network. To do this it will communicate over a number of network "interfaces". We will now look at a number of commands that help us see what is going on and could help to diagnose network problems.

### ifconfig

Lists the networking interfaces. You may have a "wlan0" (Wireless Network) and / or a eth0 (Wired Network) interfaces.  You will also see a "lo" (loopback) interface. One of the most useful aspects to check is that the interface has an IP address associated with it, which will generally be displayed on the 2nd line of output for each interface after the words "inet addr:".

### ping

Attempts to communicate with a remote host using the network. This can be a simple way of checking that you Internet connection is working. Note, however, that some computers may choose not to respond to a "ping".

### traceroute

This shows the hops that network data takes to get from your Raspberry Pi to a remote computer.

*Do exercise 5.*

# Part 6 - Permissions

### chmod

This changes the permissions of a file or directory.

### sudo

This allows you to run commands as a super user (system administrator). Some commands can only be executed by the system administrator. Care should be taken when running commands as the system administrator; with great power come great responsibility.

# Part 7 - Being Lazy

Actually, this is really about working fast and efficiently. Some of these concepts might sound a bit tricky at first, however, once you get used to using them they can really save the amount of typing that you have to do, and therefore your time.

### history

You might want to recall a command that you have recently executed, perhaps to run again, or to modify slightly. To do this you can use the 'history' command to list all of your recently executed commands. Note that the command history will typically contain commands from previous occasions when you used your Raspberry Pi.

### Ctrl-R

Better than merely examining your command history, however, is to directly retrieve the command. To do this you start by holding down the 'Ctrl' key and then pressing the 'R' key, you will notice a change in your prompt. Now you can type a few letters from a previously used command, these do not have to be the first letters of the command, they can be from any part of it, perhaps the name of a file or directory that the command used. Once you've entered a few characters, if the command that has been retrieved is not exactly the one you want, you can now press 'Ctrl-R' more times just as you did at the start to go further back through your history of commands that match the text that you entered.  

Once the command you want is displayed you can either run it again be pressing return, or use the left and right arrow keys to move to a part of the command that you want to edit, perhaps to correct an error, or to change it slightly.

### Tab Completion

To save remembering and typing directory and file names you can use the tab key.  Once you have entered the initial characters of a directory or file name you can press the 'Tab' key and the complete name will be automatically presented (assuming what you have typed thus far uniquely identifies it). If the letters typed thus far do not uniquely identify a file or directory name, then nothing is displayed.  However, you can press the 'Tab' key twice in quick succession and it will list all possible matching names. You can then see which characters you need to enter to narrow down your selection. If hitting the 'Tab' key twice does not list any names at all, then what you have typed so far does not match anything.

# Further Reading

I hope that this short course has helped you to become more familiar and comfortable using the Raspberry Pi command line. Once you have grasped the commands that I have described above you will no doubt want to learn more about them.

### Help

Most commands take an option '-h' that displays some concise information on how to use them and what options are available. This information is perfect as a memory jogger.

### Manual Pages

There is a further command called 'man' (short for manual). You can use 'man command' (replace the word 'command' with that actual command that you want to see the manual pages for). This displays much more comprehensive information on what the command does and how to use it. At first the manual pages can seem slightly intimidating, however, they are generally written to present the information in a very precise manner. This information is perfect for learning more about the capabilities of a command.

# Feedback

I welcome any feedback that you may have on this course. Subject to sufficient demand I will write a follow-on course going into some of the more advanced uses of the commands described here and introduce some new commands.  

Thank you.