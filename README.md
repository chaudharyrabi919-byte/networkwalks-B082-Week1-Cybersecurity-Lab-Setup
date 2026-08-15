# networkwalks-B082-Week1-Cybersecurity-Lab-Setup
# Cybersecurity Lab Setup
# Project Overview
This project focuses on the design and implementation of a virtual cybersecurity and penetration-testing laboratory using Oracle VM VirtualBox and Kali Linux.

The primary purpose of the laboratory is to establish a controlled, isolated, and repeatable environment in which cybersecurity tools and techniques can be safely studied and tested. The lab supports activities including network reconnaissance, network scanning, vulnerability assessment, security analysis, and other authorized penetration-testing exercises.

The laboratory is configured using a private NAT Network, providing network isolation while allowing additional virtual machines to be introduced in the future as authorized target systems. This architecture enables practical cybersecurity exercises to be conducted without exposing test systems to the external network.

# Objectives

The key objectives of this project are to:

•	Install and configure Oracle VM VirtualBox as the virtualization platform.

•	Install or import Kali Linux as the primary cybersecurity virtual machine.

•	Create and configure a dedicated NAT Network for the virtual cybersecurity laboratory.

•	Configure network connectivity between the Kali Linux virtual machine and the private laboratory network.

•	Assign a consistent IP address to the Kali Linux virtual machine for reliable laboratory operations.

•	Verify network connectivity, gateway communication, and DNS resolution.

•	Create a clean virtual machine snapshot to provide a reliable recovery point.

•	Document the complete laboratory setup and configuration process.

•	Establish a scalable environment for future cybersecurity and penetration-testing projects.

# Purpose of the Laboratory

The laboratory provides an isolated and controlled environment for cybersecurity education, experimentation, and authorized security testing. By using virtual machines and a private virtual network, security activities can be performed safely without intentionally affecting production systems or unauthorized networks.

The laboratory can support practical exercises such as:

•	Network reconnaissance and information gathering

•	Port and service scanning

•	Vulnerability assessment

•	Packet capture and network traffic analysis

•	Web application security testing

•	Controlled exploitation and penetration-testing exercises

•	Cybersecurity tool evaluation and experimentation

•	Security configuration testing

•	Incident investigation and defensive security exercises

# Lab Architecture

<img width="959" height="503" alt="image" src="https://github.com/user-attachments/assets/89df6645-0d40-4c94-bb93-f44c17749680" />

# Cybersecurity Laboratory Configuration

Host Operating System: Windows 10

Host RAM: 8 GB

Processor: Intel Core i7

Hypervisor: VirtualBox 7.2

Security Operating System: Kali Linux 2026.2

Kali Linux RAM: 2048 MB (2 GB)

Virtual Network: NAT Network

Network Address: 10.0.0.0/24

Kali Linux IP Address: 10.0.0.2/24

Default Gateway: 10.0.0.1

DNS Server: 8.8.8.8

Future Virtual Machine IP Range: 10.0.0.3–10.0.0.99

# Lab Setup Procedure

Step 1: Install 7-Zip

Download & install 7-zip: https://7-zip.org/download.html

Step 2: Install VirtualBox

Download & install Virtualbox on your laptop/PC: https://virtualbox.org/wiki/Downloads

Step 3: Create the NAT Network

Create a dedicated NAT Network in VirtualBox with:

Network Name: NatNetwork

IPv4 Prefix: 10.0.0.0/24

DHCP: Enabled

IPv6: Disabled

<img width="958" height="503" alt="image" src="https://github.com/user-attachments/assets/b87430af-c266-4aaf-a9dc-c67ef705259a" />

Step 4: Import Kali Linux

The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.
The VM network adapter was configured as follows:

Adapter 1

Attached to: NAT Network

Network:     NatNetwork

Adapter Type: Intel PRO/1000 MT Desktop

The VM was allocated:

RAM: 2048 MB

<img width="1281" height="923" alt="image" src="https://github.com/user-attachments/assets/9e8f65d4-3350-4b9e-b750-0fc0989356c9" />

Step 5. Configure the Kali Linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:

IP Address: 10.0.0.2

Subnet Mask: 255.255.255.0

Gateway: 10.0.0.1

DNS: 8.8.8.8

A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

<img width="1275" height="920" alt="image" src="https://github.com/user-attachments/assets/c126fa67-d270-4ccd-8901-0e22b87d4d30" />

Step 6. Create a Clean VM Snapshot

After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:

Clean Kali - Network Setup

The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

# Lab Verification

1. Check IP Address
2. 
ip a

4. Test Gateway
5. 
ping 10.0.0.1

7. Test Internet Connectivity
8. 
ping 8.8.8.8

10. Test DNS Resolution
11. 
nslookup networkwalks.com

13. Verify Nmap
14. 
nmap --version

16. Verify Snapshot
17. 
Restore the snapshot and run:

ip a

# Problems Encountered & Solutions

Problem 1 . Internet connectivity After Static IP Configuratin
After Manually configuring the IPV4 settings, internet connectivity may fail depending on the kali/NetworkManager configuration.

One workaround used during this lab was:

sudo nmcli connection modify "Wired connection 1" ipv4.dad-time0.

this network connection was then restarted/rebooted and connectivity was tested again.

Problem 2. VirtualBox VT-x/Virtualization Error

The VM initially failed to start because hardware virtualization was disabled in the system firmware/Bios.

The issue was resolved by:

1.Restarting the computer.

2.Entering BIOS/UEFI settings.

3.Enabling intel VT-x / hardware virtualization.

4.Saving the configuration.

5.Restarting the computer.

6.Starting the kali VM again.

# What i learned ?

Through this project , i learned how to create and configure a virtual environment for cybersecurity practice.
The most important concepts i learned include:

1.NAT VS NAT Network

2.Virtual Machine Networking

3.Static IP Configuration

4.VM Snapshots

5.Documentation

# Author

linkedIn:https://www.linkedin.com/feed/

















