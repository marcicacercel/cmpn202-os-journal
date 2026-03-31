# Phase 1 (Week 1) - System Planning and Setup

## 1. System Architecture
The system consists of my Windows laptop acting as the host machine and a virtual machine running Ubuntu Server 24.04 LTS inside Oracle VirtualBox.
I created a virtual machine named OSserver, allocating 4GB RAM and 2 CPU cores, which is sufficient for a lightweight server environment. The server runs in a headless (CLI-only) mode, meaning there is no graphical interface and all interaction is done through the terminal. This setup reflects a real-world server environment, where systems are typically accessed remotely and managed via command-line tools rather than a desktop interface.

<img width="1600" height="1154" alt="Screenshot 2026-03-29 213127" src="https://github.com/user-attachments/assets/492193a5-c4f6-4a96-a7aa-07dfcd34e079" />
<br><br>
The following figure shows the system architecture which I used in this phase. The Windows host machine acts as the workstation, Oracle VirtualBox provides the virtualization layer, and Ubuntu Server 24.04 LTS runs as a headless server VM. The server uses NAT networking, which automatically assigned the IP address 10.0.2.15 and allowed internet access for updates and package installation.

![ArchD](https://github.com/user-attachments/assets/ee22cd16-1b47-49b6-b9c5-e2702bb96e43)

## 2. Distribution Selection
I selected Ubuntu Server 24.04 LTS because it provides long-term support (5 years), making it stable and suitable for server deployments. Compared to Debian, Ubuntu offers easier initial configuration and better documentation, which helped during setup. Compared to Rocky Linux / CentOS, Ubuntu has a more beginner-friendly package management system (apt) and a larger community, making troubleshooting easier. This makes Ubuntu a practical choice for both learning and real-world system administration tasks.
## 3. Workstation Configuration
My Windows machine acts as the workstation, meaning it is used to control and interact with the server. Instead of using a second virtual machine, I chose this setup to keep things simple. The server runs inside VirtualBox, and I access it directly through the VM console. Later, this setup can be extended to use SSH for remote access. This approach reduces complexity while still meeting the requirement of separating the server environment from the main system.
## 4. Network Configuration
The virtual machine is configured using NAT (Network Address Translation) in VirtualBox.
With NAT:
- The VM shares the host’s internet connection
- The IP address is assigned automatically via DHCP

From the ip a command, the server received the following IP address: *10.0.2.15*

This confirms that:
- The network interface (enp0s3) is active
- The server has internet connectivity
- The VM is correctly integrated into the VirtualBox virtual network
This setup allows the server to install updates and communicate externally without additional configuration.
<img width="827" height="257" alt="ipAcommandOnly" src="https://github.com/user-attachments/assets/b0f737c3-7f9c-4f4b-9c42-b055cdafaee5" />
&nbsp;
## 5. System Information (CLI Evidence)
**System Kernel**
This screenshot shows the output of the uname -a command.
It confirms:
- The system is running Linux kernel 6.8.0-106-generic
- The architecture is x86_64 (64-bit)
- The kernel is part of Ubuntu’s official build
This verifies that the system is correctly installed and running a modern Linux kernel suitable for server workloads.

<img width="1009" height="188" alt="uname-aCommandOn;y" src="https://github.com/user-attachments/assets/1211137c-a84d-46da-9e39-3264452ed68e" />
&nbsp;

**OS Version**
This output is from the lsb_release -a command.
It confirms the following:
- Distribution: Ubuntu
- Version: 24.04.4 LTS
- Codename: noble
This proves that the correct server version of Ubuntu was installed and that it is an LTS release, which is important for stability and long-term updates.

<img width="317" height="113" alt="lsbCommand" src="https://github.com/user-attachments/assets/1016ce6c-7a9f-4419-806c-9af3cc9d6ca5" />
<br><br>

**Network Information**
This screenshot shows the result of the ip a command.
Key observations:
- Interface enp0s3 is active (UP)
- IPv4 address: 10.0.2.15/24
- Loopback interface (lo) is also present and functioning
This confirms that networking is properly configured and the server can communicate within the virtual network and access external resources.
<img width="827" height="257" alt="ipAcommandOnly" src="https://github.com/user-attachments/assets/b0f737c3-7f9c-4f4b-9c42-b055cdafaee5" />
<br><br>

**Memory Usage**
This output comes from the free -h command.
It shows:
- Total RAM: 3.8GB
- Used memory: ~401MB
- Available memory: ~3.4GB
This indicates that the system is running efficiently with low memory usage, which is expected for a minimal server installation without a graphical interface.

<img width="669" height="81" alt="freeHCommand" src="https://github.com/user-attachments/assets/7ebe798c-e757-4e32-985d-a789fe91dbef" />
<br><br>

**Disk Usage**
This screenshot shows the output of the df -h command.
It confirms:
- Root partition size: 12GB
- Used space: 4.9GB (46%)
- Available space: 5.8GB
The disk is managed using LVM (Logical Volume Manager), which provides flexibility for resizing storage in the future. This shows that the system has enough available storage and is correctly partitioned.
<img width="580" height="142" alt="dfHCommand" src="https://github.com/user-attachments/assets/76e6a011-e0a3-41c5-8362-26c44e29eddd" />
&nbsp;

## 6. Reflection
This week I successfully installed and configured an Ubuntu Server inside a virtual machine and learned how to work entirely through the command line.

At the beginning, I found the lack of a graphical interface challenging, but it helped me better understand how Linux systems operate at a lower level. I also learned how to retrieve system information using commands like uname, lsb_release, ip, free, and df, which are essential for system monitoring.

Setting up networking using NAT in VirtualBox helped me understand how virtual machines communicate and obtain IP addresses. Overall, this process gave me a solid foundation in Linux server setup and basic system administration.
