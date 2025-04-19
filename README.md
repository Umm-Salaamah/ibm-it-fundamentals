# ibm-it-fundamentals
Simulation project for IBM IT Fundamentals: Network Troubleshooting

# IBM IT Fundamentals: Network Troubleshooting Simulation

## Overview
This project is part of the **IBM IT Fundamentals** course and involves resolving a fictional client’s network connectivity issue using IT support tools and communication strategies.

---

## 🛠 Step-by-Step Interaction with Jovi (Chatbot Simulation)

### Step 1: Initial Troubleshooting Conversation
We begin by asking a standard question:  
**“Have you restarted your router, and does that help?”**  
Jovi responds with:  
> "When I restart the router, some devices connect to the internet and some don’t. It’s not always the same devices that connect."

![Step 1](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9c1f95f29d35c233413e4653615828f7f8d715/Screenshot%202025-04-17%20193541.png)
![Step 2](https://drive.google.com/file/d/1CtsdILToxb6GDmdlKhu_6yH1amldqcAa/view?usp=drive_link)

---

### Step 2: Narrowing Down the Issue
We then ask if the same number of devices connect each time, helping to isolate the DHCP assignment issue.

![Step 3](https://drive.google.com/file/d/1Yk056BYuK5vTNQxTFGXEIo6a0HLeB5re/view?usp=drive_link)
![Step 4](https://drive.google.com/file/d/1CIRupgrCOeDN2YQiNA_ff8Dl9HQ9Y3U0/view?usp=drive_link)

---

### Step 3: Identify Peripheral Device Issues
We explore whether the issue involves internet-enabled printers and the frustration the user faces.

![Step 5](https://drive.google.com/file/d/1S_98CZnU6lxwW0eggsIj5__1GGsvvxlI/view?usp=drive_link)
![Step 6](https://drive.google.com/file/d/1Xldf92hw0ajB1mstQ9ANU5ZcERZ6jLDE/view?usp=drive_link)

---

### Step 4: Investigating IP Assignment
We ask Jovi if they assigned static IPs, helping us rule out potential conflicts. We confirm DHCP is being used.

![Step 7](https://drive.google.com/file/d/1L6VMGaFsupNMgNjSkKTTOgj9tQ9e1vDv/view?usp=drive_link)

---

### Step 5: Remote Access for Troubleshooting
We remotely access the user’s device using **Google Chrome Remote Desktop** and review the router settings via SSH.

![Remote Access](https://drive.google.com/file/d/16koyid5E7Av8bJ4P1M3pC8LNQQVX9wui/view?usp=drive_link)
![Router Interface](https://drive.google.com/file/d/1jpAOg-PDDA0IqX3XlgF36Km3vAK66q5B/view?usp=drive_link)
![IBM Confirmation Page](https://drive.google.com/file/d/15QNDcgLAU9eSsoB37TS1B9IoWvAr5CEe/view?usp=drive_link)

---

## 🔧 Solution
We identify that the router’s **IP address pool** was too small. The default range (198.168.1.10 to 198.168.1.20) could not support all user devices. We increase the range to:
```
198.168.1.10 → 198.168.1.100
```

## ✅ Result
- Connectivity issues resolved
- Verified fix via SSH access
- Closed ticket with summary report

## 🔑 Skills Demonstrated
- Remote Desktop Support
- Network Troubleshooting (DHCP & IP conflicts)
- IT Support Communication
- SSH & Router Configuration

---


---

## 🔐 Accessing the Router via SSH for DHCP Inspection

After narrowing down the cause to DHCP limits, we accessed the router using **SSH** for deeper inspection.

### Step 6: Launch Command Prompt
![Start CMD](https://drive.google.com/file/d/122gMdioPfp-Gv47VsS0pHSep2gHBHQer/view?usp=drive_link)
![Run Command](https://drive.google.com/file/d/10PctkUwg8dR9-ThxKOEO2DApLErU1inB/view?usp=drive_link)

### Step 7: Connect to the Router via SSH
We ran the following command to initiate a secure shell session:
```bash
ssh admin@192.168.1.1
```
![SSH Initiation](https://drive.google.com/file/d/1azSw-0jF2dyWlqq6cH88OAqBwDupuy02/view?usp=drive_link)

### Step 8: Retrieve DHCP Configuration
Once connected, we used:
```bash
nvram get dhcp_start
nvram get dhcp_end
```
To fetch the current IP address allocation range.

![Check Start IP](https://drive.google.com/file/d/1qrDxDk5TWKTVdhSRT0Kd8ZXgHMRLh62H/view?usp=drive_link)
![Check End IP](https://drive.google.com/file/d/1K2d0sD0s2uRhItna8MLlFE08ASUWrdJs/view?usp=drive_link)

---

## 🔧 Solution Applied

We confirmed that the IP pool was too small to serve all devices. Using the web router interface, we updated the DHCP range:

**Before:**  
Start: `192.168.1.2`  
End: `192.168.1.10`  

**After:**  
End expanded to `192.168.1.100`

![DHCP Adjustment](https://drive.google.com/file/d/1yYi1zeEsIp2PDUH646XWDWJT-J4DERow/view?usp=drive_link)

---

## ✅ Resolution and Closing Chat

We verified that all devices could now connect to the network and followed up with the user to confirm resolution.

![Confirmation Message](https://drive.google.com/file/d/1b_Jdc_r6DjkO3ugmIIY1kyEcVKbWrpJh/view?usp=drive_link)
![Final Chat Message](https://drive.google.com/file/d/102jV922Q3AhKW7XOlcXuYON59WXJckAn/view?usp=drive_link)
![Closure](https://drive.google.com/file/d/1cN3_EKBT10oAwxoqxuQDQ36khn5RwFJu/view?usp=drive_link)

---

## 🏁 Final Outcome

The issue was resolved through:
- Careful communication
- Remote access and troubleshooting
- DHCP inspection via SSH and router interface

This hands-on experience strengthened my skills in technical analysis, customer support, and remote problem-solving.
