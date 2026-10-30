# NETWORKWALKS--CLARK-B084-WK1-CYBERSECURITY-LAB-SETUP

# 🚀 Cybersecurity Lab Setup

*Building a safe, local sandbox for ethical hacking and networking practice.*

---

## 📌 Project Overview

This project sets up an **isolated virtual laboratory** using **VirtualBox** and **Kali Linux**. It creates a secure sandbox environment where you can practice network scanning, reconnaissance, and security testing without risking your main computer or external systems.

---

## ⚙️ Lab Environment Summary

* **Host Machine:** Windows 10 (Intel Core i5-7300, 8 GB RAM)
* **Hypervisor:** VirtualBox 7.2
* **Security OS:** Kali Linux 2026.2 (Assigned 2048 MB RAM)
* **Networking Mode:** NAT Network (`10.0.0.0/24`)
* **Static Kali IP:** `10.0.0.2/24`
* **Gateway & DNS:** `10.0.0.1` (Gateway) | `8.8.8.8` (DNS)

---

## 🪜 Step-by-Step Implementation

1. **Prepare Tools:** Installed **VirtualBox** as the virtualization engine to run virtual machines.
2. **Extract Kali Linux:** Downloaded the Kali Linux VM package and used **WinRAR** to extract the archive. *(Note: WinRAR was used solely for the Kali image, not for VirtualBox!)*
3. **Configure the Virtual Network:** Created a dedicated `NatNetwork` (`10.0.0.0/24`) with DHCP enabled inside VirtualBox. This allows future virtual machines to talk to each other while still accessing the internet.
4. **Import Kali Linux:** Imported the extracted Kali machine into VirtualBox, linked its network adapter to the new NAT Network, and set up a shared folder for easy file transfers with Windows.
5. **Set a Static IP:** Assigned a fixed IPv4 address (`10.0.0.2`) to Kali so it always stays at the same address during your labs and coursework documentation.
6. **Save a Baseline Snapshot:** Created a clean VirtualBox snapshot named `Clean Kali - Setup`. If anything ever breaks during your practice, you can instantly roll back to this fresh state!

---

## 🐞 Troubleshooting & Common Fixes

* **NetworkManager DAD Timeout:** If static IP configuration causes connection delays or drops, you can fix it by adjusting the duplicate address detection timeout in the terminal:
```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

```


* **Virtualization Error:** If the virtual machine fails to boot immediately, restart your PC, enter your **BIOS/UEFI settings**, and make sure **Intel VT-x / Hardware Virtualization** is turned on.

---

## 👤 Project Metadata

* **Author:** Kaliwabo Nshuti Clark
* **Focus:** Network Fundamentals & Cybersecurity Lab Architecture
* **Tools Used:** VirtualBox, Kali Linux, WinRAR, Networking CLI Tools (`nmcli`, `ip`), Bash

---
