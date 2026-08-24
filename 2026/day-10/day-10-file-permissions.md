# Day 10 – File Permissions & File Operations Challenge

## Task

Today I practiced basic Linux file operations and file permissions.

In this practice I worked with:

* Creating files
* Reading files
* Checking file permissions
* Changing permissions using chmod
* Creating a directory
* Testing permission errors

---

## . Create Files

First I created an empty file using touch


touch devops.txt


Then I created notes.txt and added some content.


echo "I am learning Linux file permissions" > notes.txt


I created script.sh using Vim.


vim script.sh


I added this line inside the file:


echo "Hello DevOps"


Then I checked the files:


ls -l


### Files created


devops.txt
notes.txt
script.sh
screenshots/




## . Read Files

I used cat to read notes.txt.

cat notes.txt


Output:


I am learning Linux file permissions


I also checked the content of script.sh.


cat script.sh


Output:


echo "Hello DevOps"


For practicing head and tail, I checked /etc/passwd.


head -n 5 /etc/passwd



tail -n 5 /etc/passwd

This helped me understand how to view the beginning and end of a file.



## . Check File Permissions

I checked the permissions using:


ls -l devops.txt notes.txt script.sh

Initially the files had permissions like:


-rw-rw-r--


The permissions are divided into:


owner | group | others




r = read
w = write
x = execute



## . Change Permissions

### Make `script.sh` executable

I added execute permission:

chmod +x script.sh

Then checked it:


ls -l script.sh


After that I ran the script:


./script.sh


Output:


Hello DevOps


So the script was running successfully.




## . Final Files


devops.txt
notes.txt
project/
screenshots/
script.sh


I checked the directory using:


ls -l


And checked the project directory using:


ls -ld project


## What I Learned

1. touch can be used to create an empty file.
2. cat, head and tail can be used to read file content.
3. chmod is used to change file and directory permissions.
4. r, w and x represent read, write and execute permissions.
5. 640 gives the owner read/write permission and the group read permission.
6. 755 is commonly used for directories.
7. A file needs execute permission to run it directly using ./script.sh.
8. Removing write or execute permission can result in Permission denied.



## Commands Practiced


touch
echo
vim
cat
head
tail
ls -l
ls -ld

chmod

mkdir

./script.sh


#90DaysOfDevOps
#DevOpsKaJosh
#TrainWithShubham
