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
  - Assigned hostnames, configured secure enable passwords using type 5 and 9 hashing, created local user accounts with encrypted secrets, and secure console access with local authentication.
  - Applied session timeout and enable synchronous logging.
 
<p align="center">
<img src="https://i.imgur.com/r483DFN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Part 2 – VLANs and Layer-2 EtherChannels</b>
  - Implemented Layer-2 EtherChannels between distribution switches in both offices:	Office A uses Cisco-proprietary protocol (PAgP) while Office B uses open standard protocol (LACP).
  - Configured trunk links between access and distribution switches (including the EtherChannel), disabled DTP, set native VLAN 1000, and allowed specific VLANs per office e.g. VLANs 10,20,40 and 99 in office A
  - Configured VTPv2 using ifyITlab domain and one distribution switch as the server in each office and access switches as clients.
  - Created and named VLANs for PCs (Vlan 10), Phones, Wi-Fi (Vlan 40), Servers (Vlan 30), and Management (Vlan 99) in each office.
  - Assigned VLANs to access ports for PCs, phones, APs, and SRV1, with unused ports administratively disabled for security reasons.
<p align="center">
<br />
<img src="https://i.imgur.com/s4f2Kcb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
        <br/>
<img src="https://i.imgur.com/mN4j5O8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/C9xwIJj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Part 3 – IP Addressing, Layer-3 EtherChannel, and HSRP</b>
  - Assigned IPv4 addresses to R1, Core, and Distribution switches, including loopback interfaces.
  - Implemented Layer-3 EtherChannel between CSW1 and CSW2.
  - Configured HSRPv2 for each VLAN, ensuring alignment with STP root bridge roles for redundancy and load balancing.
  - Configured SRV1 with static IP settings and assigned management IPs to all access switches.

 <p align="center">
<br />
<img src="https://i.imgur.com/U8APsTD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://i.imgur.com/yQLMbtI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- <b>Part 4 – Rapid Spanning Tree Protocol (RSTP)</b>
  - Enabled Rapid PVST+ and set root bridge priorities to match HSRP active devices.
  - Enabled PortFast and BPDU Guard on all end-host-facing ports.
    
 <p align="center">
<br />
<img src="https://i.imgur.com/lbPA8W7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
<br />
<img src="https://i.imgur.com/VTOgv40.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- <b>Part 5 – Routing</b>
  - Enabled Rapid PVST+ and set root bridge priorities to match HSRP active devices.
  - Implemented OSPFv2 across R1, Core, and Distribution switches with loopback-based Router IDs.
  - Configured static default routes on R1 for dual Internet uplinks with floating route failover.
  - Redistributed default routes into OSPF for enterprise-wide Internet access.

<p align="center">
<br />
<img src="https://i.imgur.com/Ypyr2Yk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
<br />
<img src="https://i.imgur.com/Vsi3AiD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
<br />
<img src="https://i.imgur.com/g5kxxv6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- <b>Part 6 – Network Services</b>
  - Configured DHCP pools on R1 for all VLANs, excluding reserved addresses.
  - Enabled DHCP relay on distribution switches.
  - Configured DNS on SRV1 for internal and external domain resolution.
  - Implemented NTP, SNMP, and Syslog across all devices.
  - Used FTP to update R1’s IOS.
  - Enabled SSHv2 with ACL restrictions for secure remote access.
  - Configured NAT/PAT for Internet access and public server hosting.
  - Used LLDP for neighbor discovery.

<p align="center">
<br />
<img src="https://i.imgur.com/TbEYdWl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
<br />
<img src="https://i.imgur.com/2CY7O4h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
<br />
<img src="https://i.imgur.com/lV3ME32.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- <b>Part 7 – Security</b>
  - Implemented extended ACLs to control inter-office traffic between PC subnets.
  - Used Port Security to prevent MAC spoofing
  - Enabled DHCP Snooping and Dynamic ARP Inspection (DAI) for Layer-2 security.

 <p align="center">
<br />
<img src="https://i.imgur.com/KLAdnsf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
<br />
<img src="https://i.imgur.com/XwG7Cm0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
<br />
<img src="https://i.imgur.com/An7s7MK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://i.imgur.com/fl7K914.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- <b>Part 8 – IPv6</b>
  - Enabled IPv6 routing on R1, CSW1, and CSW2, assign IPv6 addresses

<p align="center">
<br />
 <img src="https://i.imgur.com/ix7oQfc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 <br />
<img src="https://i.imgur.com/IYH6MTy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>



    
 







 
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
