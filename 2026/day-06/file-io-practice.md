Day 06 – Linux Fundamentals: Read and Write Text Files

Introduction

Today I practiced basic file handling commands in Linux. The goal was to understand how to create a text file.
Write data into it, append new content, and read the file using different Linux commands. 
These commands are simple but very useful while working with configuration files, logs, and scripts.

- OS: Ubuntu Linux
- Shell: Bash
- File Name: notes.txt

Commands Executed
Create a new file

touch notes.txt


Add text to the file

echo "Linux is a powerful operating system." > notes.txt


Append more lines

echo "Learning file handling commands." >> notes.txt
echo "Practicing Linux every day." >> notes.txt

Append using tee

echo "This line was added using tee." | tee -a notes.txt

Read the file

cat notes.txt


Display first two lines

head -n 2 notes.txt


Display last two lines

tail -n 2 notes.txt


File Content
text

Linux is a powerful operating system.
Learning file handling commands.
Practicing Linux every day.
This line was added using tee.

 Observations
 
- touch creates an empty file.
- writes new data and replaces existing content.
- Adds new data without deleting previous content.
- tee -a displays the output on the terminal and also appends it to the file.
- cat, head, and tail are useful for checking file contents.


 Challenges
 
I did not face any issues while performing this practice. All commands worked as expected.

 Key Takeaways
 
- Learned how to create and manage text files in Linux.
- Understood the difference between > and >>.
- Practiced reading files using multiple commands.
- Gained confidence in performing basic file operations from the terminal.

Conclusion

This practice improved my understanding of Linux file handling.
These basic commands are commonly used while working with log files, configuration files, and shell scripts, making them an important part of everyday DevOps tasks.


