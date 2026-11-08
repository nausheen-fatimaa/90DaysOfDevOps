# Day 03 – Linux Commands Practice 🐧

## 1. Process Management Commands

| Command | Usage |
|---|---|
| `ps aux` | Display all running processes. |
| `top` | Monitor CPU and memory usage in real time. |
| `htop` | Interactive process monitoring (if installed). |
| `pgrep nginx` | Find the PID of a process by name. |
| `kill PID` | Send a termination signal to a process. |
| `kill -9 PID` | Forcefully terminate a process. |
| `nice -n 10 command` | Start a process with a specified priority. |
| `uptime` | Check system uptime and load averages. |

**Practical example:**

Find processes consuming the most CPU:

```bash
ps aux --sort=-%cpu | head -10
```

Find processes consuming the most memory:

```bash
ps aux --sort=-%mem | head -10
```

## 2. File System Commands

| Command | Usage |
|---|---|

| Command | Usage |
|---------|-------|
| `pwd` | Show the current working directory. |
| `ls` | List files and directories. |
| `ls -la` | Display detailed information including hidden files. |
| `cd <directory>` | Change the current directory. |
| `mkdir <name>` | Create a new directory. |
| `rmdir <name>` | Remove an empty directory. |
| `touch <file>` | Create a new empty file. |
| `cp source destination` | Copy files or directories. |
| `mv source destination` | Move or rename files/directories. |
| `rm <file>` | Delete a file. |
| `rm -r <directory>` | Delete a directory and its contents. |
| `cat <file>` | Display file contents. |
| `less <file>` | View large files page by page. |
| `head <file>` | Show the first 10 lines of a file. |
| `tail <file>` | Show the last 10 lines of a file. |
| `find . -name "<file>"` | Search for a file by name. |
| `du -sh /path` | Check directory disk usage. |
| `df -h` | Check available disk space. |
| `chmod 755 file` | Change file permissions. |
| `chown user:group file` | Change file ownership. |
| `cat file.txt` | Display file contents. |
| `grep "error" file.log` | Search for specific text in a file. |

**Practical example:**

Find large files:

```bash
find /var/log -type f -size +100M
```

Check disk utilization:

```bash
df -h
```

## 3. Networking Troubleshooting Commands

| Command | Usage |
|---|---|
| `ip addr` | Display network interfaces and IP addresses. |
| `ip route` | Display the routing table. |
| `ping google.com` | Test network connectivity. |
| `dig google.com` | Troubleshoot DNS resolution. |
| `curl -I https://google.com` | Check HTTP response headers. |
| `ss -tulnp` | Display listening TCP/UDP ports and processes. |
| `traceroute google.com` | Trace the network path to a destination (if installed). |
| `nslookup google.com` | Query DNS information. |
| `hostname -I` | Display assigned IP addresses. |
| `wget URL` | Download files from the internet. |

**Practical examples:**

Check network connectivity:

```bash
ping -c 4 google.com
```

Check IP address:

```bash
ip addr
```

Check DNS resolution:

```bash
dig google.com
```

Check whether port 8080 is listening:

```bash
sudo ss -tulnp | grep ':8080'
```

## 4. Log Monitoring Commands

| Command | Usage |
|---|---|
| `tail -f file.log` | Monitor log files continuously. |
| `tail -n 50 file.log` | Display the last 50 lines. |
| `journalctl -xe` | View recent system journal messages. |
| `journalctl -u nginx` | View logs for the Nginx service. |
| `grep -i error file.log` | Search for errors without case sensitivity. |

**Practical example:**

Monitor Nginx logs:

```bash
sudo tail -f /var/log/nginx/error.log
```

Search for errors:

```bash
sudo journalctl -u nginx | grep -i error
```
## 5. 💾 System Information

| Command | Description |
|---------|-------------|
| `hostname` | Display the system hostname. |
| `uname -a` | Show kernel and OS details. |
| `uptime` | Display system uptime and load. |
| `free -h` | Show memory usage. |
| `lscpu` | Display CPU information. |
| `lsblk` | List block devices. |
| `whoami` | Display the current user. |
| `id` | Show user and group IDs. |

## 6. Real-World DevOps Troubleshooting Scenarios

### Scenario 1: High CPU utilization

```bash
top
ps aux --sort=-%cpu | head
```

Identify the process consuming excessive CPU and investigate it.

### Scenario 2: Disk space is full

```bash
df -h
du -sh /var/log/*
```

Identify directories consuming excessive disk space.

### Scenario 3: Application is not accessible

```bash
ip addr
ping -c 4 google.com
ss -tulnp
curl -I http://localhost:8080
```

Check network configuration, connectivity, listening ports and application response.

### Scenario 4: Application service is failing

```bash
systemctl status nginx
journalctl -u nginx -n 50
```

Inspect service status and recent logs to identify the problem.

## 7. Key Takeaways

- Process management commands help identify resource-consuming applications.
- File system commands help manage files, permissions and disk space.
- Networking commands help troubleshoot connectivity, DNS and ports.
- Log monitoring helps identify application and system failures.
- Regular command-line practice improves troubleshooting confidence.

**Day 03 Complete – Practising Linux Like a DevOps Engineer! 🚀**