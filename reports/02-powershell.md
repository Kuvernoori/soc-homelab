# Malicious PowerShell + Sysmon Detection

## Description
Simulation of a hacker’s actions after gaining access to the system.

## Commands Executed
powershell -enc <base64>   # encoded command
whoami                     # check current user
net user                   # list users
net localgroup administrators  # list administrators
ipconfig /all              # network information

## What Wazuh Detected (via Sysmon)
| Rule ID | Description | Level |
|---|---|---|
| 92033 | Discovery activity spawned via PowerShell | 3 |
| 92039 | net.exe account discovery command | 3 |
| 92205 | PowerShell created an executable in the root folder | 9 |
| 92066 | Suspicious binary launched by PowerShell | 4 |

## Conclusion
Sysmon allows you to view the details of each command—
which process was launched, who launched it, and what it did.

## Mitigation Measures
- Constrained Language Mode for PowerShell
- Application Whitelisting
- AMSI (Antimalware Scan Interface)
- Monitoring of encoded commands (-enc flag)

