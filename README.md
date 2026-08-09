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

lab 1 testing results images

https://github.com/marcyujj/IT-Portfolio/blob/e751aedf54b608cd891dd81009c1bbd224c5bbf1/Screenshot%202026-08-05%20114830.png
https://github.com/marcyujj/IT-Portfolio/blob/6cd283c6fada5b21622d2f266fc6a72c8fd1c44d/Screenshot%202026-08-05%20115109.png

### Lab 2: Windows Server Naming and Static IP Configuration

For this lab, I prepared my Windows Server for future Active Directory and domain-management projects. My goal was to give the server a clear name and a consistent IP address so it could be identified and reached reliably on the network.

**Lab environment**

* Windows Server 2022 Standard Evaluation (Desktop Experience)
* Oracle VirtualBox
* VirtualBox NAT networking
* Server Manager
* Windows PowerShell

**What I did**

I started by creating a snapshot of the working virtual machine. This gave me a recovery point before changing the server’s name and network configuration.

Using Server Manager, I renamed the server to `LAB-DC01`. The name identifies it as the first domain controller planned for my lab environment. After restarting Windows Server, I confirmed that the new name was applied successfully.

Next, I used `ipconfig /all` to record the server’s DHCP-assigned network settings. I then manually configured the server with the following static IPv4 information:

* IP address: `10.0.2.15`
* Subnet mask: `255.255.255.0`
* Default gateway: `10.0.2.2`
* Preferred DNS server: `192.168.1.1`

I used the following commands to verify the changes and test connectivity:

```powershell
hostname
ipconfig /all
ping 10.0.2.2
ping 8.8.8.8
nslookup google.com
```

* `hostname` confirmed the new server name.
* `ipconfig /all` showed the static IP information and confirmed that DHCP was disabled.
* `ping 10.0.2.2` confirmed communication with the virtual default gateway.
* `ping 8.8.8.8` confirmed external network connectivity.
* `nslookup google.com` confirmed that DNS name resolution was working.

#### Screenshots

**Server name**

![Server Manager showing LAB-DC01](https://github.com/marcyujj/IT-Portfolio/blob/3c18dbcfdcddcaa7ec4552962384a6311685b5bd/Screenshot%202026-08-08%20210410.png)

**Static IPv4 configuration**

![Windows Server static IPv4 settings](images/lab-02/static-ip-configuration.png)

**Network verification**

![Static IP and connectivity test results](https://github.com/marcyujj/IT-Portfolio/blob/de11b78e05f9e44032d3816ab08a7c233764b104/Screenshot%202026-08-08%20210716.png)
https://github.com/marcyujj/IT-Portfolio/blob/2db159cc0ecef9fddc6c92f7957f054b672f49fd/Screenshot%202026-08-08%20210856.png

#### Troubleshooting experience

After restarting the virtual machine, I accidentally booted from the Windows Server installation media and reached the setup screen. Since the server was already installed and working, I stopped before making any changes, removed the ISO from the virtual optical drive, and restarted the VM. The server then booted normally with its existing files and configuration intact.

This reminded me to check the VM’s boot media before continuing with an installation screen, especially when a working operating system is already present.

**Result**

The server was successfully renamed to `LAB-DC01` and configured with a static IPv4 address. The gateway and external connectivity tests completed with zero packet loss, and DNS successfully resolved `google.com`.

**What I learned**

This lab helped me understand why servers need clear names and consistent IP addresses. The computer name identifies the server, while the static IP provides a reliable network location. I also practiced verifying each part of the connection instead of assuming the configuration worked after making changes.


## 📜 Certification

- CompTIA A+ (In Progress)

Thanks for visiting my portfolio!

