<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com/watch?v=cwlVz4tD8pk)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Domain Controller VM (Windows Server 2022) named “DC-1”
- Domain Controller’s NIC Private IP address to be static
- Create an Admin and Normal User Account in Active Directory
- Join Client to domain

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/lwJD66J.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First, I will need to establish the resource group so that I can add the virtual machines for the Domain Controller (DC-1) and the Client Virtual Machine (Client-1). The Domain Controller VM will use Windows Server 2022 system image (a serialized copy of the entire state of a computer system stored in some non-volatile form such as a file).*pictured above*
</p>
<br />

<p>
<img src="https://i.imgur.com/l7ewHRJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Second, check for connection between the client device and domain controller by logging into Client-1 with Remote Desktop Connection (RDP) and pinging DC-1’s private IP address using ping -t (perpetual ping). ICMPv4 (ping) was allowed on the Domain Controller's (DC-1) Firewall in Windows Firewall (Core Networking Diagnostics - ICMP Echo Request (ICMPv4-In)). After logging back into Client-1 check to make sure the ping is successful. *pictured above*
</p>
<br />

<p>
<img src="https://i.imgur.com/XolGzSp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, I will configure the organizational units for the admins and employees in Active Directory (AD) while continuing to be in DC-1 (Remote Desktop Connection). The accounts can now be viewed in Active Directory in the appropriate organizational unit. In the Active Directory, right click on your domain name and move your mouse to hover new-->Organizational Unit and left click to create folders for your AD. I will create employees, admins, and security groups.
</p>
<br />
