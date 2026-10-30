# NETWORKWALKS-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP-SAMPLE
cybersecurity lab setup

# 🔐 Cybersecurity Lab Environment Setup

**Building an isolated virtual lab for penetration testing and ethical hacking practice**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Waqas%20Karim%20CCIE-C00000?style=flat-square" />
</p>

## Project Overview

This project documents the setup of a Kali Linux virtual machine using Oracle VirtualBox. It is my first project as an intern at NetworkWorks and serves as the foundation for the cybersecurity and networking projects that follow.

## Objective

The main objective of this project is to build a stable, isolated Kali Linux environment that can be used safely for learning and practising networking and security tasks.

Specific goals:

- Install and configure Oracle VirtualBox on a Windows host.
- Create and configure a Kali Linux virtual machine.
- Configure virtual networking so the VM has working internet access.
- Assign a consistent IP for the kali linux
- Troubleshoot and resolve installation and startup problems.
- Document the full process so it can be repeated by others.

## Environment and Specifications

- Host operating system: Windows
- Hypervisor: Oracle VirtualBox
- Guest operating system: Kali Linux (64-bit, installer ISO)
- Base memory: 4096 MB
- Processors: 2
- Virtual disk: 25 GB (VDI)
- Graphics controller: VMSVGA, 128 MB video memory
- Network: NAT (Adapter 1)

## 🛡️ Purpose of the Lab

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Exploitation practice
- Security-tool experimentation



## 🏗️ Lab Architecture


Additional target machines can be added to the same virtual network in future projects.

---

## ⚙️ Lab Configuration

| 🧩 Component       | ⚙️ Configuration   |
| ------------------ | ------------------  |
| 🖥️ Host OS         | Windows 11        |
| 🧠 Host RAM        | 8 GB               |
| ⚡ Processor       | Intel Core i5     |
| 🧰 Hypervisor      | VirtualBox 7.2  |
| 🐉 Security OS     | Kali Linux 2026.2  |
| 🧠 Kali RAM        | 2048 MB            |
| 🌐 Virtual Network | NAT Network        |
| 📡 Network Address | 10.0.0.0/24        |
| 🐧 Kali IP Address | 10.0.0.2/24        |
| 🚪 Default Gateway | 10.0.0.1           |
| 🌍 DNS Server      | 8.8.8.8            |
| 🔮 Future VM Range | 10.0.0.3–10.0.0.99 |

<img width="1600" height="900" alt="Screenshot (99)" src="https://github.com/user-attachments/assets/1362311b-e522-4197-80bd-3a5d92fb15e7" />

![](2-screenshot-network-settings-1.png)

## Step 1. Install 7-Zip

7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a `.7z` archive.

**Tool:** 7-Zip

---

## Step 2. Install VirtualBox

VirtualBox was installed as the hypervisor.

---

## Step 3. Create the NAT Network

A dedicated NAT Network was created in VirtualBox.

Configuration:
Network Name: NatNetwork
IPv4 Prefix:  10.0.0.0/24
DHCP:         Enabled
IPv6:         Disabled
<img width="1600" height="900" alt="Screenshot (97)" src="https://github.com/user-attachments/assets/45223a3c-b322-44fa-8550-c73d175b02d1" />

A **NAT Network** was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.


## Step 4. Import Kali Linux

The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:

```text
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```

The VM was allocated:

```text
RAM: 2048 MB
```
<img width="1200" height="600" alt="Screenshot_2026-10-30_07-14-24" src="https://github.com/user-attachments/assets/ac686c5b-8f2e-44b8-b93e-ee3235f12a8c" />
A shared folder was also configured for transferring required files between the host operating system and the Kali VM.


## Step 5. Configure the Kali Linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:

```text
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.
<img width="701" height="550" alt="Screenshot_2026-10-29_19-41-06" src="https://github.com/user-attachments/assets/1b7a1d18-8424-4c79-aff2-6e1f12721cd0" />

## Step 6. Create a Clean VM Snapshot

After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:

```text
Clean Kali - Network Setup
```

The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.


---

# 🔎 Lab Verification

| ✅ Test                        | 🧾 Command                      | 🎯 Expected Result              |
| ----------------------------- | ------------------------------- | ------------------------------- |
| 🌐 Check IP address           | `ip a`                          | Correct Kali IP displayed       |
| 📡 Test gateway               | `ping 10.0.0.1`                 | Successful replies              |
| 🌍 Test Internet connectivity | `ping 8.8.8.8`                  | Successful replies              |
| 🔎 Test DNS resolution        | `nslookup networkwalks.com`     | Domain resolves                 |
| 🧰 Verify Nmap                | `nmap --version`                | Nmap version displayed          |
| 🔄 Verify snapshot            | Restore snapshot and run `ip a` | Baseline configuration restored |

### Example Results

```text
IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8
```
## Challenges and Solutions

### 1. VirtualBox error: Driver name clash (VERR_PDM_USB_NAME_CLASH)

- **Problem:** The VM aborted at startup with a USB driver name clash error, and the USB controller setting kept turning itself back on.
- **Cause:** A conflict between the USB driver and the VirtualBox Extension Pack.
- **Solution:** Uninstalled the Extension Pack, disabled the USB controllers for the VM, and restarted VirtualBox.


## Outcome

A working Kali Linux virtual machine with internet access, ready to be used for upcoming NetworkWalks projects.

## Lessons Learned

- Always match the VirtualBox Extension Pack version to the VirtualBox version.
- Record errors and fixes as they happen, because they make useful documentation.

# 🔐 Security & Ethical Use

This laboratory is intended strictly for education purposes only.

---

# 🔗 Tools & Resources

- **7-Zip:** [https://7-zip.org/download.html](https://7-zip.org/download.html)
- **VirtualBox:** [https://virtualbox.org/wiki/Downloads](https://virtualbox.org/wiki/Downloads)
- **Kali Linux:** [https://kali.org/get-kali](https://kali.org/get-kali)

---

## Author

Banty, cybersecurity intern at networkwalks B084
www.linkedin.com/in/akinseinde-tolulope


## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub


