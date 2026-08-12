# network-segmentation-ACL-project
## Network Topology

The network was implemented in Cisco Packet Tracer using a router,
switch, and four VLANs representing different organizational groups.

The VLANs are:

- VLAN 10 — IT — 192.168.10.0/24
- VLAN 20 — Management — 192.168.20.0/24
- VLAN 30 — Staff — 192.168.30.0/24
- VLAN 40 — Guest — 192.168.40.0/24

The switch connects the end devices to their respective VLANs,
while a trunk link connects the switch to the router for
inter-VLAN routing.

An external network (10.10.10.0/24) was also simulated to
represent the Internet.

<img width="1358" height="670" alt="Switch0 8_11_2026 2_17_19 PM" src="https://github.com/user-attachments/assets/c742a2bf-8e15-411d-9186-5cf07946fbb4" />

