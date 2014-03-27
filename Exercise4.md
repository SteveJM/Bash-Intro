# Exercise 4

For these exercises type the characters in quotes as they are shown below and press the <Return> key after each line. This exercise assumes that you have successfully completed exercises 1 to 3, which created a directory for all of the work called 'BashIntroExercises' in you home directory containing several files.

1. We can see what our Raspberry Pi is currently running. Enter the following command:

    > top

    You will be presented with a table showing the "processes" that are running. Notice that you can see a few details for each "process", including:
    
    * The "pid" - this is a unique numeric identifier for each process.
    * The user who is running the process.
    * The command that is running
    * Various figures indicating how much memory and cpu the process is using at the current time.
    
    The list is sorted with the processes using the most CPU being shown at the top. This is a good way of seeing what your Raspberry Pi is busy doing. The "top" command keeps running, refreshing the display every few seconds.

2. Lets leave "top" running and start a new terminal window. Then enter the following command:

    > find / -name foo

    Because we are searching for a file named zoo starting at the root directory there will be a lot of directories to search through. This will take some time. You should see the "find" command in the output of the "top" command.  
    
3. If the "find" command is still running hold down the "Ctrl" key and press C. This is a simple way to stop a command from running. You should get a command prompt back. Now enter the following command:

    > ps
    
    This lists all of the processes that are running. It is similar to "top" but presents the slightly different information.  
    
    * Notice that it does not keep running after it has listed the processes.
    * Notice that it lists all of the processes, not only those that fit in one window (you can scroll your terminal window back to see the information that has disappeared off the top of it).
    
    The "ps" command is useful to see what is running on your Raspberry Pi.
    
4. We can capture the output from any command, just like we did in Exercise 2 and save it to a file.  Enter the following commands:

    > ps > processes.txt  
    > ls -l
    > cat processes.txt

    Notice that the "ps" command did not display any information on the screen.  Instead it wrote if to a file.  We can see the file that was created with the 'ls' command and see the contents of the file with the 'cat' command.
    
5. We can also join commands together using "pipes". This is a very powerful concept that I intend to explore in a subsequent course, but here is a little taster. Type the following command:

    > ps | grep top
    
    We have actually ran two commands here joined together. First the "ps" command that we used above. Earlier you would have noticed that 'ps' can output quite a lot of information, however, we "piped" the output from the 'ps' command through the text search command that we used in the previous exercise. We told 'grep' to only look for lines containing the word "top". You should see two lines reported; one for our 'top' command running in the other terminal, and one for this command itself (since it also has the word "top" in it.  
    
6. Notice the first number that is reported by the 'ps' command in step 5, this is the "pid", or process identifier that was mentioned when we were looking at the output from the 'top' command itself. Enter the following command:

    > kill xxxx
    
    Instead of "xxxx" type the value of the pid that you noticed in step 5, the one for the actual 'top' command, not the "grep top" that was also seen.  
    
    You will notice that the 'top' command running in the other window has stopped. This is the same as if you had pressed "Ctrl"-C into that terminal like we did for the "find" command in step 3. This is another was that we can "kill" (or stop) a process that is running. Notice that normally you are only allowed to "kill" your own processes (those whose "owner" is yourself.
    
----
That completes this exercise. You may wish to further experiment with the 'top', 'ps' and 'kill' commands to make sure that you understand them.
