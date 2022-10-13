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
ssh cs15lfa22<yourGivenInitials>@ieng6.ucsd.edu
```
* note: The password won't be visible to you.
3. After putting the password in, your cmd would look like the screenshot. 

**Trying Some Commands**
---
![image](images/Picture3.jpg)
1. So in this part we run some commands in both Our own computer and the server. The screenshot is an example of running the commands in the server computer. 
2. You may also run the commands in your own computer to compare how your system would run the commands dfferently. 
3. The expected diffrence that you may face is that the commands will run depending on the files you have in the host system. 
In the attached screenshot, I have used the following commands. and you can see what each of them do:
* **cd** : The cd command, also known as chdir (change directory), is a command-line shell command used to change the current working directory in various operating systems ([Wikipedia](https://en.wikipedia.org/wiki/Cd_(command)#:~:text=The%20cd%20command%2C%20also%20known,directory%20in%20various%20operating%20systems.)).
* **ls** : The ls command is used to list files. "ls" on its own lists all files in the current directory except for hidden files ([Cambridge](https://www.maths.cam.ac.uk/computing/linux/unixinfo/ls#:~:text=The%20ls%20command%20is%20used,directory%20except%20for%20hidden%20files.)).
* **cd** : The pwd command writes to standard output the full path name of your current directory ([IBM](https://www.ibm.com/docs/en/aix/7.1?topic=p-pwd-command)).


**Moving Files with scp**
---
![image](images/Picture4.jpg)
1. The command that we use to move a file form either our own computer to the server or from the server to our own computer is called **secure copy (SCP)**. 
2. So in the last lines of my screenshot you can see that i tried to move the WhereAmI.java file from the server to my own computer. 
```
C:\users\samkh>scp cs15lfa22ta1@ieng6.ucsd.edu:~/WhereAmI.java WhereAmI.java
Password:
WhereAmI.java
```

3. Then to test and make sure your file has been moved, you can cd the folder you moved your file to. 

**Setting an SSH Key**
---
![image](images/Picture5.jpg)
1. First on your own computer run 'ssh-keygen' then in the line that starts with "Enter file in which ..." rnter your default path.
2. Then sign in normally (ssh your account and enter your password)
3. On your remote server run command 'mkdir .ssh' and you can log out or open another command.
4. the run the following command:
```
scp /users/your pc user/.ssh/id_rsa.pub cs15lfa22<yourGivenInitials>@ieng6.ucsd.edu:~/.ssh/authorized_keys
```
5. You're result should look like something like the attached screenshot.

**Optimizing Remote Running**
---
![image](images/Picture6.jpg)

1. the screenshot shows when you have you're all set up you you don't need to put your password anymore.
2. To extend your optimization you can try to change your WhereAmI.java in your PC. 
3. Then to transfer the file to your remote server you can use the following command:
```
scp WhereAmI.java cs15lfa22<yourGivenInitials>@ieng6.ucsd.edu:~/
```
* In following:
4. You may run the following command to access to your remote server:
```
ssh cs15lfa22<yourGivenInitials>@ieng6.ucsd.edu
```
* **note that if you've set up your key correctly you won't need to put your password in**

5. To make a class of WhereAmI.java and then call the class, you runned code will look like the following code snap:
```
[cs15lfajavac<yourGivenInitials>@ieng6-203]:~:234$ WhereAmI.java
*// Then run the java clas
[cs15lfajavac<yourGivenInitials>@ieng6-203]:~:235$ java WhereAmI 
cs15lfajavac<yourGivenInitials>
/home/linux/ieng6/cs15lfa22/cs15lfajavac<yourGivenInitials>
/home/linux/ieng6/cs15lfa22/cs15lfajavac<yourGivenInitials>
Linux
```

samans