<h1>Enterprise Network Design and Configuration Lab</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
This lab simulates the design, configuration, and verification of a multi-office enterprise network, consisting of Office A and Office B, connected through a redundant core network to the Internet. The design follows a hierarchical model with Core, Distribution, and Access layers, supporting wired PCs, IP phones, wireless clients, and centralized services. Key configurations include VLAN creation and propagation using VTP, trunking with DTP disabled, and EtherChannel for link redundancy (PAgP in Office A, LACP in Office B). HSRPv2 and Rapid PVST+ provide gateway redundancy and optimized Layer-2 paths. IPv4  addressing scheme was deployed across all devices, with OSPFv2 ensuring dynamic routing and Internet failover via dual uplinks on R1. Essential services such as DHCP, DNS, NTP, SNMP, Syslog, NAT/PAT, and secure SSHv2 management were configured, alongside security measures like extended ACLs, Port Security, DHCP Snooping, and Dynamic ARP Inspection. The wireless network is managed centrally via WLC1 with WPA2-PSK encryption.
This lab provides hands-on experience in enterprise network deployment, redundancy, routing, security, and service integration, reflecting real-world best practices in scalable network design. 

<br />


<h2>Tools/Utilities Used</h2>

- <b>Cisco Packet Tracer</b> 

<h2>Lab Tasks Overview:</h2>
The lab is divided into nine major parts, each implementing key enterprise networking concepts and configurations:

- <b>Part 1 – Initial Setup</b>

•	Assigned hostnames, configured secure enable passwords using type 5 and 9 hashing, created local user accounts with encrypted secrets, and secure console access with local authentication.
•	Applied session timeout and enable synchronous logging.



<p align="center">
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
