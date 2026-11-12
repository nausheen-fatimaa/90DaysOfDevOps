# Day 04 – Linux Practice: Processes and Services 🐧

## 1. Objective

Practise Linux process management, systemd service inspection and log monitoring using Ubuntu.

## 2. Process Checks

### Command 1: View Running Processes

```bash
ps aux
```
**Purpose:** Displays currently running processes, including their PID, CPU and memory usage.

ps-aux.png

### Command 2: Monitor System Processes

```bash
top
```
**Purpose:** Displays real-time process activity and system resource utilization.

top.png

### Command 3: Find a Specific Process

```bash
pgrep -a systemd
```
**Purpose:** Finds the PID and command line of matching processes.

image-2.png

## 3. Service Checks

Service selected: SSH

### Command 4: Check SSH Service Status

```bash
sudo systemctl status ssh --no-pager
```
**Purpose:** Checks whether the ssh service is running or stopped.

image-3.png

### Command 5: List Active Services

```bash
systemctl list-units --type=service --state=running
```

**Purpose:** Displays currently running systemd services.

image-4.png

## 4. Log Checks

### Command 6: Check SSH Service Logs

```bash
sudo journalctl -u ssh -n 20 --no-pager
```

**Purpose:** Displays the latest 20 log entries for SSH.

image-5.png

### Command 7: Check Recent System Logs

```bash
sudo journalctl -n 30 --no-pager
```

**Purpose:** Displays recent system journal messages.

image-6.png

## 5. Mini Troubleshooting Exercise

**Scenario:** Docker service is not working.

Step 1: Check service status.

```bash
sudo systemctl status docker
```
image-7.png

Step 2: Investigate service logs.

```bash
sudo journalctl -u docker -n 50 --no-pager
```
image-8.png

Step 3: If the service is stopped and the cause is understood, attempt to start it.

```bash
sudo systemctl start docker
```

Step 4: Verify the service.

```bash
sudo systemctl status docker
```
image-9.png

**Troubleshooting Result:**

- Problem identified: Docker service is not working.
- Root cause: The service is stopped.
- Solution applied: Started it.
- Final status: Running.

## 6. Key Learnings

- Learned how to inspect running Linux processes.
- Practised checking systemd service status.
- Explored system logs using journalctl.
- Understood the basic troubleshooting workflow.
- Improved confidence in Linux command-line operations.

**Day 04 Complete – Learning Linux Through Practical Implementation! 🚀**