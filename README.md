# Enterprise Network Design and Configuration

An enterprise corporate network designed, segmented, and secured using Cisco Packet Tracer. This project implements advanced network architectures including Inter-VLAN routing, dynamic RIP dynamic routing, and security Access Control Lists (ACLs).

---

##  Features & Technologies
* Network Segmentation: Multi-router topology with 4 major subnets.
* Inter-VLAN Routing: Router-on-a-Stick (ROAS) via 802.1Q trunking encapsulation.
* Routing Convergence: Dynamic RIPv2 configuration with split-horizon behavior adjustments (`no auto-summary`).
* Security Access Control Lists: Custom inbound/outbound Standard ACLs to prevent host cross-talk.

---

##  IP Addressing Table

| Device Name | Interface | IP Address | Subnet Mask | Default Gateway |
| :--- | :--- | :--- | :--- | :--- |
| Router1 | Fa0/0.10 (VLAN 10) | 192.168.10.1 | 255.255.255.0 | *N/A* |
| Router1 | Fa0/0.30 (VLAN 30) | 192.168.30.1 | 255.255.255.0 | *N/A* |
| Router1 | Se2/0 (Link to R2) | 10.0.0.1 | 255.255.255.252 | *N/A* |
| Router1 | Se3/0 (Link to R3) | 11.0.0.2 | 255.255.255.252 | *N/A* |
| Router2 | Fa0/0 | 192.168.20.1 | 255.255.255.0 | *N/A* |
| Router3 | Fa0/0 | 192.168.40.1 | 255.255.255.0 | *N/A* |
| **PC1 / PC2**| Fa0 (IT Dept) | 192.168.10.10 / .11 | 255.255.255.0 | 192.168.10.1 |
| **PC3 / PC4**| Fa0 (HR Dept) | 192.168.30.10 / .11 | 255.255.255.0 | 192.168.30.1 |
| **PC5 / PC6**| Fa0 (Subnet 20) | 192.168.20.10 / .11 | 255.255.255.0 | 192.168.20.1 |
| **PC8 / PC9**| Fa0 (Subnet 40) | 192.168.40.10 / .11 | 255.255.255.0 | 192.168.40.1 |

---

##  Topology & Verification Outputs

### 1. Network Topology
![Network Topology](block_diagram.png)

### 2. Live Diagnostics (`show ip route`)
```text
C    192.168.10.0/24 is directly connected, FastEthernet0/0.10
R    192.168.20.0/24 [120/1] via 10.0.0.2, 00:00:26, Serial2/0
C    192.168.30.0/24 is directly connected, FastEthernet0/0.30
R    192.168.40.0/24 [120/1] via 11.0.0.1, 00:00:02, Serial3/0
