**Grade.sh Bash File**


```
set -e
rm -rf student-submission
mkdir student-submission

git clone $1 student-submission
cp TestListExamples.java student-submission
cd student-submission

CPATH=.:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar

if [[ -f ListExamples.java ]];
then
    echo "Your file is found!"
else
    echo "The File was not FOUND"
    echo "You Recieved 0/2 Credit! You Absolutly Messed Up"
    exit 1
fi

set +e

javac -cp $CPATH *.java > errorCompile.txt

if [[ $? -eq 0 ]]
then
    echo "Your code Compiled!"
else
    echo "Your Code didn't Even Compile!"
    echo "You Recieved 0.5/2 Credit! You Literally Messed Up!"
    cat errorCompile.txt
    exit 2
fi

java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > test-err.txt

if [[ $? -eq 0 ]]
then 
    echo "All tests Passed Legend"
    echo "You Recieved 2/2 Credit! GOOD JOBBBBB, You're a true LEGEND"
    exit
else
    echo "Your Test Unfortunatly Failed"
    echo "You Recieved 1/2 Credit"
    cat test-err.txt
    exit 3
fi
```

[The first Example (**1**)](https://github.com/ucsd-cse15l-f22/list-methods-lab3)
---
Link to the Repo: https://github.com/ucsd-cse15l-f22/list-methods-lab3 

![image](Lab5\example1.jpg)

[The Second Example (**2**)](https://github.com/ucsd-cse15l-f22/list-methods-corrected)
---
Link to the Repo: https://github.com/ucsd-cse15l-f22/list-methods-corrected  

![image](Lab5\example2.jpg)


[The Third Example (**3**)](https://github.com/ucsd-cse15l-f22/list-methods-compile-error)
---
Link to the Repo: https://github.com/ucsd-cse15l-f22/list-methods-compile-error

![image](Lab5\example3.jpg)


**The Trace of Script**
---
I will trace [The Second Example (**2**)](https://github.com/ucsd-cse15l-f22/list-methods-corrected) Since it involves the whole bash file. 

1. ```set -e``` :
    - *standard output* and *standard error* are ```None``` for this run.
    - The return Code : ```Zero```

2. ```rm -rf student-submission```:
    -  *standard output*:
    
    ```
    removed 'student-submission/.git/config'
    removed 'student-submission/.git/description'
    removed 'student-submission/.git/HEAD'
    removed 'student-submission/.git/hooks/applypatch-msg.sample'

    .
    .
    .
    .
    .
    removed directory 'student-submission/lib'
    removed 'student-submission/ListExamples.java'
    removed 'student-submission/TestListExamples.java'
    removed directory 'student-submission'
    ```
    
    - *standard error* is ```None``` for this run.
    - The return Code : ```Zero```



3. ```mkdir student-submission```
    - *standard output* and *standard error* are ```None``` for this run.
    - The return Code : ```Zero```



4. ```git clone $1 student-submission```
    - *standard output* ```None``` for this run.
    - and *standard error* is ```cloning into 'student-submission'...```
    - The return Code : ```Zero```



5. ```cp TestListExamples.java student-submission```
    - *standard output* is ```TestListExamples.java' -> 'student-submission/TestListExamples.java``` for this run.
    - and *standard error* is ```None```
    - The return Code : ```Zero```

6. ```cd student-submission```
    - *standard output* is ```'lib' -> 'student-submission/lib'
    'lib/junit-4.13.2.jar' -> 'student-submission/lib/junit-4.13.2.jar...``` for this run.
    - and *standard error* is ```None```
    - The return Code : ```Zero```


7. ```if [[ -f ListExamples.java ]];``` Is True since the file exists and is found.

8. ```set +e```
    - *standard output* and *standard error* are ```None``` for this run.
    - The return Code : ```Zero```


9. ```if [[ $? -eq 0 ]]``` Is True Since ```javac -cp $CPATH *.java > errorCompile.txt``` results in exit code 0. Which shows the code compiles successfully. 



10. ```if [[ $? -eq 0 ]]``` Is True Since ```java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > test-err.txt``` Results in exit code 0. 