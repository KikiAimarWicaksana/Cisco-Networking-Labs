# 🌐 Cisco Networking Labs

A collection of hands-on Cisco networking labs built with Cisco Packet Tracer.

This repository documents my practical learning journey in network
infrastructure, routing, wireless networking, network security, and
device management through simulated enterprise network environments.

---

## 📚 Labs

### 01. Enterprise Network Infrastructure

A small enterprise network implementing network segmentation,
inter-VLAN routing, dynamic routing, centralized network services,
and ACL-based traffic control.

**Topics:**

- VLAN
- Inter-VLAN Routing
- OSPF
- DHCP Relay
- DNS
- Web Server
- ACL

📂 [View Lab](labs/enterprise-network/)

---

### 02. Wireless Network & Access Point

A wireless enterprise network integrating an Access Point with
dedicated VLAN segmentation, wireless security, DHCP, ACL,
NAT/PAT, and SSH-based device management.

**Topics:**

- Access Point
- SSID
- WPA2-PSK / AES
- Wireless VLAN
- DHCP
- ACL
- NAT/PAT
- SSH
- Network Segmentation

📂 [View Lab](labs/wireless-access-point/)

---

### 03. Cisco ASA NAT & Firewall

A network security lab focused on firewall configuration,
traffic filtering, network segmentation, and NAT/PAT using
Cisco ASA 5506-X.

**Topics:**

- Cisco ASA
- Firewall
- Security Zones
- NAT/PAT
- ACL
- Traffic Filtering
- Network Segmentation
- Internet / WAN Simulation

📂 [View Lab](labs/cisco-asa-firewall/)

---

## 🧠 Skills & Concepts

This repository covers practical networking concepts including:

| Category | Concepts |
|---|---|
| Network Fundamentals | IP Addressing, Subnetting, Routing |
| Switching | VLAN, Trunking, Access Ports |
| Routing | Static Routing, Inter-VLAN Routing, OSPF |
| Network Services | DHCP, DHCP Relay, DNS, Web Server |
| Wireless | Access Point, SSID, WPA2-PSK, AES |
| Security | ACL, Firewall, Network Segmentation |
| NAT | Static NAT, Dynamic NAT, PAT |
| Management | SSH |
| Simulation | Cisco Packet Tracer |

---

## 🏗️ Repository Structure

```text
Cisco-Networking-Labs/
│
├── README.md
│
└── labs/
    │
    ├── enterprise-network/
    │   ├── README.md
    │   ├── enterprise-network-lab.pkt
    │   └── topology.png
    │
    ├── wireless-access-point/
    │   ├── README.md
    │   ├── Wireless-Network.pkt
    │   └── wireless-network.png
    │
    └── cisco-asa-firewall/
        ├── README.md
        ├── cisco-asa-nat-firewall-lab.pkt
        └── topology_nat_firewall.png
