# IAS-Project-Sep-2025
📌 1. Project Overview

This project implements a secure enterprise network for five departments:

1)IT

2)HR

3)IS

4)CS

5)Server Room (HTTP + DNS)

The goal is to design, configure, and secure a functional multi-department network using routing, VLANs, DHCP, SSH, SNMP, and an ASA firewall.

📌 2. Network Topology Summary

The network uses a hybrid topology:

Section	Topology	Description
IT	Star	PCs connected to a central switch
HR	Hierarchical	Router → Switches → PCs
IS	Partial Mesh	Multiple interconnected switches (redundancy)
CS	Wireless Star	Wireless router serving devices
Server Room	Star	Servers connected via switch through ASA firewall
Core Backbone	Hierarchical	MAIN router acts as central routing point
📌 3. Key Technologies Used

Static Routing (inter-department communication)

DHCP (automatic IP assignment)

SSH (secure remote login)

SNMP (network monitoring)

VLAN Segmentation

ASA Firewall + NAT (secure server access)

Password and access control hardening

📌 4. IP Scheme Overview

IT: 192.168.10.0/24

HR: 192.168.20.0/24

CS: 192.168.30.0/24

IS: 192.168.40.0/24

Server VLAN: 192.168.50.0/24

ASA Inside: 10.0.10.1/24

📌 5. Firewall Configuration Summary

ASA 5505 placed between MAIN router and Server VLAN:

Inside (VLAN1): 10.0.10.1/24

Outside (VLAN2): 192.168.50.1/24

Configured NAT, ACLs, and disabled DHCP

Allows only HTTP & DNS to pass to servers

Blocks unauthorized access to Server VLAN

📌 6. Security Enhancements

Enforced SSH on all routers

Applied strong passwords & enable secret

Enabled SNMP read-only monitoring

Identified risks:

Unsecured WiFi → recommend WPA2/WPA3

STP attack risk → enable BPDU Guard

Weak password usage → require policy improvement

📌 7. Conclusion

The final network is:

Fully functional

Securely segmented

Routed using static routes

Protected with an ASA firewall

Monitored with SNMP

Hardened with SSH and strong access controls

This project successfully demonstrates real-world enterprise networking and security implementation.
