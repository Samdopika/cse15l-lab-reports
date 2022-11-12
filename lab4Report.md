**Part I**
---

**Changing the name of the ```start``` parameter and its uses to ```base```**
---

**>>We first Open the file with vim ```vim DocSearchServer.java<Enter>```**
---

![image](images\lab4pic1.jpg)


**>>Then we write  ```:%s/<start>/```***
---

![image](images\lab4pic2.jpg)


**>>Then we write  ```<base>/g```***
---

![image](images\lab4pic3.jpg)


**Part II**
---


**Start in Visual Studio Code and make the edit there, then scp the file to the remote server and run it there. Log into a ssh session. Make the edit, exit Vim and run bash test.sh:**

The time to do the first part was about 1 minute and couple of seconds. I did not encounter any issues. 
The time to do the second part was about 35 seconds. I also did not encounter any issues. 

**Which of these two styles would you prefer using if you had to work on a program that you were running remotely, and why?**

I used to prefer to scp my edited files but after using vim it makes more sense to just edit my code in the remote server. Thus, Now if i am trying to edit a code in remote server i simply ssh to the remote server and use vim editor to fix or modify my code. It is a super faster way and also there is less chance to make and error. 


**What about the project or task might factor into your decision one way or another? (If nothing would affect your decision, say so and why!)**

It really depends on the project. If the project requires me to test my program and run it in the remote server, i may decide to still use vim. However, if the project can be easily ran on my computer i would do it in an IDE in my local computer because of the easiness to navigate and also my own excelency in working faster in VS code. Overall, I would probably choose to work with my own IDE and then scp my filess over to the remote server. 