# Linux Security Lab

A hands-on cybersecurity home lab built on Ubuntu 24.04 in VirtualBox.

## Overview
Built a fully hardened Linux server from scratch. Implemented SSH hardening, 
firewall rules, intrusion detection, automated security monitoring, and containerized tooling.

## Tools Used
- VirtualBox
- Ubuntu 24.04
- SSH
- ufw / iptables
- Fail2ban
- auditd
- Nmap
- Wireshark
- Python
- Bash
- Docker
- Git

## Topics Covered

### SSH Hardening
Key-based authentication, disabled root login, MaxAuthTries, AllowUsers restriction.

### Firewall
ufw and iptables rules — default deny incoming, allow only SSH and HTTP.

### Networking
IP addressing, DNS queries, port scanning with Nmap, live traffic capture with Wireshark.

### Audit Logging
auditd watching /etc/passwd and /etc/shadow. Auth log analysis with grep and awk.

### Scripting
Bash hardening script, Python real-time auth monitor, Python IP alert system with threshold detection.

### Docker
Containerized the Python security monitor with a custom Dockerfile.
