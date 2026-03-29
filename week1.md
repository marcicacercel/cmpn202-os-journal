# Phase 1 (Week 1) - System Planning and Setup

## 1. System Architecture
The system consists of a host machine (Windows) and a virtual Ubuntu Server running in VirtualBox. 
The server is configured without a graphical interface and is accessed through the command line.



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
