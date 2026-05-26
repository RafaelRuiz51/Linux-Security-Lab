**Screenshots**

### SSH Key Setup
![SSH Key](SSH/basicssh.png)

### PowerShell Remote Connection
![PowerShell SSH](SSH/powershellsshd.png)

### Passwordless Login
![No Password](SSH/sshnopassword.png)

### SSH Activity Logs
![SSH Logs](SSH/sshactivitylog.png)

### Root Login Blocked
![Permission Denied](SSH/permissiondeniedrootlogin.png)

### Hardened sshd_config
![Hardened SSH](SSH/hardenssh.png)

---

## Networking

### Summary
Understanding how data moves across a network is essential for any security role. I explored how my VM was addressed on the network, how DNS resolves domain names, what ports and services were exposed, and how to capture and analyze live traffic — the same skills used in network security monitoring.

### What I Did
- Checked IP addressing and routing tables with ip addr and ip route
- Performed DNS lookups using nslookup and dig
- Scanned open ports and running services with Nmap
- Traced packet routes across the internet with traceroute
- Captured and filtered live network traffic with Wireshark

**Screenshots**

### DNS Records — dig google.com
![DNS Records](Networking/dnsrecordgoogle.com.png)

### Traceroute — Hops to Google
![Traceroute](Networking/hopstogoogle.png)

### Nmap — Open Ports and Services
![Nmap](Networking/nmapshowingportsandservicesopen.png)

### Port 80 Open — Apache Running
![Port 80](Networking/port80open.png)

### Port 200 Open
![Port 200](Networking/port20Open.png)

### curl and ps Output
![curl ps](Networking/curl&ps.png)

### Wireshark — DNS Traffic
![Wireshark DNS](Networking/wiresharkdns.png)

### Wireshark — ICMP Traffic
![Wireshark ICMP](Networking/wiresharkicmp.png)

---

## Firewall

### Summary
A firewall is the first line of defense for any server. I configured both ufw for simplified rule management and iptables for low-level traffic control — blocking all unwanted inbound connections while allowing only the services I explicitly permitted.

### What I Did
- Set default deny on all incoming traffic with ufw
- Allowed only SSH (port 22) and HTTP (port 80)
- Added and removed custom iptables rules manually
- Verified all active rules with ufw status verbose and iptables -L

**Screenshots**

### ufw Active Rules
![ufw Rules](Firewall/activityrules.png)

### iptables Rules
![iptables](Firewall/IPtablerules.png)

---

## Audit Logging

### Summary
Audit logging is how security teams detect unauthorized changes on a system. I configured auditd to watch critical system files and set up log analysis to identify failed login attempts — the same techniques used in real incident response.

### What I Did
- Installed and enabled auditd
- Set watches on /etc/passwd and /etc/shadow to detect unauthorized modifications
- Triggered audit events by adding a test user and confirmed they were captured
- Searched audit logs with ausearch and generated reports with aureport
- Analyzed auth.log to identify failed login attempts and suspicious source IPs

**Screenshots**

### Audit Event Triggered
![Audit Event](Audit-Logging/auditevent.png)

### Failed Login Attempts
![Failed Logins](Audit-Logging/failedloginattempts.png)

### Failed IPs
![Failed IPs](Audit-Logging/failedIP.png)

---

## Scripting

### Summary
Manual monitoring doesn't scale — security engineers automate everything they can. I wrote a Bash script to harden a fresh server automatically, and two Python tools to monitor authentication logs and alert on suspicious IP behavior in real time.

### What I Did
- Wrote a Bash hardening script that installs and configures ufw, Fail2ban, and SSH in one run
- Built a Python auth monitor that reads /var/log/auth.log and reports CPU, RAM, disk, and failed login counts every 30 seconds
- Built a Python IP alert system that tracks failed login attempts per IP and fires an alert when a threshold is crossed — mimicking what real SIEM tools do

**Screenshots**

### Bash Script Running
![Bash](Scripting/bashshowingmyip.png)

### Python Auth Monitor — Live Output
![Python Monitor](Scripting/pythonmonitorshowinglivestats.png)

### Python IP Alert — Alert Firing
![IP Alert](Scripting/pythonalertsystem.png)

---

## Docker

### Summary
Docker is used in virtually every modern tech environment to run applications in isolated, portable containers. I packaged my Python security monitor into a Docker image so it can be deployed on any server instantly — the same workflow used in production security tooling.

### What I Did
- Installed Docker on Ubuntu 24.04 and verified it with a hello-world container
- Ran an Nginx web server container to understand port mapping and container lifecycle
- Wrote a Dockerfile to package the Python auth monitor into a custom image
- Mounted /var/log as read-only so the container could access live system auth logs
- Verified the monitor was running correctly inside the container using docker logs

**Screenshots**

### Python Script Running in Container
![Docker Container](Docker/pythonscriptrunningcontainer.png)
