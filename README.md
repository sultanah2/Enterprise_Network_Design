# Enterprise_Network_Design

## Overview
This project demonstrates the design and implementation of an enterprise network using Cisco Packet Tracer. It implements advanced network architectures including Inter-VLAN routing, dynamic RIP routing, and security Access Control Lists (ACLs).

## Features
- VLAN Configuration and Segmentation (IT Dept & HR Dept)
- Router-on-a-Stick (ROAS) Inter-VLAN Routing
- Dynamic RIPv2 Routing Configuration
- Standard Access Control Lists (ACL) for Traffic Restriction

## Network Topology

!Network Topology

## IP Addressing Summary

| Device Name | Interface | IP Address | Subnet Mask |
| :--- | :--- | :--- | :--- |
| **Router1** | Fa0/0.10 (VLAN 10) | 192.168.10.1 | 255.255.255.0 |
| **Router1** | Fa0/0.30 (VLAN 30) | 192.168.30.1 | 255.255.255.0 |
| **Router1** | Se2/0 | 10.0.0.1 | 255.255.255.252 |
| **Router1** | Se3/0 | 11.0.0.2 | 255.255.255.252 |
| **Router2** | Fa0/0 | 192.168.20.1 | 255.255.255.0 |
| **Router3** | Fa0/0 | 192.168.40.1 | 255.255.255.0 |
| **Hosts (PCs)** | VLAN 10, 20, 30, 40 | 192.168.x.x Subnets | 255.255.255.0 |

---

## Verification and Live Diagnostics

### 1. Routing Table Diagnostics (show ip route)
This command displays the router's routing table, showing directly connected networks (C) and networks learned via the RIP routing protocol (R):
```text
C    192.168.10.0/24 is directly connected, FastEthernet0/0.10
R    192.168.20.0/24 [120/1] via 10.0.0.2, Serial2/0
C    192.168.30.0/24 is directly connected, FastEthernet0/0.30
R    192.168.40.0/24 [120/1] via 11.0.0.1, Serial3/0

### 2. Security Enforcement (ACL Ping Proof)
Verification that the Access Control List successfully blocks restricted host traffic while maintaining secure segmentation:
نسخ


C:\> ping 192.168.40.10
Pinging 192.168.40.10 with 32 bytes of data:
Reply from 11.0.0.1: Destination host unreachable.

## Tools
 * Cisco Packet Tracer
