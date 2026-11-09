# Subnetting-and-Vlan
Designed a two-floor office network using Cisco switches, VLAN segmentation, CIDR subnetting, and trunking. Demonstrates network isolation, IPv4 addressing, and basic network security principles.

Office Network Segmentation Using VLANs and CIDR Subnetting
1. Project Overview

This project demonstrates the design and configuration of a two-floor office network using Cisco switches, Virtual Local Area Networks (VLANs), and CIDR-based subnetting.

The network consists of three departments:

Management
Sales
IT Support

Each department is assigned a separate VLAN to provide network segmentation, improve network organization, and reduce unnecessary communication between departments.

Project Type: Networking / Cybersecurity Lab

Technologies Used: Cisco Switches, VLANs, IPv4, CIDR Subnetting, Trunking

2. Network Design

The original network was:

192.168.10.0/24

The original network was divided into smaller /27 subnets to allocate separate IP address ranges to each department.

The network contains:

Two Cisco switches.
Three departmental VLANs.
Two floors of office devices.
An inter-switch trunk connection.

3. IP Addressing and Subnetting

The original /24 network was divided into /27 subnets.

Each /27 subnet provides:

32 total IP addresses.
30 usable host addresses.
1 network address.
1 broadcast address.
Department	VLAN	Network Address	Subnet Mask
Management	10	192.168.10.0/27	255.255.255.224
Sales	20	192.168.10.32/27	255.255.255.224
IT Support	30	192.168.10.64/27	255.255.255.224
4. VLAN Configuration

Three VLANs were created to separate the departments.

VLAN ID	VLAN Name	Department
10	MANAGEMENT	Management
20	SALES	Sales
30	IT_SUPPORT	IT Support

Each department's devices were assigned to their corresponding VLAN.

5. Switch Configuration

Two Cisco switches were configured to support the office network.

Switch 1 – Ground Floor
Switch Port	VLAN	Department
Fa0/1–5	10	Management
Fa0/6–10	20	Sales
Fa0/11–15	30	IT Support
Fa0/24	Trunk	Connection to Switch 2
Switch 2 – First Floor
Switch Port	VLAN	Department
Fa0/1–5	10	Management
Fa0/6–10	20	Sales
Fa0/11–15	30	IT Support
Fa0/24	Trunk	Connection to Switch 1
6. Network Security Concepts

The main security concept demonstrated in this project is network segmentation.

Each department is placed in its own VLAN, creating separate Layer 2 broadcast domains.

For example:

Management devices belong to VLAN 10.
Sales devices belong to VLAN 20.
IT Support devices belong to VLAN 30.

Devices in different VLANs cannot communicate directly at Layer 2.

Inter-VLAN communication requires Layer 3 routing. Additional security controls, such as Access Control Lists (ACLs), can be implemented to restrict communication between departments.

The trunk connection allows VLAN traffic to travel between the two switches, allowing devices in the same VLAN to communicate across different floors.

7. Connectivity Testing

Network connectivity was tested to verify VLAN segmentation and inter-switch communication.

Expected results:

Devices in the same VLAN on different switches should be able to communicate, assuming correct IP addressing and VLAN configuration.
Devices in different VLANs should not communicate without inter-VLAN routing.
The trunk link should carry traffic for the configured VLANs.
8. Skills Demonstrated
VLAN creation and configuration.
Network segmentation.
CIDR subnetting.
IPv4 addressing.
Cisco switch configuration.
Access port configuration.
Trunk port configuration.
Network topology design.
Network connectivity testing.
Basic network security principles.
9. Project Conclusion

This lab provided practical experience in designing and configuring a segmented office network using Cisco switching technologies.

It demonstrated how VLANs and subnetting can organize a network into separate departmental segments and how trunk connections enable VLAN communication across multiple switches.

Network segmentation is an important security principle because it helps limit unnecessary network communication and provides a foundation for implementing additional security controls.

10. Future Improvements

Potential improvements to this network include:

Implementing inter-VLAN routing.
Configuring Access Control Lists (ACLs).
Adding firewall security policies.
Implementing DHCP for automatic IP assignment.
Configuring port security on access ports.
