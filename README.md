# Home-Lab

## Project Overview:
This project aims to create a **Network Security Homelab** for learning and testing network security concepts using **VirtualBox**, **OPNSense**, **Wireshark**, and **Ubuntu**. The objective was to simulate network environments, capture network traffic, and analyze it for potential security vulnerabilities. Along the way, I encountered several challenges that allowed me to gain hands-on experience with network troubleshooting, firewall configurations, and network analysis.

## Technologies Used:
- **VirtualBox**: Virtualization software used to create and manage the virtual machines (VMs).
- **OPNSense**: Open-source firewall/router software used to simulate network security features.
- **Wireshark**: Network protocol analyzer for capturing and analyzing network traffic.
- **Ubuntu**: Linux-based operating system used as a client to interact with the network.

## Objective
**Network Security Setup:** Simulate a network environment with Ubuntu and OPNSense.
**Packet Capture and Analysis:** Use Wireshark to capture packets and analyze traffic between Ubuntu and OPNSense.
**Network Troubleshooting:** Resolve installation and configuration issues with VirtualBox, OPNSense, and Ubuntu networking.

## Setup Guide

### 1. Install VirtualBox
   - Download and install VirtualBox from [VirtualBox Download](https://www.virtualbox.org/).
   - Choose the version appropriate for your operating system (Windows, macOS, or Linux).

### 2. Create Virtual Machines
   - **Ubuntu**: Create a new VM in VirtualBox with Ubuntu as the operating system. Allocate sufficient resources (e.g., 2GB RAM, 20GB storage).
   - **OPNSense**: Create a VM for OPNSense using the downloaded pfSense ISO. Allocate at least 1GB of RAM and configure network adapters as required.

### 3. Configure Networking in VirtualBox
** Ubuntu VM:** Configure Adapter 1 to use the NAT and adapter 2 to use the Internal Network for communication with OPNSense.
**OPNSense VM**: Configure Adapter 1 to use NAT (to get internet access) and Adapter 2 to use the Internal Network (to communicate with Ubuntu). This allows the Ubuntu VM to be connected to the OPNSense firewall/router for traffic routing.

- Network Setup:
**OPNsense VM has:**
  Adapter 1: NAT (provides internet access to the OPNsense VM).
  Adapter 2: Internal Network (for communication with the Ubuntu VM).
**Ubuntu VM has:**
Adapter 1: Internal Network (to communicate with OPNsense).

- OPNsense and Ubuntu can communicate over the Internal Network while the OPNsense VM has internet access through the NAT adapter.

<img width="500" alt="Ubuntu Network Configuration" src="https://github.com/user-attachments/assets/aada855b-7920-4aa3-b01c-b6d69fce17f2" />

<img width="500" alt="OPNSense Network Configuration" src="https://github.com/user-attachments/assets/09b85b9b-be47-42ee-9ef2-fa694aa3c120" />

<img width="500" alt="OPNSense Network Configuration" src="https://github.com/user-attachments/assets/320c9f36-5968-47ec-be7d-19b9536f1635" />


### 4. Install OPNSense on VirtualBox
   - Boot the OPNSense VM with the OPNSense ISO image.
   - Follow the installation prompts to complete the OPNSense setup. (In case OPNSense fails to reboot, refer to troubleshooting steps below.)
   - Using command to decompress the .bz2 file (on MAC) using the teminal:
     <img width="300" alt="Terminal" src="https://github.com/user-attachments/assets/821bdd04-75df-4b61-9df7-3c3bfd50400e" />
     

### 5. Install Wireshark on Ubuntu
   - Install Wireshark in Ubuntu by running:
     sudo apt update (to update the software)
     sudo apt install wireshark (to install the software)
     
     <img width="450" alt="Installation of Wireshark within Ubuntu" src="https://github.com/user-attachments/assets/124a67b7-34ec-498e-aa12-46d0dd4c63ac" />
   - Run Wireshark to start capturing network traffic on the configured interfaces.

   - Desktop Environment:

  <img width="600" alt="Desktop" src="https://github.com/user-attachments/assets/53a305f4-cf74-4c8d-a586-5bc83d078012" />



## Troubleshooting Steps

### Issue 1: OPNSense Installation Issues
- **Problem**: After downloading the OPNsense installation image, I encountered an issue where the downloaded file was in a compressed .bz2 format. This meant that the image file couldn’t be used directly for installation, as it needed to be decompressed first.
- **Solution**: 
   To resolve this, I used the macOS terminal to navigate to the directory where the installation image was saved. The following steps were taken:
1. Navigating to the Download Directory:
I opened the terminal and used the cd command to move into the "Downloads" folder where the OPNsense image was located.
- The command used was:
- cd ~/Downloads (move through the directory)
- bunzip2 opnsense-image.bz2

3. Decompressing the .bz2 File:
Once inside the correct directory, I ran the bunzip2 command to decompress the .bz2 file, which extracted the ISO image file needed for the installation:

This step successfully extracted the OPNsense installation image, allowing me to proceed with creating a bootable installation drive or using the image in a virtual environment.

## What I Accomplished
- **Network Security Setup**: Successfully set up Ubuntu and pfSense (or OPNsense) to create a virtualized network environment.
- **Wireshark Traffic Analysis**: Captured and analyzed network traffic to identify potential security vulnerabilities or misconfigurations.
- **Network Troubleshooting**: Gained experience in solving common networking issues related to virtual machines and firewall configurations.

## Helpful Resources:
- [Homelab Setup Guide](https://www.youtube.com/watch?v=kku0fVfksrk)
 _This video helped me understand what a homelab is and to setup the environment._

-  [Networking Basics for Homelab](https://www.youtube.com/watch?v=5iafC6vj7kM&t=312s)  
  _This video was useful for configuring networking in my lab._

