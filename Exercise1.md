# Exercise 1

For these exercises type the characters in quotes as they are shown below and press the <Return> key after each line.

* Lets understand which directory we are in.

>    Type: 'pwd'

Note the location represents your current directory.

* We will now create a directory specifically for these exercises to keep our work separate from other files on your Raspberry Pi. If you, or someone else, have already done these exercises then this directory may already exist.

>    Type: 'mkdir ~/BashIntroExercises'
>    Type: 'cd ~/BashIntroExercises'
>    Type: 'pwd'

The '~' Character has a special meaning of "My home directory". The above commands first create a new directory directly below your home directory called 'BashIntroExercises'. The next command changes to that directory, finally we confirm that we are in the expected director.  Note how the output from the 'pwd' command differs from the output in step 1.

* We can continue to make further directories and navigate around them as much as we want.

>    Type: 'mkdir newdir'
>    Type: 'cd newdir'
>    Type: 'pwd'
>    Type: 'cd ..'
>    Type: 'pwd'

This time we created a directory called 'newdir', because we went straight for a name it has been created in out current directory, which is 'BashIntroExercises'. Note the effect of the 'cd' commands.  The second 'cd' command used '..', this is another special character seqeuence that means the parent directory to the one we are currently in.

* Now let's try removing (deleting) a directory.

>    Type: 'rmdir newdir'
>    Type: 'cd newdir'
>    Type: 'pwd'

Note that you removed the directory you created in section 2. The attept to change directory failed, after which you are still in the 'BashIntroExercises' directory.

* We can also specify an absolute directory location.

>    Type: 'cd /tmp'
>    Type: 'pwd'

Note that you are now in a completely different location. Directory paths starting with a '/' character refer to an absolute location.

* Now go back to the course directory.

>    Type: 'cd ~/BashIntroExercises'
>    Type: 'pwd'

You are back in the 'BashIntroExercises' directory that you created below your 'home' directory.  

That completes this exercise. You may wish to further experiment with the 'cd', 'mkdir' and 'rmdir' commands to make sure that you inderstand them. If you do, it would be a good idea to repeat section 6. again at the end so that you are back in you home directory.