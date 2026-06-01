# Active Directory Detection & Response Lab

## Overview
Built an enterprise-style security monitoring environment to simulate detection and response to unauthorized RDP activity in an Active Directory environment.

The project combines Active Directory, Splunk, Shuffle SOAR, and Slack to create an automated incident response workflow capable of detecting suspicious logins, notifying analysts, and disabling compromised accounts.

## Objectives
- Deploy an Active Directory environment
- Centralize Windows Security logs in Splunk
- Detect unauthorized RDP logins
- Generate real-time security alerts
- Integrate SOAR automation
- Send analyst notifications through Slack
- Automate account containment actions

### Skills Learned
- Active Directory Administration
- Windows Server Management
- Security Event Monitoring
- Splunk Deployment
- Universal Forwarder Configuration
- SPL Query Development
- Detection Engineering
- Alert Tuning
- SOAR Automation
- Incident Response
- Security Operations Center (SOC) Workflows
  
## MITRE ATT&CK Mapping
| Technique | Description |
|------------|------------|
| T1078 | Valid Accounts |
| T1021.001 | Remote Desktop Protocol |
| T1110 | Brute Force |

### Tools Used
| Tool                       | Purpose
| -------------------------- |-------------------- |
| VMware Workstation	       | Virtualization      |
| Windows Server 2022	       | Domain Controller   |
| Windows 10	               | Endpoint            |
| Ubuntu	                   | Splunk Server       |
| Kali Linux	               | Attack Simulation   |
| Splunk Enterprise	         | SIEM                |
| Splunk Universal Forwarder | Log Collection      |
| Shuffle	                   | SOAR Platform       |
| Slack	                     | Alerting            |
| Draw.io	                   | Architecture Design |


## Part 1: Environment Build
draw.io was used to make a diagram to logically map out the lab. 
<img width="2249" height="857" alt="Untitled" src="https://github.com/user-attachments/assets/d58f4c89-0911-46bc-965c-f9b2edffbda5" />

The lab consists of four virtual machines connected through a private network. Windows Security Events are forwarded to Splunk for analysis. Detection alerts are sent to Shuffle via webhook, which generates Slack notifications and enables automated response actions.
| System         | Purpose           | IP              |
| -------------- | ----------------- | --------------- |
| Windows Server | Domain Controller | 192.168.112.128 |
| Windows Server | Test Machine      | 192.168.112.129 |
| Ubuntu         | Splunk            | 192.168.112.131 |
| Kali           | Attack simulation | 192.168.112.132 |


### Windows Test Machine
<img width="451" height="645" alt="Screenshot (273)" src="https://github.com/user-attachments/assets/e274a3be-6de0-46f5-aabe-3595f7e47844" />



Created test users for authentication and monitoring purposes.
<img width="1915" height="759" alt="Screenshot (71)" src="https://github.com/user-attachments/assets/6f8a1710-d9d9-416c-9c93-6439227ba8ec" />



Joined the Windows endpoint to the Active Directory domain.
<img width="1919" height="704" alt="Screenshot (73)" src="https://github.com/user-attachments/assets/184c923f-b535-4a7c-9c9f-9b3d8b1cdf0f" />
<img width="1917" height="752" alt="Screenshot (76)" src="https://github.com/user-attachments/assets/b27ae57d-6bb5-4e8b-a904-9c7ecf888875" />
<img width="1890" height="874" alt="Screenshot (78)" src="https://github.com/user-attachments/assets/9c6ba94c-b086-4688-b10a-d789e9d90d77" />


## Part 2: Splunk Deployment


Installed Splunk Universal Forwarder on the Windows endpoint and configured forwarding to the Splunk server.
<img width="1119" height="523" alt="Screenshot (147)" src="https://github.com/user-attachments/assets/798be549-0fa7-4e0c-a6b9-837040ed9ee2" />

Configured Windows Security Event collection using inputs.conf.

Configuration:

[WinEventLog://Security]
index = rahmd-ad
disabled = false

<img width="769" height="342" alt="Screenshot (150)" src="https://github.com/user-attachments/assets/7c5ce2cc-12eb-429c-8636-c95a992a26c4" />
<img width="491" height="61" alt="Screenshot (151)" src="https://github.com/user-attachments/assets/3917f391-2f4b-4107-898f-1e270171affb" />

Verified successful ingestion of Windows Security Events.
<img width="1000" height="855" alt="Screenshot (159)" src="https://github.com/user-attachments/assets/be0ce8c3-3836-4a4c-b3b2-dd8b7a501cb5" />


## Part 3: Detection Engineering

Relevant Event ID
| Event ID |   Description            |
|--------- | ------------------------ |
| 4624     | Successful Logon(Type 10)|

Used Kali Linux to RDP into the test machine
<img width="1082" height="781" alt="Screenshot (171)" src="https://github.com/user-attachments/assets/d0f7300c-e7e8-421b-b586-53eb768ce1ff" />

Made a SPL Query to identify suspicious successful RDP logins.

SPL Detection Query

index=rahmd-ad EventCode=4624 Logon_Type=10
| stats count by Account_Name Source_Network_Address host
<img width="1561" height="812" alt="Screenshot (169)" src="https://github.com/user-attachments/assets/bb05db48-47b3-4320-9dcd-0f1782b43e11" />

Created a scheduled alert to identify suspicious successful RDP logins.
<img width="1028" height="936" alt="Screenshot (170)" src="https://github.com/user-attachments/assets/9fdd2e25-723d-4d02-8a27-305a7144695e" />
<img width="1585" height="171" alt="Screenshot (259)" src="https://github.com/user-attachments/assets/ad767525-901f-413f-b802-4667b6da2893" />


## Part 4: SOAR Automation
### Workflow Overview

1. Splunk alert triggers.                                                                                  
2. Alert is sent to Shuffle.
3. Shuffle posts notification to Slack.
4. Analyst reviews alert.
5. Analyst decides whether to disable account.
6. Active Directory action executes.
7. Slack confirmation is sent.


Configured Splunk alert actions to send events to Shuffle.
<img width="790" height="332" alt="Screenshot (175)" src="https://github.com/user-attachments/assets/4509ccbc-f3d9-489f-9faf-6cfc9e2cbdc1" />

Configured Slack channel alerts for security events.
<img width="2102" height="1330" alt="Screenshot (211)" src="https://github.com/user-attachments/assets/745d5705-a756-4d92-93e8-5aa1f2e30217" />
<img width="1295" height="852" alt="Screenshot (227)" src="https://github.com/user-attachments/assets/a5db18cb-acb3-4240-a5a8-68091f37f65c" />

Email is sent after Slack alert
<img width="1430" height="533" alt="Screenshot (252)" src="https://github.com/user-attachments/assets/4313c9f9-36b2-46e5-a1fc-6507bce0dfc4" />
<img width="1989" height="306" alt="Screenshot (246)" src="https://github.com/user-attachments/assets/25882c05-53bc-429a-adf8-d8568be101f4" />

Created a response workflow that requires analyst approval before disabling a potentially compromised account.
<img width="1879" height="178" alt="Screenshot (245)" src="https://github.com/user-attachments/assets/4b1a383f-2bec-40ff-92a5-2b06e0a3fad8" />
<img width="1450" height="795" alt="Screenshot (251)" src="https://github.com/user-attachments/assets/d82b329e-9b41-491c-a892-ff48289b0d3f" />
<img width="768" height="127" alt="Screenshot (247)" src="https://github.com/user-attachments/assets/57f4c371-e586-49da-9eb7-c20cef588b8f" />

Slack notifies if an account is disabled
<img width="1822" height="594" alt="Screenshot (250)" src="https://github.com/user-attachments/assets/35ed6654-2956-4818-b729-9a0384be71b8" />
<img width="1242" height="858" alt="Screenshot (248)" src="https://github.com/user-attachments/assets/6708dd2b-c734-4233-96ca-a90bd4b54109" />

# Conclusion
Successfully built an enterprise-style SOC environment capable of:

1. Centralized Windows log collection
2. Active Directory monitoring
3. Detection of successful RDP logins
4. Real-time alert generation
5. Slack notification delivery
6. Analyst-guided containment
7. Automated account disabling

And this project follows the SOC cycle

Log collection -----> Detection -----> Alert -----> Investigate -----> Response-----> Containment

# Future Improvements
- Sysmon integration
- Additional detection rules
- PowerShell logging
- Windows Defender monitoring
- Automated ticket creation
- Threat intelligence enrichment
- Multi-stage attack simulations
