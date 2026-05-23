# Linux SSH Brute-Force Defense Lab

## Overview

This project simulates a controlled SSH brute-force attack against a Linux server and demonstrates how defensive security controls detect, respond to, and mitigate unauthorized access attempts.

The goal of this lab is to replicate a real-world attack scenario and implement layered security controls to protect SSH services in a Linux environment.

---

## Lab Environment

- OS: Debian Linux
- Service: OpenSSH Server
- Attacker Simulation: Kali Linux
- Platform: VirtualBox (isolated lab environment)

---

## Security Tools Used

- Fail2Ban (intrusion prevention system)
- UFW Firewall (network filtering)
- OpenSSH (target service)
- Linux system logs (`/var/log/auth.log`)

---

## Attack Scenario

A brute-force SSH attack was simulated against the target system using repeated login attempts with invalid credentials. The objective was to test the system’s ability to detect and respond to unauthorized access attempts.

---

## Detection & Response

The system successfully identified multiple failed authentication attempts through system logging.

Fail2Ban monitored authentication logs in real time and automatically:

- Detected repeated failed login attempts
- Banned offending IP addresses
- Updated firewall rules dynamically

---

## Mitigation Controls

### Fail2Ban
- Monitors SSH authentication logs
- Automatically blocks suspicious IP addresses after repeated failures

### UFW Firewall
- Enforces network-level access control
- Restricts unauthorized inbound traffic to SSH service

---

## Evidence

The following evidence is included in this repository:

1. SSH service actively listening on port 22  
2. Multiple failed SSH login attempts recorded in system logs  
3. Fail2Ban jail status confirming active protection  
4. UFW firewall rules enforcing access control  

---

## Outcome

The system successfully detected and mitigated brute-force SSH attempts without manual intervention, demonstrating effective layered security controls.

---

## Key Learnings

- Importance of monitoring authentication logs in Linux systems
- Effectiveness of Fail2Ban for automated intrusion prevention
- Role of firewall rules in reducing attack surface
- Value of defense-in-depth security strategy
