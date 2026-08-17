## Network Segmentation and ACL Implementation Report
## 1. Introduction

This project was designed and implemented in Cisco Packet Tracer to demonstrate basic network segmentation and access control.

The network uses VLANs to separate different user groups and Extended Access Control Lists (ACLs) to control communication between the networks.

Additional security measures, including device authentication, MOTD banners, and switch port security, were also configured.


## 2. Network Design

The network is divided into four VLANs:

VLAN 10 – IT:192.168.10.0/24
VLAN 20 – Management:192.168.20.0/24
VLAN 30 – Staff:192.168.30.0/24
VLAN 40 – Guest:192.168.40.0/24

The external network representing the Internet uses:

Internet: 10.10.10.0/24

The switch connects the end devices to their respective VLANs. The switch's G0/1 interface connects to the router and is configured as a trunk.

## 3. Inter-VLAN Routing

Router-on-a-Stick was used to enable communication between the VLANs.

The router uses sub-interfaces for each VLAN:

VLAN 10 → 192.168.10.1
VLAN 20 → 192.168.20.1
VLAN 30 → 192.168.30.1
VLAN 40 → 192.168.40.1

802.1Q encapsulation was configured on the router sub-interfaces to identify the different VLANs.

## 4. Access Control Lists

Extended ACLs were used to control traffic based on source network, destination network, protocol, and port number.

The main security requirements were:

IT users were given full network access.

Management users were allowed to communicate with Staff and access the IT server using HTTP and HTTPS.

Staff users were allowed to access the Internet and the IT server through HTTP and HTTPS.

Guest users were restricted to Internet access and blocked from internal VLANs.

External traffic was restricted so that the IT network could only be accessed through HTTP and HTTPS.

## 5. Device Security

Basic security hardening was also implemented on the router and switch.

An enable secret was configured to protect privileged EXEC mode.

The actual password is not included in this repository.

MOTD Banner

A warning banner was configured to notify unauthorized users that access to the devices is restricted.

Switch Port Security

Port security was configured on the switch access ports to restrict unauthorized devices from connecting to the network.

## 6. Verification

The following Cisco IOS commands were used to verify the network configuration:

show ip interface brief
show vlan brief
show interfaces trunk
show access-lists
show ip interface
show port-security
show running-config

Connectivity tests were also used to verify that permitted traffic could pass while restricted traffic was blocked.

## 7. Security Benefits

The implementation provides several security benefits:

Network segmentation: VLANs separate users into different security zones.
Access control: ACLs restrict communication based on security requirements.
Least privilege: Users receive only the access required for their role.
Guest isolation: Guest devices cannot access internal networks.
Server protection: Access to the IT server can be restricted to approved services.
Layer 2 security: Port security helps prevent unauthorized devices from using protected switch ports.

## 8. Lessons Learned

This project demonstrated that network connectivity does not necessarily mean unrestricted access.

VLANs provide logical network separation, while ACLs determine what traffic is actually permitted between those networks.

I also learned the importance of ACL rule order, interface placement, and configuration verification. A security policy is only effective when it is correctly configured and tested.

## 9. Conclusion

This project provided practical experience with VLANs, Router-on-a-Stick, Extended ACLs, and basic Cisco device hardening.

The combination of network segmentation, traffic filtering, and Layer 2 security provides a stronger and more controlled network environment.

The project also strengthened my understanding of how networking concepts can be applied to real-world cybersecurity scenarios.
