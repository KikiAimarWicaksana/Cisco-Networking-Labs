# 🛡️ Cisco ASA NAT & Firewall Lab
An enterprise network security lab simulating zone segmentation, traffic filtering, and address translation using **Cisco ASA 5506-X** in Cisco Packet Tracer.

---

## 📌 Project Overview & Topology

![Cisco ASA NAT & Firewall Topology](topology_nat_firewall.png)

* **🔵 INSIDE:** Trusted clients (`192.168.10.0/24`, `192.168.20.0/24`)
* **🟢 DMZ:** Public-facing servers (`192.168.30.0/24`, `192.168.40.0/24`)
* **🔵 OUTSIDE:** Untrusted external network (`200.100.20.0/24`)

---

## 🌐 IP Addressing Table

| Zone | Device | Interface / IP | Gateway / Mask | Role |
| :--- | :--- | :--- | :--- | :--- |
| **INSIDE** | ASA Inside / Router1 | `192.168.1.1` / `192.168.1.2` | `/30` | Inter-router link |
| | PC1 / PC2 | `192.168.10.2` / `192.168.20.2` | `/24` (via Router1) | Internal Clients |
| **DMZ** | ASA DMZ / Router2 | `192.168.2.1` / `192.168.2.2` | `/30` | DMZ gateway link |
| | WEB / FTP Server | `192.168.30.2` / `192.168.40.2` | `/24` (via Router2) | HTTP / FTP Servers |
| **OUTSIDE** | ASA Outside / Router3 | `200.100.10.1` / `200.100.10.2` | `/29` | WAN link |
| | PC3 | `200.100.20.2` | `/24` (via Router3) | External Client |

---

## 🔥 Security Policies & Access Control (ACL)

Traffic follows the **least-privilege model**: HTTP is exposed externally, while FTP remains strictly internal.

| Source Zone | Destination | Service / Port | Action | Purpose |
| :--- | :--- | :---: | :---: | :--- |
| 🔵 **INSIDE** | 🟢 WEB Server | TCP / `80` | ✅ **ALLOW** | Internal web access |
| 🔵 **INSIDE** | 🟢 FTP Server | TCP / `21` | ✅ **ALLOW** | Internal file transfer |
| 🔵 **OUTSIDE** | 🟢 WEB Server | TCP / `80` | ✅ **ALLOW** | Public web hosting |
| 🔵 **OUTSIDE** | 🟢 FTP Server | TCP / `21` | ❌ **DENY** | Blocked by ASA ACL |

---

## 🔄 NAT & PAT Architecture

* **Static NAT (DMZ Inbound):** Maps DMZ Web Server (`192.168.30.2`) ➔ Public IP `200.100.10.3` (accessible via `http://200.100.10.3`).
* **PAT / NAT Overload (Outbound):** Overloads LAN subnets (`192.168.10.0/24`) ➔ ASA Outside Interface `200.100.10.1`.

> **Key Rule:** **NAT** handles IP address translation, while **ACL** enforces permit/deny traffic policies.

---

## 🧪 Verification & Repository Structure

```text
├── cisco-asa-nat-firewall-lab.pkt   # Packet Tracer lab topology
├── topology_nat_firewall.png        # Network architecture diagram
└── README.md                        # Project documentation

