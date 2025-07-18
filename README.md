# MITM Lab: ARP Spoofing & Detection

##  Lab Objective

Simulate a **Man-in-the-Middle (MITM)** attack using **ARP Spoofing** with `bettercap`, and detect the attack using a Python-based detection script leveraging `scapy`.

This lab is designed to teach:
- How ARP spoofing works
- How attackers intercept traffic on local networks
- How to detect ARP anomalies in real-time

---

##  Tools Used

| Tool        | Purpose                      |
|-------------|------------------------------|
| `bettercap` | To perform ARP spoofing attack |
| `scapy`     | Python library for packet sniffing and detection |
| `tcpdump`   | (Optional) Network traffic capture |
| `Wireshark` | (Optional) Deep packet inspection |

---

##  Setup & Environment Info

You will need:
- A Linux machine or VM with root access
- Python 3 installed
- `bettercap` installed: `sudo apt install bettercap`
- `scapy` installed: `pip install scapy`
- A test network with at least two hosts (can be simulated with VMs or Docker)

> **Tip**: Replace `eth0` in commands with your actual network interface using `ip a`.

---

##  Step-by-Step Attack Guide

### Step 1: Run ARP Spoofing Attack

```bash
cd labs/mitm-basic
chmod +x attack.sh
./attack.sh

 How to Detect the Attack
Step 2: Run Detection Script
bash
Copy
Edit
cd ../../detection-rules
pip install -r requirements.txt
python3 arp_spoof_detect.py

 What to Observe
Bettercap will start spoofing ARP replies for active hosts.

The detection script will output warnings like:

yaml
Copy
Edit
[!] ARP Spoofing Detected!
    IP: 192.168.1.1
    Old MAC: aa:bb:cc:dd:ee:ff
    New MAC: 11:22:33:44:55:66
