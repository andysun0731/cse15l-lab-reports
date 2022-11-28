# Lab Report Week 9
## grade.sh 
```
# Create your grading script here
set -e
rm -rf student-submission
git clone $1 student-submission
cp TestListExamples.java student-submission
cp lib/hamcrest-core-1.3.jar student-submission
cp lib/junit-4.13.2.jar student-submission
echo "Successfully cloned"
cd student-submission

if [[ -f ListExamples.java ]]
then 
    echo "ListExamples found"
else 
    echo "ListExamples not found 0/2" 
    exit 
fi

cp ListExamples.java ..

cd ..

set +e
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
if [[ $? -ne 0 ]]
then
    echo "Compiler Error!"
    exit
fi

java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples

if [[ $? -ne 0 ]]
then
    echo "Fail"
    exit  
else
    echo "Pass All Tests"
    exit
```
* FUll CREDIT: 
<img width="1464" alt="截屏2022-11-27 下午5 18 32" src="https://user-images.githubusercontent.com/114369562/204172118-46469543-9bbf-4dbd-8a4d-e5f037e38a94.png">

* COMPILE ERROR:
<img width="1454" alt="截屏2022-11-27 下午5 21 32" src="https://user-images.githubusercontent.com/114369562/204172380-e1c8b5f8-4b89-4d89-9bc0-b6fb71a7867b.png">

* FILE NOT FOUND
<img width="1460" alt="截屏2022-11-27 下午5 22 15" src="https://user-images.githubusercontent.com/114369562/204172433-700b1aa8-ac4d-435d-8122-85e73f4cb17f.png">

* Trace the path of file not found:

Command: `set -e`, Standard Output: N/A, Standard Error: 0

Command: `rm -rf student-submission`, Standard Output: N/A, Code: 0 

Command: `git clone $1 student-submission`, Standard Output: N/A, Code: 0 

Command: `cp TestListExamples.java student-submission`, Standard Output: N/A, Code: 0 

Command: `cp lib/hamcrest-core-1.3.jar student-submission`, Standard Output: N/A, Code: 0 

Command: `cp lib/junit-4.13.2.jar student-submission`, Standard Output: N/A, Code: 0 

Command: `echo "Successfully cloned"`, Standard Output: `Successfully cloned`, Code: 0

Command: `cd student-submission`, Standard Output: N/A, Code: 0 

Command: `if [[ -f ListExamples.java ]]`, Standard Output: N/A, Code: 0

Command: `else`, Standard Output: N/A, Code: 0

Command: `echo "ListExamples not found 0/2"`, Standard Output: `ListExamples not found 0/2`, Code: 0

Command: `exit`, Standard Output: N/A, Code: 1

In the if statement, we are checking if the file ListExamples.java exist or not, in this scenario, the file ListExamples.java doesn't exsit, so we are skipping the then statement (which is line 12 and 13) and run the else statement, in the else statement we are using echo to make a standard output to mention that we haven't found this file and exit early therefore we are not running the rest of the codes.





