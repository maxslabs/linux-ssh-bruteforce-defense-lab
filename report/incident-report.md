# SSH Brute Force Attack Simulation & Defense Report

## 1. Incident Summary

This report documents a simulated SSH brute-force attack against a Debian Linux system and the defensive measures implemented to mitigate the attack. The objective was to understand how unauthorized access attempts can be detected and prevented using Linux security tools.

---

## 2. Environment

- OS: Debian Linux
- Service: OpenSSH Server
- Security Tools: Fail2Ban, UFW Firewall
- Lab Type: Isolated Virtual Machine (VirtualBox)

---

## 3. Attack Simulation

A brute-force attack simulation was performed against the SSH service. Multiple failed login attempts were generated to mimic unauthorized access attempts targeting valid and invalid usernames.

Evidence of failed login attempts is shown in the system logs.

---

## 4. Detection

The system successfully recorded multiple failed authentication attempts.

Fail2Ban monitored SSH logs and detected repeated failures from the same source, triggering automatic defensive rules.

---

## 5. Mitigation

The following security controls were implemented:

### Fail2Ban
- Monitored `/var/log/auth.log`
- Detected repeated failed SSH login attempts
- Automatically banned offending IP addresses

### UFW Firewall
- Restricted and controlled inbound SSH traffic
- Verified active firewall rules protecting SSH service

---

## 6. Evidence

Screenshots included in this repository:

1. SSH service running and listening on port 22  
2. Failed SSH login attempts recorded in logs  
3. Fail2Ban active jail status  
4. UFW firewall rules enforcing access control  

---

## 7. Outcome

The system successfully detected and mitigated brute-force attempts. Unauthorized access was prevented through automated banning and firewall enforcement.

---

## 8. Key Learnings

- Importance of monitoring authentication logs
- Effectiveness of Fail2Ban in brute-force prevention
- Role of firewall rules in restricting access
- Value of layered security (defense in depth)
