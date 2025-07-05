# code-alpha-Task4
# 🛡️ CodeAlpha Task 4 – Setting Up NIDS Using Snort on Ubuntu

This project documents the full process of setting up a **Network-Based Intrusion Detection System (NIDS)** using **Snort** on **Ubuntu**, as part of **Task 4** in my **CodeAlpha Cybersecurity Internship**. The NIDS was tested using **Kali Linux attacks**, successfully detecting malicious scans.

---

## 📌 Live Link

View : https://adityadahake33.github.io/code-alpha-Task4/
---

## 🧠 Steps to Set Up Snort for NIDS on Ubuntu

### 📥 1. Install Gedit (to edit Snort config easily)

sudo apt install gedit

### 🐍 2. Install Snort

sudo apt-get install snort -y
During installation, you’ll be asked for your HOME_NET IP. You can modify this later if needed.

### ⚙️ 3. Configure snort.conf (set your IP address)

Open the config file in gedit:

sudo gedit /etc/snort/snort.conf
Find the line:
ipvar HOME_NET any

### Replace it with:
ipvar HOME_NET [your Ubuntu IP]
💡 You can find your IP with ifconfig or ip a (commonly ens33 interface)

### 🧪 4. Test the Snort Configuration

To verify if everything is working:

sudo snort -T -c /etc/snort/snort.conf -i ens33

### ▶️ 5. Start Snort in Live Detection Mode!


This command runs Snort in console alert mode:

sudo snort -A console -q -u snort -g snort -c /etc/snort/snort.conf -i ens33


### 💣 Simulating Attacks with Kali Linux
On the Kali Linux machine, I performed Nmap scans targeting the Ubuntu system:

### 1. Null Scan:
nmap -sN [Ubuntu IP]

### 2. Ping Scan (host discovery):
nmap -Pn [Ubuntu IP]
✅ The Snort console detected and alerted these scans, proving the NIDS setup is working correctly.


📁 Files Included
snort.conf (optional) – Modified config

screenshots/ – Setup and detection proof (to be added)

🧠 What I Learned
Installing and configuring Snort as a live IDS

Customizing snort.conf with the local network

Running detection on real-time traffic

Simulating threats using Kali Linux

Interpreting console-based intrusion alerts

📜 Credits
🏢 Internship Organization: CodeAlpha

🔐 Task: 4 – NIDS Setup and Attack Simulation

👨‍💻 Role: Cybersecurity Intern

🗓️ Month: June 2025


🙌 Special Thanks
Huge gratitude to CodeAlpha for providing this hands-on experience and to the mentors who guide aspiring cybersecurity professionals like me every step of the way! 🌸

---

Let me know if you want:
- A version with embedded images later 📸  
- Markdown preview with emojis/icons  
- Deployment instructions to run this setup in a VM or lab

You're absolutely rocking it, sakha! Let’s capture every bit of your skill and progress! 💻🛡️✨
