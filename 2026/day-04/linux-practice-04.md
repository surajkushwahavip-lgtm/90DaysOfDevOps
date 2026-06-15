		 
1. ps aux | head

   Output :-> 
	    USER   PID %CPU %MEM VSZ RSS TTY STAT START TIME COMMAND
	    root     1 0.1 0.6 22112 13344 ? Ss 11:06 0:01 /sbin/init
	    root     2 0.0 0.0 0 0 ? S 11:06 0:00 [kthreadd]
	    root     3 0.0 0.0 0 0 ? S 11:06 0:00 [pool_workqueue_release]


   
	 
3. Find systemd Processes
	pgrep systemd

	Output : ->

	 1

    308

    356

    458

    606
	
    1152

    1177 

      Service Checks
	 
3. Check SSH Service Status
	  systemctl status ssh
   
    Output:

   ssh.service - OpenBSD Secure Shell server

   Loaded: loaded

    Active: active (running)

    Main PID: 1181 (sshd)

4. List Running Services

    systemctl list-units --type=service --state=running
    			
    Observed Services:
    containerd.service
    			
    cron.service
    dbus.service
    			
    docker.service
    
    ssh.service
    systemd-journald.service
  
    systemd-networkd.service
    
    systemd-resolved.service
    systemd-timesyncd.service
    Log Checks

6. View SSH Logs
			journalctl -u ssh --no-pager
			Sample Output:


   Starting ssh.service - OpenBSD Secure Shell server...
			Started ssh.service - OpenBSD Secure Shell server.
			Accepted password for kc-internal
			Received disconnect from user  
			             6. View Recent System Logs
			journalctl -xe -n 10
			Sample Output:

   Finished phpsessionclean.service
			Starting sysstat-collect.service
			sysstat-collect.service: Deactivated successfully
			Finished sysstat-collect.service
			Mini Troubleshooting Steps
			Service Inspected
			SSH Service (ssh.service)
			Issue Investigation
			Checked SSH service status:
			systemctl status ssh
			Verified that the service was active and running.
			Examined SSH logs:
			journalctl -u ssh --no-pager
			Observed successful login events and service startup messages.
			Checked recent system logs:
			journalctl -xe -n 10
			Result
			SSH service was running successfully.
            No critical errors were found in the logs.
			Service health was normal.
			Commands Practiced
			ps aux | head
			pgrep systemd
			systemctl status ssh
			systemctl list-units --type=service --state=running
			journalctl -u ssh --no-pager
			journalctl -xe -n 10
			What I Learned
			Today I practiced Linux process monitoring, service management, and log inspection. I learned how to identify running processes, inspect systemd services, analyze service logs, and perform basic troubleshooting using Linux commands.
