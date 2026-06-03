VLAN Segmentation and Router-on-a-Stick Inter-VLAN Routing (Cisco Packet Tracer)
Project Overview

This project demonstrates the implementation of VLAN segmentation and Router-on-a-Stick (ROAS) inter-VLAN routing using Cisco Packet Tracer. The network consists of four switches and one router connecting three departments: HR, FINANCE, and IT.

The objective is to isolate departmental traffic using VLANs while enabling controlled communication between VLANs through a router configured with 802.1Q trunking and subinterfaces.

Network Topology
                Router R1
                     |
                Trunk Link
                     |
                  Switch 1
               /     |     \
              /      |      \
        Switch2  Switch3  Switch4
           |         |         |
        HR PCs   FIN PCs    IT PCs
Devices Used
1 Cisco Router
4 Cisco Switches
Multiple PCs
Copper Straight-Through Cables
VLAN Configuration
Department	VLAN ID	Network
HR	10	192.168.0.1/26
FINANCE	20	192.168.0.65/26
IT	30	192.168.0.129/26

Default Gateways
VLAN	Gateway
VLAN 10	192.168.0.1
VLAN 20	192.168.0.65
VLAN 30	192.168.0.129
Features
VLAN-based network segmentation
Departmental traffic isolation
802.1Q trunking between switches
Router-on-a-Stick inter-VLAN routing
End-to-end connectivity testing
Network troubleshooting and validation
Configuration Summary
Create VLANs
vlan 10
 name HR

vlan 20
 name FINANCE

vlan 30
 name IT
Configure Access Ports
interface fa0/1
 switchport mode access
 switchport access vlan 10
Configure Trunk Ports
interface g0/1
 switchport mode trunk
Router-on-a-Stick Configuration
interface g0/0
 no shutdown

interface g0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface g0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0

interface g0/0.30
 encapsulation dot1Q 30
 ip address 192.168.30.1 255.255.255.0
Verification

The following commands were used to verify the configuration:

show vlan brief
show interfaces trunk
show ip interface brief
show running-config

Connectivity was tested using:

ping <destination-ip>
Expected Results
Devices within the same VLAN communicate successfully.
Devices in different VLANs communicate through Router R1.
VLAN traffic remains logically separated.
Trunk links carry VLAN traffic between switches.
Troubleshooting
Problem	Cause	Solution
Hosts could not communicate	Incorrect VLAN assignment	Assigned ports to correct VLAN
Inter-VLAN routing failed	Missing router subinterface	Added required subinterfaces
Trunk links not working	Interface configured as access port	Changed interface to trunk mode
PCs could not reach gateway	Wrong default gateway	Corrected gateway settings
VLAN traffic not passing between switches	Trunk misconfiguration	Reconfigured trunk links
Learning Outcomes

Through this project, I gained hands-on experience with:

VLAN creation and management
Switch port assignment
Trunk configuration using 802.1Q
Router-on-a-Stick implementation
Inter-VLAN routing
Network troubleshooting and verification
Cisco Packet Tracer network design

Author
ALIMI RIDWAN OLAIDE
Created as a Cisco Networking and Network Segmentation Lab Project using Cisco Packet Tracer.
