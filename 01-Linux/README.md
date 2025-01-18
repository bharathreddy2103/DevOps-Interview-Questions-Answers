1. What is Linux, and why is it important in DevOps?
Linux is an open-source operating system widely used for server environments due to its stability, scalability, and security. Most DevOps tools (Docker, Kubernetes, Jenkins, etc.) run on Linux, making it essential for DevOps Engineers.

2. How do you check the current working directory in Linux?

  Command: pwd

  It prints the full path of the current directory.

3. What are the different types of file permissions in Linux?

   Read (r): Allows viewing the contents of a file.

   Write (w): Allows modifying the file.

   xecute (x): Allows running the file as a program.

4. What is the difference between cp and mv?

   cp: Copies files/directories.

   mv: Moves or renames files/directories.

5. What is the purpose of the grep command?

   Used to search for specific patterns in files.

   Example: grep "error" /var/log/syslog (Searches for "error" in the syslog file).

6. How do you check the uptime of a Linux system?

  Command: uptime

  It shows how long the system has been running, the number of users, and the load averages.

7. How do you manage systemd services in Linux?

   Start a service: systemctl start service_name

   Stop a service: systemctl stop service_name

   Enable a service at boot: systemctl enable service_name

8. What is the purpose of the top and htop commands?

   top: Displays real-time system resource usage (CPU, memory, processes).

   htop: A more user-friendly version of top with color coding and additional features.

9. How do you troubleshoot high CPU usage in Linux?

   Use top or htop to identify resource-hungry processes.

   Check logs for any abnormal activity: journalctl, /var/log/syslog.

   Optimize or kill the offending process using kill -9 PID.

10. Explain iptables and its use in Linux.

   iptables is a command-line tool to configure the Linux kernel firewall.

   Example:

  Allow SSH traffic: iptables -A INPUT -p tcp --dport 22 -j ACCEPT

  Drop all other traffic: iptables -P INPUT DROP

11. What are hard links and soft links?

    Hard Link: Points directly to the inode of a file. Deleting the original file does not affect the hard link.

    Soft Link (Symbolic): Points to the file path. If the original file is deleted, the soft link becomes invalid.

    Create a hard link: ln file1 file2

    Create a soft link: ln -s file1 file2

12. What are some common cron job scheduling expressions?

    Cron syntax: * * * * * command_to_execute

   Minute (0-59)

  Hour (0-23)

  Day of Month (1-31)

  Month (1-12)

  Day of Week (0-6)


Example:

Run a script daily at 2 AM: 0 2 * * * /path/to/script.sh

13. Scenario: A server is running out of disk space. How do you troubleshoot and free up space?
Steps:

Check disk usage: df -h.

Identify large files: du -sh /path/* | sort -rh.

Clear unnecessary logs: > /var/log/large_log_file.

Delete unused files or directories: rm -rf /path/to/file.

14. Scenario: A website is down, but the service is running. What steps would you take?
Steps:

Check if the service is listening on the correct port: netstat -tuln.

Verify firewall rules: iptables -L or ufw status.

Check DNS resolution: nslookup domain_name.

Inspect logs for errors: /var/log/nginx/error.log.

15. Scenario: You can't SSH into a remote server. What could be the issue?
Steps:

Verify network connectivity: ping remote_server.

Ensure the SSH service is running: systemctl status sshd.

Check firewall rules: iptables -L.

Confirm correct SSH credentials and permissions for .ssh/authorized_keys.

16. Scenario: A process is unresponsive. How do you handle it?
Steps:

Identify the process using top or ps aux.

Kill the process: kill -9 PID.

Check logs for the cause of unresponsiveness.

17. Scenario: How do you recover a root password on a Linux system?
Steps:

Boot into single-user mode.

Edit the boot loader (GRUB) and add init=/bin/bash.

Remount the root filesystem: mount -o remount,rw /.

Change the password: passwd root.

Reboot the system.

18. Scenario: High memory usage is affecting system performance. What steps would you take?
Steps:

Identify memory-hogging processes: ps aux --sort=-%mem.

Clear cached memory: echo 3 > /proc/sys/vm/drop_caches.

Check swap usage: swapon -s.

Add swap if necessary.
