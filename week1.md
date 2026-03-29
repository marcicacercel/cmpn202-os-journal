# Phase 1 (Week 1) - System Planning and Setup

## 1. System Architecture
The system consists of a host machine (Windows) and a virtual Ubuntu Server running in VirtualBox. 
The server is configured without a graphical interface and is accessed through the command line.
<img width="1600" height="1154" alt="Screenshot 2026-03-29 213127" src="https://github.com/user-attachments/assets/492193a5-c4f6-4a96-a7aa-07dfcd34e079" />

## 2. Distribution Selection
Ubuntu Server 24.04 LTS was selected due to its long-term support, stability, and strong community 
support. Compared to Debian, it provides more user-friendly configuration. Compared to CentOS/Rocky, 
it is easier to manage for beginners.
## 3. Workstation Configuration
The host Windows machine is used as the workstation. This simplifies the setup and allows direct 
interaction with the virtual server.
## 4. Network Configuration
The virtual machine uses NAT networking in VirtualBox. The server automatically receives an IP 
address (10.0.2.15), allowing it to access the internet through the host system.
<img width="1280" height="800" alt="ipAcommand" src="https://github.com/user-attachments/assets/3af44efe-55a3-45e4-be82-1848f907cc14" />
## 5. System Information (CLI Evidence)
**System Kernel**
<img width="1280" height="800" alt="uname-aCommand" src="https://github.com/user-attachments/assets/fa5f3d51-87dd-459a-9d31-e7f406617a68" />
**OS Version**


**Network Information**

**Memory Usage**

**Disk Usage**


## 6. Reflection
This week I successfully installed and configured an Ubuntu Server in a virtual environment. I learned how to interact with a Linux system using the command line and understand basic system information. The setup process also helped me understand virtualization and networking concepts.


