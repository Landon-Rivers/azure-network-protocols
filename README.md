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
<img src="https://i.imgur.com/kZZPDIB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
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


<p>
<img src="https://i.imgur.com/WS1RQ9A.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
8. Retrieve the private IP address of the Ubuntu VM and attempt to ping it from within the Windows 10 VM using a command line or PowerShell.
 
 a. Observe ping requests and replies within WireShark
</p>
<br />

<p>
<img src="https://i.imgur.com/cL42bf3.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
9. From The Windows 10 VM, attempt to ping a public website (such as www.google.com) and observe the traffic in WireShark.
</p>
<br />

<p>
<img src="https://i.imgur.com/AryODHO.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
10. Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM.
</p>
<p>
 <img src="https://i.imgur.com/sxpS5g2.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  a. Open the Network Security Group your Ubuntu VM is using and disable incoming (inbound) ICMP traffic.
</p>
<p>
 <img src="https://i.imgur.com/LZvnWVr.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  b. Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity.
</p>
<p>
 <img src="https://i.imgur.com/XT45RYA.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  c. Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is using.
</p>
<p>
 <img src="https://i.imgur.com/KKsJo1x.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  d. Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity (should start working).
</p>
<p>
 <img src="https://i.imgur.com/HGGdDWc.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  e. Stop the ping activity.
</p>
<br />
