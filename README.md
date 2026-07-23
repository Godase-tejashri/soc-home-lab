# SOC Home Lab - Wazuh SIEM Deployment & Threat Monitoring

## Project Overview
Implemented a Wazuh SIEM home lab on an Acer PC and Windows to monitor endpoint logs, analyze MITRE ATT&CK threats, and detect authentication failures via a central dashboard.

---

## Architecture & Implementation Steps

### 1. Environment Setup
Wazuh Server: Deployed and hosted on a local server (IP: 10.163.225.136).
Endpoints Monitored:
  Linux Endpoint :Agent installed with IP 192.168.100.5.
  Windows Endpoint:Windows 10 instance connected to the manager.

### 2. Agent Installation (Linux Command Reference)
```bash
sudo WAZUH_MANAGER="10.163.225.136" dpkg -i wazuh-agent_4.14.6-1_amd64.deb
sudo systemctl daemon-reload
sudo systemctl enable wazuh-agent
sudo systemctl start wazuh-agent

Lab Screenshots & Evidence
1. Linux Agent Installation & Status
Description:
 Successful installation and active running status of the Wazuh agent on the Linux Acer PC. Verified that the agent service is actively communicating with the central Wazuh manager via secure channels.

<img width="1600" height="953" alt="image_1" src="https://github.com/user-attachments/assets/964668a8-21c7-466f-8dba-782dc16db1be" />


2. Wazuh Discover / Logs (Authentication Failure)
Description: Captured PAM and unix_chkpwd system logs displaying explicit failed password attempts (Rule ID: 5557, Severity Level 5). This validates how raw operating system logs are parsed into structured security events.

<img width="1502" height="850" alt="image_2" src="https://github.com/user-attachments/assets/866ff40f-e41e-43bf-b467-689bd84f68c0" />


3. MITRE ATT&CK Dashboard Analysis
Description:
Real-time mapping of detected security events against the MITRE ATT&CK framework, categorizing the malicious or failed login attempts under Credential Access (Technique: T1110.001 - Password Guessing).

figure 1:<img width="1600" height="897" alt="image_3" src="https://github.com/user-attachments/assets/728a7825-2cac-487d-ae76-3116f6cfda8c" />
figure 2:<img width="1592" height="904" alt="image_4" src="https://github.com/user-attachments/assets/c5c02897-6d06-4cbb-9d83-7cfd7419a81e" />


4. Threat Hunting Summary & Analytics
Description:
Comprehensive overview showing total alert metrics, agent distribution across the network, and frequency of authentication failures to monitor overall endpoint security posture.

figure 1:<img width="1600" height="916" alt="image_5" src="https://github.com/user-attachments/assets/9c0b82c9-4dcd-41de-8048-4cb39099adc5" />
figure 2:<img width="1332" height="798" alt="image_6" src="https://github.com/user-attachments/assets/74243f05-aaea-4df3-ab36-cdaec1361b18" />


Conclusion
This hands-on SOC home lab successfully demonstrates endpoint log collection, SIEM monitoring, threat detection engineering, and incident investigation workflows.
