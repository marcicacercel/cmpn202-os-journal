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
<img width="827" height="257" alt="ipAcommandOnly" src="https://github.com/user-attachments/assets/b0f737c3-7f9c-4f4b-9c42-b055cdafaee5" />
&nbsp;
## 5. System Information (CLI Evidence)
**System Kernel**

<img width="1009" height="188" alt="uname-aCommandOn;y" src="https://github.com/user-attachments/assets/1211137c-a84d-46da-9e39-3264452ed68e" />
&nbsp;

**OS Version**

<img width="317" height="113" alt="lsbCommand" src="https://github.com/user-attachments/assets/1016ce6c-7a9f-4419-806c-9af3cc9d6ca5" />
<br><br>

**Network Information**

<img width="827" height="257" alt="ipAcommandOnly" src="https://github.com/user-attachments/assets/b0f737c3-7f9c-4f4b-9c42-b055cdafaee5" />
&nbsp;

**Memory Usage**

<img width="669" height="81" alt="freeHCommand" src="https://github.com/user-attachments/assets/7ebe798c-e757-4e32-985d-a789fe91dbef" />
&nbsp;

**Disk Usage**

<img width="580" height="142" alt="dfHCommand" src="https://github.com/user-attachments/assets/76e6a011-e0a3-41c5-8362-26c44e29eddd" />
&nbsp;

## 6. Reflection
This week I successfully installed and configured an Ubuntu Server in a virtual environment. I learned how to interact with a Linux system using the command line and understand basic system information. The setup process also helped me understand virtualization and networking concepts.


