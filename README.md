# SSH Brute-Force Attack Simulation & Intrusion Prevention Lab

## 1. Overview

This project demonstrates a controlled SSH brute-force attack simulation and defensive response using a Linux-based intrusion prevention system. The goal was to evaluate authentication security, logging visibility, and automated threat response mechanisms.

## 2. Lab Environment

* Attacker Machine: Kali Linux
* Target Machine: Debian GNU/Linux
* Service Under Test: OpenSSH
* Security Tools: Fail2ban, UFW Firewall

## 3. Objective

Simulate unauthorized SSH login attempts and observe:

* system logging behaviour
* detection by Fail2ban
* firewall response actions

## 4. Attack Simulation

A brute-force SSH attack was performed from the Kali Linux machine against the Debian target using repeated authentication attempts.

The attack generated multiple failed login events, triggering system security mechanisms.

## 5. Detection & Response

### SSH Logging

The system recorded failed authentication attempts in real time via system logs.

### Fail2ban Response

Fail2ban detected repeated failed login attempts and automatically banned the attacking IP address.

### Firewall Enforcement

UFW enforced network-level blocking rules to prevent further connection attempts.

## 6. Results

* Brute-force attempts successfully detected
* Attacker IP automatically banned
* SSH service remained stable and operational
* No unauthorized access achieved

## 7. Conclusion

The system successfully demonstrated a layered security model combining authentication controls, intrusion detection, and firewall enforcement. This setup effectively mitigates basic SSH brute-force attacks in a Linux environment.
