# Exercise 5

For these exercises type the characters in quotes as they are shown below and press the <Return> key after each line. This exercise assumes that you have successfully completed exercises 1 to 3, which created a directory for all of the work called 'BashIntroExercises' in you home directory containing several files.  

Steps 2. onwards of this exercise assumes that you have networking setup and are able to communicate over the Internet. If you only have local networking, your teacher should provide some local network computers that you can use instead of those specified.

1. Lets see what network interfaces our Raspberry Pi has. Enter the following command:
    
    > ifconfig
    
    You will be presented with a list of information sub-divided into a section for each "interface". The most useful parts of this output are the "INTERFACE UP" which indicates that the network interface is active, and the "inet addr:" which shows the "IP Address" that has been assigned to the interface. The the interface is down, or there is no IP Address assigned then the Raspberry Pi will not be able to communicate over this interface. You should have one or more of the following network interfaces available:  
    
    * eth0 - The is a "Ethernet" interface, this will be listed if you have a Model B Raspberry Pi with a "wired" network interface.
    * wlan0 - This is a "Wireless" interface, this will be listed if you have a Wireless Network dongle attached to your Raspberry Pi.The user who is running the process.
    * lo - This is a "Loopback" interface. It represents a local network connection. We will see that networking is integral to the operation of the Raspberry Pi, this "interface" provides the means for processes that are running to communicate with each other as if they are using a network interface. Notice that this interface always has the IP Address of "127.0.0.1".
    * There may be other interfaces list, but they are beyond the scope of this course.
       
2. The most basic network check that we can do to check if we can communicate with another computer. Then the following command:

    > ping www.bbc.co.uk

    This sends an "echo" to the remote computer (in this case "www.bbc.co.uk") and awaits a response. If a response is received then details of how long it took is provided. You will note that this command keeps sending further "echo"s to the remote computer. You will need to press "Ctrl"-C to stop the ping command running (you learnt how to do this in the previous lesson).
    
3. Now lets see what happens when we try to communicate with a computer that does not exist. Enter the following command:

    > ping abc.def.ghi.jkl
    
    There will be a short delay and then you will be told that the host you specified is unknown. Notice that this is subtly different from being told that the host is known, but is not responding to our "echo" requests, in this case you will be told that a "Timeout" occurred.  
    
    If we believe that this computer should exist (perhaps because it is a well known name), but we are given the same message that we see above, then we should report that we are having "DNS" problems to our network administrator.
    
4. If we are unable to communicate with another computer that we know is there, and we are not seeing the "Host Unknown" message seen above, then we can examine the route that our network communication tasks when we communicate to another computer, Enter the following command:

    > traceroute google.co.uk

    This command will gradually reveal the each step between out Raspberry Pi and the remote computer. It is worth being familiar with the first few steps which are through your local network, out through your Internet provider. Then, if there is a problem with one of these steps you should be able to contact whoever is responsible for that part of the network.  
    
    When all is well you will see timing details for each step. This will help you to diagnose slow connections. You may see a series of '*' instead of the times. This indicates that a router along the way has been told not to respond to "echo" requests, this is a typical policy for some routers and should be accepted as normal.  

    How many of the initial steps are you able to identify ?
    Can you see who provides your Internet service ?
        
----
That completes this exercise. You may wish to further experiment with the 'ifconfig', 'ping' and 'traceroute' commands to make sure that you understand them.
