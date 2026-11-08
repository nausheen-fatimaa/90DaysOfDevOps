# Day 02 – Linux Architecture, Processes, and systemd 🐧

## 1. Linux Architecture

Linux architecture consists of four major components:

- **Hardware:** Physical components such as CPU, RAM, disk and network devices.
- **Kernel:** The core of Linux. It manages hardware, memory, processes, device drivers and system resources.
- **Shell:** Provides an interface between users and the operating system. Examples: Bash and Zsh.
- **User Space:** The environment where applications, utilities and services run.

### Linux Boot Process

1. BIOS/UEFI initializes hardware.
2. Bootloader (GRUB) loads the Linux kernel.
3. Kernel initializes hardware and memory.
4. Kernel starts the init process (systemd).
5. systemd starts services and targets.
6. The system becomes ready for users.

## 2. Process Management

A process is an instance of a running program. Every process has a unique Process ID (PID).

Linux creates processes using system calls such as `fork()` and `exec()`.

- `fork()` creates a child process.
- `exec()` replaces the current process with a new program.
- `wait()` allows a parent process to collect its child's exit status.

### Process States

| State | Meaning |
|-------|---------|
| R     | Running or runnable |
| S     | Interruptible sleep |
| D     | Uninterruptible sleep |
| T     | Stopped |
| Z     | Zombie process |

**Zombie process:** A process that has completed execution but whose parent has not collected its exit status.

**Orphan process:** A process whose parent has terminated while it is still running.

## 3. What is systemd?

systemd is the init system and service manager used by many modern Linux distributions.

It runs as PID 1 and manages system startup and background services.

### Why systemd matters in DevOps

- Starts and stops services.
- Manages application processes.
- Automatically restarts configured services.
- Controls system startup targets.
- Collects system logs through journald.
- Helps troubleshoot failed services.

### Important systemd Commands

```bash
systemctl status nginx
systemctl start nginx
systemctl stop nginx
systemctl restart nginx
systemctl enable nginx
systemctl disable nginx
```

View service logs:

```bash
journalctl -u nginx
```

## 4. Five Linux Commands I Will Use Daily

| Command | Purpose |
|---|---|
| `ps aux` | View running processes |
| `top` | Monitor CPU and memory usage |
| `free -h` | Check memory utilization |
| `df -h` | Check disk space |
| `systemctl status` | Check service status |

## 5. Practical Troubleshooting

**Scenario 1: High CPU utilization**

```bash
top
ps aux --sort=-%cpu | head
```

Identify the process consuming excessive CPU and investigate it before taking action.

**Scenario 2: Service is not running**

```bash
systemctl status nginx
journalctl -u nginx -n 50
```

Check service status and logs to identify the issue.

**Scenario 3: Disk space is full**

```bash
df -h
du -sh /var/log/*
```

Identify directories consuming excessive disk space.

## 6. Key Takeaways

- The kernel manages hardware and system resources.
- Processes represent running programs.
- Understanding process states helps diagnose system issues.
- systemd manages services and system startup.
- Linux commands and logs are essential for DevOps troubleshooting.

**Day 02 Complete – Understanding Linux Internals! 🚀**