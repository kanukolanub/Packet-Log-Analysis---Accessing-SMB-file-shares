# Packet-Log-Analysis---Accessing-SMB-file-shares
# 🛡️ SMB Attack Simulation & Detection Lab

## 📘 Introduction

As part of my hands-on learning journey toward becoming a **Security Operations Center (SOC) Analyst**, I designed and executed a lab focused on simulating and detecting **SMB-based attack techniques**. This project allowed me to explore how attackers exploit network file sharing protocols and how defenders can identify and respond to such threats using logs and network analysis.

## 🧪 Lab Objectives

- Simulate SMB enumeration and file access from a Linux (Ubuntu) machine to a Windows target
- Observe and analyze Windows Event Logs for suspicious activity
- Capture and inspect SMB traffic using Wireshark
- Understand attacker behavior and map it to MITRE ATT&CK techniques
- Practice incident detection and documentation

## 🖥️ Lab Environment

| Component        | Details                          |
|------------------|----------------------------------|
| Attacker Machine | Ubuntu 22.04 (Kali optional)     |
| Target Machine   | Windows 10 (with SMB enabled)    |
| Tools Used       | Wireshark, Event Viewer, PowerShell, smbclient |
| Network Setup    | Host-only or bridged network     |

## ⚙️ Attack Simulation Steps

1. **SMB Enumeration**  
   Used `smbclient -L <IP>` to list available shares on the Windows machine.

2. **Accessing Shared Files**  
   Connected to a share using `smbclient //<IP>/<Share>` and browsed files.

3. **File Transfer**  
   Downloaded and uploaded files to simulate data exfiltration and staging.

4. **Log Analysis**  
   Inspected Windows Event Logs for SMB-related events (e.g., 5140, 4624, 4662).

5. **Network Traffic Capture**  
   Used Wireshark to capture SMB packets and identify anomalies.

## 🔍 Detection & Analysis

- **Event IDs Monitored**:
  - `4624`: Successful logon
  - `5140`: Network share accessed
  - `4662`: Object access (file read/write)

- **Indicators of Compromise (IOCs)**:
  - Unusual access times
  - Access from unknown IPs
  - Large file transfers

- **MITRE ATT&CK Mapping**:
  - `T1071.002`: Application Layer Protocol – SMB
  - `T1021.002`: Remote Services – SMB/Windows Admin Shares
  - `T1041`: Exfiltration Over SMB

## 📈 Key Learnings

- SMB traffic is rich with forensic evidence when properly logged and monitored.
- Event correlation between logs and
