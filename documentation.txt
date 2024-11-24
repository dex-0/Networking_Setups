### Documentation: Three-Tier Enterprise Network

#### **Overview**

A three-tier enterprise network design connecting two branches via a Cisco 2911 router, providing internet access with redundancy. All devices are dual-stack with IPv4 and IPv6, ensuring scalability and flexibility.

---

#### **Routing Configuration**

1. **Routing Protocols**:
    - **OSPFv2** used for IPv4 dynamic routing within the internal network.
    - **Static routing** configured for the connection between the router and ISP.
2. **NAT**:
    - **Dynamic NAT overload** configured on the 2911 router for private IP address translation.
3. **Virtual Interfaces**:
    - Virtual interfaces configured as gateways for each subnet to enable inter-VLAN routing.

---

#### **Device Access Security**

1. **Authentication**:
    - **Router (R1)**:
        - `enable password` secured using `scrypt`.
        - Local credentials: `username cisco`, password `ccna`.
    - **Switches (Distribution, Core, Access)**:
        - Local credentials: `username ccna`, password `ccna`.
2. **Remote Access**:
    - **SSHv2** configured to allow secure remote access, with Telnet disabled.

---

#### **Network Security Features**

1. **Access Control**:
    - **ACLs** configured to control traffic flow and restrict unauthorized access.
2. **Switch Security**:
    - **Dynamic ARP Inspection (DAI)**, **DHCP Snooping**, and **Port Security** applied for protection against malicious activities.
    - **Unused ports** disabled, end-device ports configured with **PortFast** and **BPDU Guard** for enhanced security.
3. **Spanning Tree**:
    - **RSTP** (Rapid Spanning Tree Protocol) used for fast convergence and loop prevention.

---

#### **Switching Configuration**

1. **EtherChannel**:
    - **LACP** configured for **Layer 2 EtherChannels** between access and distribution switches with trunking.
    - **Layer 3 EtherChannels** configured between core switches for efficient routing.

---

#### **DHCP and DNS**

1. **DHCP**:
    - DHCP pools configured on R1 to dynamically assign IP addresses to end devices.
2. **DNS**:
    - A **dedicated DNS server** configured to provide name resolution services across the network.

---

#### **Wireless Configuration**

1. **WLC**:
    - **Management VLAN** configured for the Wireless LAN Controller (WLC).
    - **WLAN** named **Wi-Fi** deployed for client access.
    - **WPA2+PSK** security configured for secure wireless access.

---

#### **Time and Logging Services**

1. **NTP**:
    - **R1** acts as the **NTP server** at level 5, providing time synchronization across all devices.
2. **SNMP and Syslog**:
    - **Syslog** configured to send logs to an external server for centralized logging and monitoring.
    - **SNMP** configured for network monitoring.

---

#### **Other Measures**

1. **Redundancy**:
    - Critical points in the network configured with redundancy for enhanced reliability and failover.
2. **Documentation and Consistency**:
    - Proper hierarchy and standardized configurations maintained to ensure network stability and manageability.

This design provides a robust, secure, and scalable network solution with high availability and efficient management.

---
---
