# Exercise 2

For these exercises type the characters in quotes as they are shown below and press the <Return> key after each line. This exercise assumes that you have successfully completed exercise 1, which created a directory for all of the work called 'BashIntroExercises' in you home directory.

1.  Start by checking that you are in the couse directory:

>    Type: 'cd ~'
>    Type: 'ls'

You should, see a directory listing, as a minimum you should see you 'BashIntroExercises' directory.

2.  Type: 'ls -a'

This is a listing of 'all' files and directories in your current directory. As a minimum, note that in addition to the output from 1. above, it includes two special directories:

>    .  This represents the 'current' directory, i.e. the directory that you are listing.
>    .. This represents the 'parent' directory, i.e. the one above the directory that you are listing
       (you may recall that you used this in the previous section to change directory to the parent directory.

3.  We can also list the contents of any other directory.

>    Type: 'ls ..'

This is a listing of the contents of your parent directory.

4.  Here's another example:

>    Type: 'ls /tmp'

This is a listing of the '/tmp' directory.

5.  The 'ls' command will also show us more information.

>    Type: 'ls -l /tmp'

This is a 'long' listing of the '/tmp' directory. The more useful columns are listed below:
>   1st: The directory / file permissions
>   3rd: The directory / file owner
>   4th: the directory / file group
>   5th: the directory / file size
>   6th - 8th: The directory / file modification date
>   9th: The directory / file name.

The more astute will also notice that the first character of the permissions field is a 'd' where the item is a directory and a '-' where the item is a regular file.

6.  We now want to create some files, first we will make sure that e are in the course directory.

>    Type: 'cd BashIntroExercises'
>    Type: 'pwd'

    You should be in the 'BashIntroExercises' directory that you created during Exercise 1.

7.  Now will will repeat an earlier command with a slight twist.

>    Type: 'ls -l /tmp > listing.txt'

You will notice that this command, whilst similar to the one in step 5, has not output anything to the terminal. This command is using output redirection to write the output to a file. The use of redirection is indicated by the '>' character followed by the name of the file to which thev output should be written.  Be careful when using output redirection because if you use the name of an existing file then it will be overwritten.

>   Type: 'ls -l'

You should see the 'listing.txt' file in amoungst any other files that you may have.

>   Type: 'cat listing.txt'

This has displayed the contents of the 'listing.txt' file, as this was ceated by caturing the output from the previous command, the contents should look familiar. Note that the contents of this file is simply the listing of the '/tmp' directory at the time it was created, any changes to the '/tmp' directory will not be included in 'listing.txt'.

8.  Now that we have a file we can make a copy of it.

>   Type: 'cp listing.txt listing.bak'
>   Type: 'ls -l'

You will now see both of the files. Note that either the 'source' file (the first one), or the destination file (the second one) may be in completely different directories.

>   Type: 'mkdir Exercise2Backup'
>   Type: 'cp listing.txt Exercise2Backup'
>   Type: 'ls -l Exercise2Backup'

Note here that we didn't really give the copy command a new name for the file, we just specified the name of a directory.  When the copy commnand saw that the directory was there, it realised that you simply mean to make a copy of 'listing.txt' in the 'Exercise2Backup' directory.

8.  Alternatively, we can move it to another location.

>   Type: 'mv listing.bak Exercise2Backup'
>   Type: 'ls -l'

You should notice that the 'listing.bak' file is no longer shown, it is not there anymore.

>   Type: 'ls -l Exercise2Backup'

Ahhh, there is it.  As you no doubt expected, you moved it from its current location to the Exercise2Backup directory.

>   Type: 'mv listing.txt tmp_listing.txt'
>   Type: 'ls -l'

In this case we have moved a file in our directory to another file in our directory, this is simply akin to renaming the file.

9.  Finally, we can delete a file.

>   Type: 'rm tmp_listing.txt'
>   Type: 'ls -l'

As expected, the 'tmp_listing.txt' file has been removed.

>   Type: 'rmdir Exercise2Backup'

Uh-oh, yes, I tricked you. Although the rmdir command worked in exercise 1, how in complains that the directory is not empty and can't be removed. we could go through and delete each file in 'Exercise2Backup' one by one, but that is a lot of work if we know that we don't want any of them (it would be even more work if 'Exercise2Backup' contained further sub-directories, with even further files and directories in them. This is where the 'recursive' option comes it.

>   Type: 'rm -r Exercise2Backup'
>   Type: 'ls -l'

Now you will notice that the 'Exercise2Backup' directory has been deleted.
