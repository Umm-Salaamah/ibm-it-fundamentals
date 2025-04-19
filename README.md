
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

![Step 1](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-17%20193541.png)
![Step 2](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-17%20193555.png)

---

### Step 2: Narrowing Down the Issue
We then ask if the same number of devices connect each time, helping to isolate the DHCP assignment issue.

![Step 3](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-17%20193724.png)
![Step 4](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-17%20193753.png)

---

### Step 3: Identify Peripheral Device Issues
We explore whether the issue involves internet-enabled printers and the frustration the user faces.

![Step 5](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-17%20193916.png)
![Step 6](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-17%20194047.png)

---

### Step 4: Investigating IP Assignment
We ask Jovi if they assigned static IPs, helping us rule out potential conflicts. We confirm DHCP is being used.

![Step 7](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20194840.png)

---

### Step 5: Remote Access for Troubleshooting
We remotely access the user’s device using **Google Chrome Remote Desktop** and review the router settings via SSH.

![Remote Access](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20195050.png)
![Router Interface](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20195111.png)
![IBM Confirmation Page](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20195125.png

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
![Start CMD](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20200424.png)
![Run Command](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20200504.png)

### Step 7: Connect to the Router via SSH
We ran the following command to initiate a secure shell session:
```bash
ssh admin@192.168.1.1
```
![SSH Initiation](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20200610.png)

### Step 8: Retrieve DHCP Configuration
Once connected, we used:
```bash
nvram get dhcp_start
nvram get dhcp_end
```
To fetch the current IP address allocation range.

![Check Start IP](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20200800.png)
![Check End IP](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20201616.png)

---

## 🔧 Solution Applied

We confirmed that the IP pool was too small to serve all devices. Using the web router interface, we updated the DHCP range:

**Before:**  
Start: `192.168.1.2`  
End: `192.168.1.10`  

**After:**  
End expanded to `192.168.1.100`

![DHCP Adjustment](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20201656.png)

---

## ✅ Resolution and Closing Chat

We verified that all devices could now connect to the network and followed up with the user to confirm resolution.

![Confirmation Message](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20201809.png)
![Final Chat Message](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20210417.png)
![Closure](https://github.com/Umm-Salaamah/ibm-it-fundamentals/blob/8f9262e7d3cdd321ff44b70b6a64d70eb7878860/Screenshot%202025-04-18%20210442.png)

---

## 🏁 Final Outcome

The issue was resolved through:
- Careful communication
- Remote access and troubleshooting
- DHCP inspection via SSH and router interface

This hands-on experience strengthened my skills in technical analysis, customer support, and remote problem-solving.
