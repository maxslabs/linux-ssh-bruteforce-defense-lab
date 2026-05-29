# Debian Linux Admin Lab - Setup Log

This document tracks every step taken to build and configure a Debian Linux virtual machine for system administration practice.

---

## Step 1: Virtual Machine Setup
- Created Debian VM using VirtualBox
- Allocated resources (CPU, RAM, disk)
- Installed Debian 13

---

## Step 2: Initial Login
- Logged into system using created user account

---

## Step 3: System Update

Updated the Debian system packages to ensure the latest security patches and software versions were installed.

### Command used:
```bash
sudo apt update && sudo apt upgrade -y

---

## Step 4: Install Core Administration Tools

Installed essential Linux system administration tools to support networking, monitoring, and remote access.

### Tools Installed:
- OpenSSH Server (remote access via SSH)
- UFW (firewall management)
- curl (data transfer tool)
- wget (file retrieval tool)
- net-tools (network diagnostics utilities)
- htop (system monitoring tool)

### Command used:
```bash
sudo apt install openssh-server ufw curl wget net-tools htop -y

---

## Step 5: SSH Service Setup

Enabled and started OpenSSH server to allow secure remote access to the system.

### Commands used:
```bash
sudo systemctl enable ssh
sudo systemctl start ssh

---

## Step 6: Firewall Configuration (UFW)

Configured and enabled Uncomplicated Firewall (UFW) to secure the system.

### Commands used:
```bash
sudo ufw allow ssh
sudo ufw enable
sudo ufw status

---

## Step 7: SSH Hardening

Applied basic security hardening to the SSH configuration.

### Changes made:
- Disabled root login via SSH (`PermitRootLogin no`)
- Verified SSH service restart after configuration changes

### Commands used:
```bash
sudo nano /etc/ssh/sshd_config
sudo systemctl restart ssh

---

## Step 8: User Management & Permissions

Created and tested a new Linux user account to practice user management and permission concepts.

### Commands used:
```bash
sudo adduser maxslabs
su - maxslabs
whoami
ls -l testfile.txt

---

## Step 9: System Monitoring & Processes

Practiced Linux system monitoring and troubleshooting commands to understand system performance and active processes.

### Commands used:
```bash
uname -a
uptime
ps aux
top
htop
free -h
df -h

---

## Step 10: Logs & Troubleshooting

Explored Linux system logs to understand system events, authentication activity, and troubleshooting data.

### Commands used:
```bash
journalctl -xe
journalctl -b
cat /var/log/auth.log
dmesg
grep "Failed password" /var/log/auth.log

---

## Step 11: Incident Simulation (SSH Service Failure)

Simulated a service outage by stopping the SSH service and practicing troubleshooting and recovery steps.

### Incident:
SSH service was stopped manually to simulate a system failure scenario.

### Investigation:
Checked service status using systemctl to confirm service state.

### Resolution:
Restarted SSH service and verified successful recovery.

### Commands used:
```bash
sudo systemctl stop ssh
sudo systemctl status ssh
sudo systemctl start ssh
