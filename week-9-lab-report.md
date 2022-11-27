# Lab Report 5
## code for the grade.sh:
```
    FILE='ListExamples.java'
    rm -rf student-submission
    git clone $1 student-submission

    if [[ $? -eq 0 ]]
    then
        echo "[PASSED] Cloned successfully."
    else
        echo "[FAILED] Clone failed. Check the submit URL."
        exit 1
    fi

    cd student-submission
    if [[ -f $FILE ]]
    then 
        echo "[PASSED] File found."
    else
        echo "[FAILED] File not found."
        echo "Grade: 0% [File wasn't even there]."
        exit 1
    fi  

    CP=".:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar"
    cp ../TestListExamples.java .


    javac -cp $CP *.java 2> comp-err.txt
    if [[ $? -eq 0 ]]
    then
        echo "[PASSED] Compiled successfully."
    else
        echo "[FAILED] Compile Failed."
        cat comp-err.txt
        echo "Grade: 0% [File can't be compiled]."
        exit 1
    fi

    java -cp $CP org.junit.runner.JUnitCore TestListExamples > test-result.txt
    if [[ $? -eq 0 ]]
    then
        echo "[PASSED] JUnit Result:"
        echo test-result.txt
        echo "Grade: 100%"
    else
        echo "[FAILED] JUnit result: "
        cat test-result.txt
        echo "Grade: 50%, file compiled successfully but failed the test."
        exit 1
    fi
   ```
   # Screenshots of three different student submissions and the reported grade using list methods files from lab 3:
   (Run 1) expected test failure using https://github.com/ucsd-cse15l-f22/list-methods-lab3 :
   
   ![run1](https://user-images.githubusercontent.com/114322700/204165593-23ddd3d5-38f1-4547-8520-b08b62f8a79b.png)
   
   (Run 2) expected test success using https://github.com/ucsd-cse15l-f22/list-methods-corrected :
   
   ![run2](https://user-images.githubusercontent.com/114322700/204165701-bfa84f0b-6480-4975-b733-93e63d392f9c.png)
   
   (Run 3) expected file compilation error using https://github.com/ucsd-cse15l-f22/list-methods-compile-error :
   
   ![run3](https://user-images.githubusercontent.com/114322700/204165773-b8405b1e-b7d9-4f5d-9274-1a4dd95674ae.png)


   
   
