
 ## Day 12 – Breather & Revision

Introduction
Today was a revision day. I went back through the things I learned from Day 01 to Day 11 instead of starting a new topic.
I revised some basic Linux commands, processes, services, files, permissions, users and groups. I also reran a few commands to check whether I still remembered how to use them.
The main focus today was to refresh the basics and find the topics I need to practice more.

Goal
	• Revise Days 01–11
	• Rerun some important Linux commands
	• Check file permissions and ownership
	• Review users and groups
	• Find the commands I can use quickly

# Revision Practice
1. Process Check
ps
ps aux | head
I used these commands to quickly check the running processes.

2. File Operations
ls -l
mkdir revision-test
touch revision-test/test.txt
echo "Day 12 revision" >> revision-test/test.txt
cat revision-test/test.txt
This helped me revise basic file and directory operations.

3. Permission Practice
chmod 644 revision-test/test.txt
ls -l revision-test/test.txt
I checked the permission changes using ls -l.

5. Ownership Practice
sudo chown ubuntu:ubuntu revision-test/test.txt
ls -l revision-test/test.txt
This was a quick revision of the chown command from Day 11.

6. User Check
id
whoami
I used these commands to check my current user and group information.

# Commands I Want to Remember

The 3 commands that are most useful to me right now:
	1. ls -l – to quickly check files, permissions and ownership.
	2. ps – to check running processes.
	3. id – to check user and group information.

# Mini Self-Check
1. Which 3 commands save me the most time?
ls -l, ps, and id because I can quickly check files, running processes and user information.

2. How do I check if a service is healthy?
First I would use:
systemctl status <service>
journalctl -u <service>
These help me check the service status and its logs.

3. How do I safely change ownership and permissions?
First I check the current settings:
ls -l filename
Then I can make the required change, for example:
sudo chown ubuntu:ubuntu filename
After that I verify again with ls -l.

4. What will I focus on improving?
I want to improve my Linux commands, permissions, process management and troubleshooting so I can use them more confidently.

Key Takeaways
	• Revision helps me remember commands instead of only reading them.
	• ls -l is useful for checking permissions and ownership.
	• ps helps in checking running processes.
	• systemctl and journalctl are useful for service troubleshooting.
	• id helps me check users and groups.



# #90DaysOfDevOps

# #DevOpsKaJosh

# #TrainWithShubham



