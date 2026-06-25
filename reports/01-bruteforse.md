# Brute Force Attack - SSH (Hydra)

## Description
Simulation of a brute-force password attack on a Windows SSH service.

## Infrastructure
- Attacker: Kali Linux (192.168.143.129)
- Victim: Windows 10 (192.168.143.130)
- Tool: Hydra
- Protocol: SSH (port 22)

## Attack Command
hydra -l jesse -P /usr/share/wordlists/rockyou.txt ssh://192.168.143.130

##  Wazuh
- Rule ID: 60122
- Rule: Logon Failure - Unknown user or bad password
- Severity level: 5
- Number of events: 15,000+

## Conclusion
The brute-force attack is clearly visible in the logs—an abnormally high
number of Logon Failure events in a short period of time.

## Mitigation Measures
- Fail2ban — block IP addresses after N failed attempts
- Strong passwords (16+ characters)
- Two-factor authentication
- Disable SSH if not in use

