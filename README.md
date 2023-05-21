<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Resources
- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic
- Observe RDP Traffic
- Lab Cleanup

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/sQ330tQ.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
1. Create a Resource Group.
</p>
<br />

<p>
<img src="https://i.imgur.com/PYTvJEc.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
2. Create a Windows 10 Virtual Machine (VM).
</p>
<br />


<p>
<img src="https://i.imgur.com/PkZZPDIB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
3. Create a Linux (Ubuntu) VM.
</p>
<br />

<p>
<img src="https://i.imgur.com/lhAsBFd.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
4. Observe Your Virtual Network within Network Watcher.
</p>
<br />

<p>
<img src="https://i.imgur.com/EXQTqNV.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
5. Use Remote Desktop to connect to your Windows 10 Virtual Machine.
</p>
<br />

<p>
<img src="https://i.imgur.com/wwhUG3p.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
6. Within your Windows 10 Virtual Machine, Install Wireshark.
</p>
<br />

<p>
<img src="https://i.imgur.com/qQMOoen.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
7. Open Wireshark and filter for ICMP traffic only.
</p>
<br />
