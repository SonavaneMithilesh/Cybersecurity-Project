# Cybersecurity Lab Environment Setup

An isolated virtual cybersecurity lab built with **VMware Workstation** and **Kali Linux** for cybersecurity learning, penetration-testing practice, and authorized security testing.

## 📌 Project Overview

This project focuses on setting up a virtual cybersecurity and penetration-testing laboratory using VMware Workstation and Kali Linux.

The purpose of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, packet analysis, and other security-testing activities can be performed safely and repeatedly.

The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.

## 🎯 Objectives

The main objectives of this project are to:

- Install and configure VMware Workstation.
- Install/import Kali Linux as a virtual machine.
- Create and configure an isolated virtual network.
- Configure network connectivity for Kali Linux.
- Assign a consistent IP address to the Kali VM.
- Verify network connectivity and DNS resolution.
- Create a clean VM snapshot for recovery.
- Document the complete setup process.
- Prepare the environment for future cybersecurity projects.

## 🛡️ Purpose of the Lab

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Security-tool experimentation
- Penetration-testing practice in authorized lab environments

## 🧰 Lab Features

| Component | Configuration |
|---|---|
| 🖥️ Host OS | Windows 11 |
| 🧠 Host RAM | 16 GB |
| ⚡ Processor | Intel Core i5-120U |
| 🧰 Hypervisor | VMware Workstation |
| 🐉 Security OS | Kali Linux 2026.2 |
| 🧠 Kali RAM | 2048 MB |
| 🌐 Virtual Network | VMware NAT / Isolated Virtual Network |
| 📡 Network Address | 10.0.0.0/24 |
| 🐧 Kali IP Address | 10.0.0.2/24 |
| 🚪 Default Gateway | 10.0.0.1 |
| 🌍 DNS Server | 8.8.8.8 |

> **Note:** Replace the network/IP values above if your actual VMware configuration uses different values.

## 🔧 Lab Setup Procedure

### Step 1. Install 7-Zip

7-Zip was installed to extract the Kali Linux virtual-machine package when distributed as a `.7z` archive.

**Tool:** 7-Zip

### Step 2. Install VMware Workstation

VMware Workstation was installed as the hypervisor for creating and managing the cybersecurity virtual laboratory.

### Step 3. Configure the Virtual Network

A dedicated virtual network was configured in VMware for the cybersecurity lab.

The network was designed to provide controlled communication between future attacker and target virtual machines.

A private virtual network is useful for cybersecurity labs because testing activities can be performed without directly exposing intentionally vulnerable machines to the physical network.

### Step 4. Import Kali Linux

The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported/configured in VMware Workstation.

The VM network adapter was configured to use the laboratory virtual network.

Example VM configuration:

- **Network Adapter:** VMware virtual network
- **RAM:** 2048 MB
- **Operating System:** Kali Linux 2026.2

### Step 5. Configure the Kali Linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:


IP Address:    10.0.0.2
Subnet Mask:   255.255.255.0
Gateway:       10.0.0.1
DNS:           8.8.8.8


A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

### Step 6. Create a Clean VM Snapshot

After completing the initial configuration, a VMware snapshot was created.

**Example snapshot name:**

Newly Installed Kali Linux


The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

## 🧪 Lab Verification

| Test | Command | Expected Result |
|---|---|---|
| 🌐 Check IP address | `ip a` | Correct Kali IP displayed |
| 📡 Test gateway | `ping 10.0.0.1` | Successful replies |
| 🌍 Test Internet connectivity | `ping 8.8.8.8` | Successful replies |
| 🔎 Test DNS resolution | `nslookup networkwalks.com` | Domain resolves |
| 🧰 Verify Nmap | `nmap --version` | Nmap version displayed |
| 🔄 Verify snapshot | Restore snapshot and run `ip a` | Baseline configuration restored |

### Example Result


IP Address: 10.0.0.2/24
Gateway:    10.0.0.1
DNS:        8.8.8.8


## ⚠️ Problems Encountered & Solutions

### Problem 1. Internet Connectivity After Static IP Configuration

After manually configuring the IPv4 settings, Internet connectivity may fail depending on the Kali Linux and NetworkManager configuration.

One workaround used during the lab was:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
```

The network connection was then restarted/rebooted and connectivity was tested again.

> The exact connection name may be different on another Kali installation. Check available connections with `nmcli connection show`.

## 📚 What I Learned

Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.

The most important concepts I learned include:

### 1. VMware Virtual Networking

I learned how VMware virtual network adapters allow virtual machines to communicate with each other and/or external networks depending on the selected network configuration.

### 2. Virtual Machine Networking

I learned how virtual network adapters connect VMs to different network configurations and how network settings affect communication.

### 3. Static IP Configuration

I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

### 4. VM Snapshots

I learned that a clean snapshot should be created before performing risky or experimental activities.

This provides a known-good recovery point for future cybersecurity exercises.

### 5. Documentation

I learned that documenting commands, configurations, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

## 🔐 Security & Ethical Use

This laboratory is strictly for **educational purposes and authorized security testing only**.

All scanning, vulnerability assessment, penetration testing, and exploitation activities should be performed only against systems that I own or have explicit permission to test.

## 🛠️ Tools & Resources

- **7-Zip:** https://7-zip.org/download.html
- **VMware Workstation:** https://www.vmware.com/products/desktop-hypervisor/workstation-pro.html
- **Kali Linux:** https://www.kali.org/get-kali/

## 📌 Project Information

**Program:** Cybersecurity at Networkwalks  
**Week:** 01  
**Project:** Cybersecurity & Pentesting Lab Setup  
**Platform:** VMware Workstation + Kali Linux  
**Repository:** GitHub

## 👨‍💻 Author

**Mithilesh Vijay Sonavane**

Cyber Security Student  
B.Voc Cyber Security & Forensic  
LinkedIn Profile: https://www.linkedin.com/in/mithilesh-sonavane-a08766374/

---

⭐ If this project is useful for learning cybersecurity lab setup, feel free to explore the repository and build upon it with additional attacker and target VMs.

