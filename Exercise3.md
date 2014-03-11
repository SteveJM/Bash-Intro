# Exercise 3

For these exercises type the characters in quotes as they are shown below and press the <Return> key after each line. This exercise assumes that you have successfully completed exercise 1, which created a directory for all of the work called 'BashIntroExercises' in you home directory.

1. We are going to start by creating a few files for use in the rest of this exercise. All of the commands used should be familar to you, in fact this will also serve as a useful reminder of what you have learnt so far. Enter the following commands:

    > cd ~/BashIntroExercises  
    > ls -l /tmp > tmp_files  
    > ls -l / > root_files  
    > mkdir one_directory two_directory three_directory  
    > ls -l ~ > one_directory/home_files  
    > ls -l /etc > two_directory/etc_files  
    > ls -l > three_directory/one_files  
    > cp -r one_directory three_directory

    Here we have repeatedly used the 'ls' (list) command and captured the output in order to create a few files. Note that when we ran the 'mkdir' (make directory) command we gave it three directory names to create at the same time. Notice also that we have used a '-r' option with the copy command, this tells 'cp' to copy "recursively" (this means copy the source item and everything below it to the destination).

2. Now lets find a file, run the following command:

    > find . -name home_files

    The full 'pathname' of the 'home_files' file is displayed. We talk about a complete directory and filename as being a path. But what did we ask the 'find' command to do ?  
    
    We gave the find command three 'arguments' (arguments are simply paramters that the command we are running is given to use, we have already been using arguments with the other commands that we have been running, such as directory or file names.  
    
    The first argument ('.') is the starting location from where we want to start looking. You might recall from exercise 2, step 2 that '.' means "the current directory".  
    
    The next argument tells find that we are looking for something by name.  
    
    The final argument is the name that we are looking for.
    
    So, putting it altogether we said find anything called 'home_files' starting with the current directory. You can now see the effect of the recusive copy command.

3. Now for a more advanced use, type the following:

    > find /var -name "*.log"
    
    Here we have used the same syntax, except that we have told find to start its search in the '/var' directory. We have also used a wildcard because we are unsure of exactly what the name of the item we want to find is called. This has to be quoted, don't worry about the reason for using quotes for the time being, that will be revealed in a later course. For now accept that when using wildcards they must be in quotes.

4. Here's a slightly more complicated example, compare the outout of the following two commands:

    > find . -name "one*"  
    > find . -type f -name "old*"

    The first command should be simple enough to understand. However, in the second command we have introduced a further concept. The 'find' command can also take a '-type' argument, this must be followed by a further argument indicating the type of item that we are looking for. For now, the two 'types' that we might want to use are 'f' for a file, or 'd' for a directory.
    
5. Suppose that we don't want to find a file having a certain name, but a file containing a certain name, this is where 'grep' comes in. Type the following command:

    > grep tmp *
    
    The syntax and output might not be quite what you were expecting. What we have asked is for grep to look for the word "tmp" in and files in our current directory, and it has shown us all matching occurrences.  
    
    Notice that here the wildcard character was not quoted.  This is a subtle difference in what we are asking. When we ran find, we wanted the find command to know that we are looking for anything ending with '.log'. In this case we want grep to search through any files in our current directory.  
    
    If we had missed the quotes off from the find command it would have tried to match files in our durrent directory, not found any, and then given us an error.  
    
    If we had included quotes around the wildcard in trhe grep command, it would have looked for a file explicitly called '*', not found one, and similarly given us an error.

6. Suppose, rather than the matching occurrences we want to know the name of the item that contained the match, well grep can do that for us too:

    > grep -l tmp *
    
    The '-l' option tells grep to just list the items that contain the matching text.
    
    As you might imagine grep is capable of a whole lot more than what you've seen here, including searching for very complex patterns. I intend to cover that in a later course on regular expressions if there is sufficient demand.

7. Now lets look at the 'tar' command:

    > tar -cvf files.tar three_directory
    
    What have we asked tar to do ?  
    
    Well, we gave it three options all at once '-c' '-v' and '-f'. The '-c' option instructed tar to Create a new "tar" file.  The '-v' option instructed tar to give us verbose output of its activities.  The '-f' option told tar that we wanted the output written to a file. Because we used the '-f' option, the next argument must be the name of the file in which it is to store our files. Finally we gave it the name of the item that we wanted to include. Often we call this "tarring up some files"; we just tar'd up our "three_directory".  
    
    You will notive that tar works recursively and can see the contents of the tar file being created. Note, also that we could have included further items (directories or files) on the end of the tar command to be included.

8. Examing a tar file.

    > tar -tvf files.tar
    
    This command is very similar to the previous command, but instead of the '-c' option to "create" a tar file we used the '-t' option to "tell" us what is in the tar file.

9. Extracting files from a tar file.

    > rm -r three_directory  
    > ls -l
    
    First we have removed the "three_directory". You can see that it has gone.  Now, lets retrieve it from our tar file.  
    
    > tar -xvf files.tar
    > ls -l

    The tar command was similay to those used previously, except we used the '-x' option to eXtraxt our files. You can see the tar command list the files that it extracted and can then see that the "three_directory" has been restored.  
    
    Using tar like this to tar up groups of files, verify the contents are as expected and then to extract them again provides us with a simple means of preserving some files, perhaps as a local backup, or to copy to another computer or thumb-drive.

----
That completes this exercise. You may wish to further experiment with the 'find', 'grep' and 'tar' commands to make sure that you inderstand them.
