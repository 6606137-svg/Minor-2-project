# Network Traffic Analysis & Incident Investigation Using PCAP  
### (SOC Analyst Simulation)

## 📌 Project Overview
This project focuses on analyzing network traffic using PCAP files, simulating the role of a SOC Analyst.  
The goal is to identify malicious activity, detect reconnaissance behavior, analyze HTTP traffic, and extract files from unencrypted network communication using **Wireshark**.

---

## 🎯 Project Objectives
- Analyze PCAP files like a SOC Analyst  
- Identify attacker and victim IP addresses  
- Detect reconnaissance activity such as Nmap port scanning  
- Analyze HTTP traffic  
- Extract files from unencrypted network traffic  

---

## 🛠 Tools Used
- **Wireshark**
- **PCAP File**
- **Windows / Linux OS**

---

## 🔍 Methodology & Steps

### Step 1: Download PCAP File
- Obtain the PCAP file provided for analysis.

### Step 2: Open PCAP in Wireshark
- Launch Wireshark  
- Open the downloaded PCAP file  

### Step 3: Analyze Traffic Pattern
- Use **Statistics → Conversations**
- Identify high packet flow between source and destination
- Determine attacker and victim IP addresses

### Step 4: Identify Attack Start Time
- Use **Statistics → I/O Graph**
- Analyze timestamps to find sudden spikes in traffic

### Step 5: Detect Reconnaissance Activity (Port Scanning)
Apply the following Wireshark filter : tcp.flags.syn == 1 && tcp.flags.ack == 0
- Large number of SYN packets sent to multiple ports confirms scanning activity

### Step 6: Analyze HTTP Traffic
- Apply HTTP filter : http
- Navigate to **File → Export Objects → HTTP**
- Identify and extract the downloaded ZIP file

### Step 7: Extract the ZIP File
- Save the ZIP file locally
- Unzip the file to reveal the extracted content and flag

---

## ❓ Questions & Answers

**1. What is the attacker IP address?**  
- `192.168.29.10`

**2. What is the first packet timestamp related to the attack?**  
- Within **1 second (approximately 100 packets)**

**3. What is the name of the downloaded ZIP file?**  
- `dog_flag.jpg`

**4. What is the flag obtained after unzipping the file?**  
- `pkhuyar{dogesh_bhai_jindabad}`

**5. What evidence suggests reconnaissance activity?**  
- The attacker sends multiple SYN packets to different port numbers on the victim machine

---

## 📊 Result & Conclusion
This project demonstrates how PCAP analysis helps in identifying malicious behavior such as port scanning and unauthorized file downloads.  
Using Wireshark, we successfully detected reconnaissance activity, identified attacker details, and extracted sensitive files from unencrypted HTTP traffic.

---
