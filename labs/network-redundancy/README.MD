# Cisco Network Redundancy Lab

A Cisco Packet Tracer lab focused on **network redundancy, high availability, Layer 2 loop prevention, inter-VLAN routing, and Internet connectivity simulation**.

This lab demonstrates how several Cisco technologies work together to keep a network available when links or gateway devices fail.

## Topology

![Network Topology](topology-redudancy.png)

### Main Components

- **Router1** — ISP / simulated Internet
- **Router0** — Edge Router
- **Multilayer Switch1** — Distribution Switch / HSRP Active
- **Multilayer Switch2** — Distribution Switch / HSRP Standby
- **Switch0** — Access Switch
- **PC1 & PC2** — Client devices
- **Server1** — Internal Server
- **Access Point + Laptop0** — Wireless Network

---

## Technologies Implemented

### EtherChannel

Two physical links are bundled into a single logical link using **LACP**.

```text
L3-SW1 ↔ Switch0
Fa0/1 + Fa0/2 → Port-Channel 1

L3-SW2 ↔ Switch0
Fa0/1 + Fa0/2 → Port-Channel 2
