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
   (Run 1) using https://github.com/ucsd-cse15l-f22/list-methods-lab3 :
   
   ![run1](https://user-images.githubusercontent.com/114322700/204165593-23ddd3d5-38f1-4547-8520-b08b62f8a79b.png)
   
   Here, it compiled successfully but failed the tests, and the grade given was 50%.
   
   (Run 2) using https://github.com/ucsd-cse15l-f22/list-methods-corrected :
   
   ![run2](https://user-images.githubusercontent.com/114322700/204165701-bfa84f0b-6480-4975-b733-93e63d392f9c.png)
   
   Here, it compiled successfully and passed all the tests, and the grade given was 100%.
   
   (Run 3) using https://github.com/ucsd-cse15l-f22/list-methods-compile-error :
   
   ![run3](https://user-images.githubusercontent.com/114322700/204165773-b8405b1e-b7d9-4f5d-9274-1a4dd95674ae.png)

   Here, there was a compilation error, so a compilation error output and a grade of 0% was given.
   
   ## Tracing the script:
   We will take the examples in the first screenshot of run 1. In this example of the test the if statement always runs because the exit code is always 0. And in the      code, the If statement always runs as long as the exit code is 0. So the condition of every if statement in this case is always true because the exit code is always    0. The first thing that happened was that the student-submission directory was deleted and replaced with new contents based on what is present in the github link.      If the cloning was successful a 0 exit code will be returned which indicates that it was cloned successfully, then echoes cloned successfully to show it. Otherwise,    it   will automatically go to the else statement which gives a return 1 and echo clone failed. In this case the clone was successful so the return code was 0. The   next if statement checks if 'ListExamples.java' exists in the directory. If it does, it gives exit code 0 and echoes file found. If it does not, a exit code of 1 is returned and echoes file not found and grade 0%. In this case, the file was found so exit code 0 was returned and we move on to the next if statement. The third if statement tells us whether the file is able to compile. If it is, we are given exit code 0 and echoes compiled successfully or exit code 1 and compile failed, grade 0% file can't be compiled. How the if statement works is that we set the path of javac to something outside of student submission, then we use javac to check if the file is able to compile, if the file is not able to compile the grade is assigned to 0% and we give out the compilation error message using cat. In this case the file was able to compile and the exit code returned was 0, so we move on to the next if statement. The last if statement checks for correctness of file content by checking if the contents matches the conditions for the expected test result, if it is, a 100% grade is given for passing all the if statements and exit code 0. If not, a grade of 50% is given for passing all the if statements except for the one in charge of checking for correctness and exit code 1 is returned.
   
