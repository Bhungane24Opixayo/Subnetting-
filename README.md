# Cisco Packet Tracer – VLSM/Subnetting Network Lab
A simple routed network topology created in Cisco Packet Tracer to demonstrate IPv4 subnetting, network identification, host ranges, broadcast addresses, and communication between two LANs.
Topology Overview
The network is divided into two LANs connected through a Cisco ISR4331 router:
 
 IP Addressing
The original network is:
192.168.40.0/24
It is divided into two /25 subnets.
Network	Network ID	Usable Range	Broadcast
ADMIN	192.168.40.0/25	192.168.40.1–126	192.168.40.127
FINANCE	192.168.40.128/25	192.168.40.129–254	192.168.40.255
Subnet mask:
255.255.255.128
Each /25 subnet provides 126 usable host addresses.
Router Configuration
ADMIN
enable
configure terminal
interface gigabitEthernet 0/0/0
ip address 192.168.40.1 255.255.255.128
no shutdown
exit
FINANCE
interface gigabitEthernet 0/0/1
ip address 192.168.40.129 255.255.255.128
no shutdown
exit
Save the configuration:
end
copy running-config startup-config
Verification
Use:
show ip interface brief
and:
show ip route
Test connectivity using:
ping 192.168.40.1
ping 192.168.40.129
For inter-network communication, test from an ADMIN PC to a FINANCE PC:
ping 192.168.40.138
Key Concepts
•	IPv4 subnetting
•	/24 to /25 subnetting
•	Network ID
•	Broadcast address
•	Usable host range
•	Default gateway
•	Router interfaces
•	Inter-subnet routing
•	Cisco IOS
•	no shutdown
•	ICMP/Ping
•	Routing-table verification
Learning Objectives
After completing this lab, learners should be able to:
1.	Divide an IPv4 /24 network into /25 subnets.
2.	Identify network IDs and broadcast addresses.
3.	Determine usable host ranges.
4.	Configure IPv4 addresses on router interfaces.
5.	Configure default gateways on end devices.
6.	Verify router interfaces and routing tables.
7.	Test connectivity using ping.
8.	Explain how routers enable communication between different IP networks.
:::

