# Phase 2 (Assesment Week 2) - Security Planning And Testing Methology
## 1. Performance Testing Plan
In this phase, I designed a simple testing approach to monitor how the server behaves under normal usage. Since the system is running without a graphical interface, all monitoring is done using command-line tools.

To observe system performance, I focused on three main areas:
- CPU usage
- Memory usage
- Disk activity

I used built-in Linux tools such as:
- top – to monitor real-time CPU and process usage
- free -h – to check memory consumption
- df -h – to analyse disk usage

The plan is to run these commands before and during activity (e.g. installing packages or running services) and compare the results. This allows me to understand how different workloads affect system resources.
Since the coursework requires remote monitoring, this setup will later be extended using SSH, allowing the server to be monitored from the host machine without opening the VirtualBox console.

## 2. Security Configuration Checklist
To secure the server, I created a checklist covering the main areas required in the brief.
<br><br>

**2.1 SSH Hardening**

I installed the OpenSSH server to allow remote access using the folowing command:
*sudo systemctl status ssh*\
After installation, I verified that the SSH service was running:
*sudo ufw allow OpenSSH*\
This ensures the server can accept remote connections. Alos, to improve securit, I will later perform these actions:
- Disable root login
- Disable password authentication (use SSH keys instead)
- Change default SSH settings if needed\
Initially, after installing OpenSSH, the SSH service was not running, as shown by the inactive (dead) status. This meant that the server was not accepting remote connections. To resolve this, I manually started the SSH service using systemctl start ssh and enabled it to start automatically on boot using systemctl enable ssh. After this, the service status changed to active (running), confirming that SSH is now correctly configured.
<br><br>

**2.2 Firewall Configuration**

To improve the security of the server, I configured a firewall using UFW (Uncomplicated Firewall). This allows me to control which network connections are permitted and helps protect the system from unauthorised access.\
First, I allowed SSH connections to ensure I would not lose remote access to the server:\
*sudo ufw allow OpenSSH*\
This step is important because enabling the firewall without allowing SSH could block remote access completely.Next, I enabled the firewall:\
*sudo ufw enable*\
After enabling it, I checked the firewall status:\
*sudo ufw status*\
The output confirms that the firewall is active and that SSH connections are allowed. This means the system is now protected by default, only permitting explicitly allowed traffic.\

<img width="672" height="385" alt="image" src="https://github.com/user-attachments/assets/bc72972f-dcd7-4e43-861e-18e6a6b034c1" />
<br><br>

**2.3 Automatic Updates**

To keep the system secure, I installed automatic updates using the following commands:
*sudo apt install unattended-upgrades\
sudo dpkg-reconfigure unattended-upgrades*\
This ensures that security patches are applied automatically without manual intervention.\
To improve system security, I configured automatic updates using the unattended-upgrades package. This ensures that critical security patches are applied without manual intervention.\
I installed and configured the service using the following commands:
*sudo apt install unattended-upgrades -y\
sudo dpkg-reconfigure -f noninteractive unattended-upgrades*\
After configuration, I verified the status of the service by running the following command: *sudo systemctl status unattended-upgrades*\
The output shows that the service is active (running) and enabled, meaning it will automatically apply updates in the background. This reduces the risk of vulnerabilities caused by outdated software and ensures the system remains secure over time.
<br><br>

**2.4 User Privilege Management**

The server uses a non-root user- marcicac for normal operations.\
Administrative tasks are performed using *sudo*. This reduces the risk of accidental system damage and follows best practices by avoiding direct root usage.\
To confirm that my user account has administrative privileges, I used the whoami command to verify the current logged-in user. The output showed my username (marcicac), confirming that I am operating as a standard user rather than root. I then used the following command to check my sudo permissions: *sudo -l*\
This command lists the administrative privileges assigned to the current user. It confirmed that my account is allowed to execute commands with elevated privileges using sudo. This approach improves system security by avoiding direct root login while still allowing controlled administrative access.

<img width="1526" height="245" alt="Screenshot 2026-03-31 203217" src="https://github.com/user-attachments/assets/aad3db84-3d8d-451a-850d-36fcf4ef4b8c" />
<br><br>

**2.5 Network Security**

The server is running behind a NAT network, which already provides a basic level of isolation.
Key points:
- The server is not directly exposed to external networks
- It only communicates through the host system
- External access requires explicit configuration (e.g. port forwarding)\
This setup reduces exposure to external attacks during initial configuration.

## 3. Thread Model

I identified several realistic security threats and how they can be mitigated.\
**Threat 1: Unauthorized SSH Access (Brute Force Attack)**\
  Attackers may attempt to guess login credentials through repeated login attempts.
  Mitigation:
  - Disable password authentication
  - Use SSH key-based authentication
  - Configure firewall rules to limit access\
**Threat 2: Unpatched System Vulnerabilities**\
  If the system is not updated regularly, it may contain known vulnerabilities.
  Mitigation:
  - Enable automatic updates
  - Regularly check for upgrades using\
**Threat 3: Misconfigured Firewall**\
  If the firewall is not properly configured, unnecessary ports may remain open.
  Mitigation:
  - Use ufw to restrict traffic
  - Only allow required services (e.g. SSH)
  - Periodically check rules using

## 4. CLI Evidence

**SSH Installation Verification**\



**Firewall Status**\


**Automatic Updates Setup**\



## 5.Reflection

This week helped me understand how to secure a Linux server beyond basic installation. Instead of just running commands, I learned why each configuration is important. Setting up SSH made me realise how servers are typically accessed remotely, and why securing it is critical. Configuring the firewall showed how easily a system can be exposed if rules are not properly defined. I also understood the importance of keeping systems updated, as outdated software can become a major security risk. Overall, this week moved my understanding from simply using Linux commands to thinking more like a system administrator responsible for securing a server.

  


