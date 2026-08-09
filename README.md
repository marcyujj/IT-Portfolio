# IT-Portfolio
Hands on IT labs, troubleshooting projects, and CompTIA A+ home lab documentation
# 👋 Welcome to My IT Portfolio

Hi, I'm Jean.

I'm currently studying for the CompTIA A+ certification while building hands-on IT experience through home labs and personal projects. I enjoy learning how computers and networks work, troubleshooting problems, and documenting what I learn along the way.

This portfolio is where I share the projects I've completed, the challenges I ran into, and the solutions I found. My goal is to continue improving my skills and begin my career in IT support.

## 🎯 Current Goal

Build a strong foundation in IT through hands-on practice and earn my first Help Desk or IT Support role.

## 🛠 Skills

- Windows 10 & Windows 11
- Networking Fundamentals
- TCP/IP
- DNS
- DHCP
- VirtualBox
- Hardware Troubleshooting
- Windows Server (Learning)
- Active Directory (Learning)

## 📂 Projects
### Lab 1: Windows Server Network Configuration and Connectivity Testing
### Windows Server 2022 Network Connectivity Lab

For my first home lab, I installed Windows Server 2022 in Oracle VirtualBox and practiced checking its network configuration. My goal was to understand how an IT support technician can narrow down the cause of a connection problem instead of changing settings at random.

**Lab environment**

* Windows Server 2022 Standard Evaluation
* Oracle VirtualBox
* NAT network connection
* Windows PowerShell

**What I did**

I started with `ipconfig /all` to identify the server’s IP address, subnet mask, default gateway, DNS server, DHCP status, and MAC address.

I then tested each part of the connection:

powershell
ping 127.0.0.1
ping 10.0.2.2
ping 8.8.8.8
nslookup google.com



* `ping 127.0.0.1` confirmed that the server’s TCP/IP stack was working.
* `ping 10.0.2.2` confirmed communication with the virtual default gateway.
* `ping 8.8.8.8` confirmed that the server could reach an external internet address.
* `nslookup google.com` confirmed that DNS could translate a domain name into an IP address.

#### Troubleshooting experience

While working through this lab, my virtual machine froze and stopped responding. Since I had already created a snapshot, I powered off the VM, restored the last working snapshot, and started it again. Once Windows Server loaded, I repeated the network tests to make sure everything was still working correctly.

This helped me understand the value of creating snapshots before making changes. If something goes wrong, I can return to a working version of the virtual machine instead of starting the entire setup over.


**Result**

All connectivity tests passed with no packet loss. The server successfully communicated with itself, its default gateway, an external IP address, and its configured DNS server.

**What I learned**

This lab helped me understand how to troubleshoot a network connection in stages. Testing the local computer, gateway, internet connection, and DNS separately makes it easier to identify where a problem is occurring.




## 📜 Certification

- CompTIA A+ (In Progress)

Thanks for visiting my portfolio!

