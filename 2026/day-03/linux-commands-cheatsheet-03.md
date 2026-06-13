
🧠 Process Management
	 
.ps aux → show all running processes
	
.ps -ef → process list with parent IDs
	
.top → live CPU and memory usage
	
.htop → better version of top
	
.uptime → system running time and load
	
.free -m → check memory usage
	
.kill PID → stop a process gracefully
	
.kill -9 PID → force kill processes

📁 File System

Command	      Usage
	
cd	 -> 	Change the directory

ls	 -> 	List all files and folders

touch ->	Create a new empty file

rm	->	Remove a file

mv	->	Move or rename a file

cat	->	Display the contents of a file

nano	-> Open a file to write or edit text

grep ->	Search for a pattern inside a file or log

wc -l	 -> Count the number of lines in a file

df	->	Show available disk space on the system

chmod +x <file>  ->	Make a file executable before running it

man	->	Open the manual/help page for any command

*Networking Troubleshooting

ping google.com - Check network connectivity.

ip addr - Display IP address information.

curl https://google.com - Test website response.

dig google.com - DNS lookup.

ss -tulpn - Show listening ports.

hostnamectl - Display hostname and OS information.
	
*System Monitoring

free -h - Show memory usage.

uptime - Display system uptime.

df -h | awk 'NR==2 {print $5}' - Show disk usage percentage.

free -h | awk 'NR==2 {print $3}' - Show used memory.	
	
