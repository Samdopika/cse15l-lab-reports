**Grade.sh Bash File**


```
set -e
rm -rd student-submission
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

![image](Lab5\example1.jpg)

[The first Example (**2**)](https://github.com/ucsd-cse15l-f22/list-methods-corrected)
---

![image](Lab5\example2.jpg)


[The first Example (**3**)](https://github.com/ucsd-cse15l-f22/list-methods-compile-error)
---

![image](Lab5\example3.jpg)


**The Trace of Script**
