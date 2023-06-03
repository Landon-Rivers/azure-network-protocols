<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com/watch?v=LDTI4jl3qJk)

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

<p>
<img src="https://i.imgur.com/BXxeWXS.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
11. Back in Wireshark, filter for SSH traffic only.
</p>
<br />

<p>
<img src="https://i.imgur.com/sN4if1F.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
12. From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)
</p>
<p>
 <img src="https://i.imgur.com//3ZVEfjV.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  a. Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark.
</p>
<p>
 <img src="https://i.imgur.com/SjRN4tZ.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  b. Exit the SSH connection by typing ‘exit’ and pressing [Enter].
</p>
<br />

<p>
<img src="https://i.imgur.com/WoQTClt.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
13. Back in Wireshark, filter for DHCP traffic only.
</p>
<br />

<p>
<img src="https://i.imgur.com/akJ0egW.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
14. From your Windows 10 VM, attempt to issue your VM a new IP address from the command line (ipconfig /renew).
</p>
<p>
 <img src="https://i.imgur.com//7Yb1Ae4.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  a. Observe the DHCP traffic appearing in WireShark.
</p>
<br />

<p>
<img src="https://i.imgur.com/P4OsOvN.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
15. Back in Wireshark, filter for DNS traffic only.
</p>
<br />

<p>
<img src="https://i.imgur.com/iTVyCCh.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/0tgEMn5.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
16. From your Windows 10 VM within a command line, use nslookup to see what google.com and disney.com’s IP addresses are. Observe the DHCP traffic appearing in WireShark.
</p>
<br />

<p>
<img src="https://i.imgur.com/O1xd8wh.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
17. Back in Wireshark, filter for RDP traffic only (tcp.port == 3389).
</p>
<br />

18. Observe the immediate non-stop spam of traffic? Why do you think it’s non-stop spamming vs only showing traffic when you do an activity?
 a. Answer: because the RDP (protocol) is constantly showing you a live stream from one computer to another, therefor traffic is always being transmitted.
 
<p>
<img src="https://i.imgur.com/m6F7PP0.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
19. Close your Remote Desktop connection.
</p>
<br />

<p>
<img src="https://i.imgur.com/tTe5Al7.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
20. Delete the Resource Group(s) created at the beginning of this lab.
</p>
<br />

<p>
<img src="https://i.imgur.com/Q9iCAKU.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
21. Verify Resource Group Deletion.
</p>
<br />

This concludes the observation of various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups.
