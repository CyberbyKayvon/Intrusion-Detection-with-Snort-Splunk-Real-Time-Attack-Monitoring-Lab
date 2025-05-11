# Intrusion-Detection-with-Snort-Splunk-Real-Time-Attack-Monitoring-Lab
This project demonstrates real-time detection and analysis of network-based attacks using **Snort** and **Splunk Enterprise**. It includes configuration, live traffic monitoring, and the generation of alerts for multiple Nmap scans and exploits.

## 🛠Tools & Environment

- Snort IDS
- Splunk Enterprise (local instance)
- Kali Linux (attacker)
- Metasploitable2 (victim)
- Ubuntu 22.04 (Snort + Splunk host)
- VirtualBox with NAT networking

## Objectives

- Configure Snort to output logs in `alert.full` format
- Set up Splunk to ingest Snort logs in real time
- Launch various Nmap scans and Metasploit exploits
- Correlate and verify alerts in Snort and Splunk
- Create a custom Snort rule for Java RMI detection

## Setup Overview

1. **Assign Static IP to Ubuntu VM**
2. **Install Snort and edit snort.conf**
3. **Configure Splunk to ingest `/var/log/snort/alert.full`**
4. **Install "Snort Alert for Splunk" App**
5. **Run attack simulations and compare detection**

## Attacks Simulated

- Nmap: ping scan, TCP scan, UDP scan, OS detection, service version
- Exploits: VSFTPD backdoor, Java RMI
- Exfiltration: `/etc/passwd` & `/etc/shadow` via Netcat

## Alert Examples

- "Possible Nmap SYN scan"
- "ATTACK-RESPONSES id check returned root"
- Custom Rule: "Potential Java RMI Exploit!" (SID 1000003)

## Results

| Attack Type        | Snort Alerts | Splunk Alerts |
|--------------------|--------------|----------------|
| TCP Scan (-sT)     | 1,101        | 1,069          |
| UDP Scan (-sU)     | 8            | 8              |
| OS Detection (-O)  | 4            | 4              |
| VSFTPD Exploit     | 2            | 2              |
| Java RMI Exploit   | 14           | 14             |

## Custom Snort Rule (Java RMI)


## Key Learnings

- Real-time log correlation with Splunk
- Custom IDS rule creation
- Challenges in log duplication, ingestion lag
- Importance of alert summaries vs full event logs

## Screenshots

![Snort Alerts in Splunk](screenshots/splunk-snort-alerts.png)
![Snort Console Output](screenshots/snort-output-terminal.png)

---


