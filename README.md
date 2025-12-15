# 🔐 Integration of Snort IDS with Wazuh SIEM

**One-line description:**  
An open-source cybersecurity project demonstrating the integration of Snort IDS with Wazuh SIEM to detect network intrusions in real time, centralize IDS alerts, and enable threat monitoring, log correlation, and incident analysis through a unified security dashboard.

---

## 📌 Project Overview

This project demonstrates the integration of **Snort Intrusion Detection System (IDS)** with **Wazuh Security Information and Event Management (SIEM)** to achieve centralized and real-time monitoring of network-based security events. Snort inspects live network traffic and generates alerts for suspicious activities, while Wazuh collects, correlates, and visualizes these alerts through a unified dashboard.

The integration enables security analysts to monitor IDS alerts, perform threat hunting, and analyze intrusion attempts from a single interface, improving visibility and incident response capabilities.

---

## 🏗️ System Architecture

```
Network Traffic
       |
       v
   Snort IDS
(Packet Inspection)
       |
   alert.ids
       |
       v
  Wazuh Agent
(Log Collection)
       |
       v
 Wazuh Manager
(Log Analysis)
       |
       v
 Wazuh Dashboard
(SIEM & Analytics)
```

---

## 🛠️ Technologies Used

- Snort IDS  
- Wazuh SIEM  
- Wazuh Agent  
- Npcap  
- Windows & Linux  

---

## ⚙️ Setup & Configuration

### 1. Snort Installation
- Install Snort on Windows
- Install Npcap (WinPcap compatibility mode)
- Configure `snort.conf`
- Enable logging to:
```
C:\Snort\log\alert.ids
```

### 2. Wazuh Server Setup
- Install Wazuh Manager, Indexer, and Dashboard on Linux
- Verify all services are running

### 3. Wazuh Agent Setup
- Install agent on Snort system
- Register agent using authentication key
- Ensure agent status is active

### 4. Snort–Wazuh Integration
Add the following to `ossec.conf`:
```xml
<localfile>
  <log_format>syslog</log_format>
  <location>C:\Snort\log\alert.ids</location>
</localfile>
```

Restart the Wazuh agent after configuration.

---

## 📊 Results

- ICMP and scan traffic detected by Snort
- Alerts forwarded to Wazuh successfully
- IDS alerts visible in Wazuh Threat Hunting dashboard

---

## 📸 Screenshots

Screenshots included:
- Snort installation
- Wazuh agent setup
- Alert generation
- Dashboard visualization

---

## 🚀 Future Enhancements

- SOAR integration
- Threat intelligence enrichment
- Automated incident response
- Multi-agent deployment

---

## 👨‍🎓 Authors

- Muhammed Danish AP  
- Mohammed Nasvin  
- Delson Dennis  

**Guide:** Malavika  
**Institute:** RedTeam Hacker Academy  

---

## 📜 License

This project is intended for educational and research purposes only.
