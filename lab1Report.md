**lab 1**
============

**VS Code Installation**
---
![image](images/Picture1.jpg)
1. I installed VS Code a while ago and i didn't need to go through the steps to install it.
2. In order to install VS Code we can use this [website](https://code.visualstudio.com/).
3. My screenshot is illustrating the initial page of VS Code. 

**Remotely Connecting**
---
![image](images/Picture2.jpg)
1. Because my account didn't work I used one of the TA accounts that they offered in the Lab.  
2. For running the remote account we have to use the secure shell command which is ssh:
```
$ ssh cs15lfa22ta1@ieng6.ucsd.edu
```
* note: The password won't be visible to you.
3. After putting the password in, your cmd would look like the screenshot. 

**Trying Some Commands**
---
![image](images/Picture3.jpg)
1. So in this part we run some commands in both Our own computer and the server. The screenshot is an example of running the commands in the server computer. 
2. You may also run the commands in your own computer to compare how your system would run the commands dfferently. 
3. The expected diffrence that you may face is that the commands will run depending on the files you have in the host system. 

**Moving Files with scp**
---
![image](images/Picture4.jpg)
1. The command that we use to move a file form either our own computer to the server or from the server to our own computer is called **secure copy (SCP)**. 
2. So in the last lines of my screenshot you can see that i tried to move the WhereAmI.java file from the server to my own computer. 
3. Then to test and make sure your file has been moved, you can cd the folder you moved your file to. 

**Setting an SSH Key**
---
![image](images/Picture5.jpg)

**Optimizing Remote Running**
---
![image](images/Picture6.jpg)