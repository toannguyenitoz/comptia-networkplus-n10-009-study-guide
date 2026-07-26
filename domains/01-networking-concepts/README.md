<div align="center">

# 1️⃣ Domain 1 — Networking Concepts

### *Protocols • models • services • traffic • cloud • emerging technologies*

[![Weight](https://img.shields.io/badge/Exam_Weight-23%25-EA1D2C?style=for-the-badge)](#-exam-focus)
[![Level](https://img.shields.io/badge/Level-Foundation-0A66C2?style=for-the-badge)](#-learning-objectives)
[![Status](https://img.shields.io/badge/Notes-Ready-success?style=for-the-badge)](#)

[🏠 Home](../../README.md) • [➡️ Domain 2](../02-networking-implementation/README.md) • [⚡ Cheat Sheets](../../cheat-sheets/README.md)

</div>

---

## 🎯 Learning Objectives

By the end of this domain, you should be able to:

- 🧱 Explain all **seven OSI layers** and the encapsulation process
- 🔌 Match major **protocols, ports and transport types**
- 🖧 Compare routers, switches, firewalls, APs and specialised appliances
- ☁️ Distinguish **IaaS, PaaS, SaaS** and cloud deployment models
- 📣 Explain unicast, broadcast, multicast and anycast
- 🧭 Compare LAN, WAN, MAN, CAN, PAN and common topologies
- 🚀 Summarise SDN, SD-WAN, SASE, SSE, VXLAN and IPv6 transition options

---

## 🧱 OSI Model

| Layer | Name | Main Function | Common Examples | PDU |
|---:|---|---|---|---|
| **7** | Application | User-facing network services | HTTP, DNS, SMTP, SNMP | Data |
| **6** | Presentation | Translation, encryption, compression | TLS, JPEG, ASCII | Data |
| **5** | Session | Establish and manage sessions | RPC, NetBIOS | Data |
| **4** | Transport | Segmentation, reliability, flow control | TCP, UDP | Segment/Datagram |
| **3** | Network | Logical addressing and routing | IP, ICMP, OSPF, BGP | Packet |
| **2** | Data Link | Framing, MAC addressing, error detection | Ethernet, PPP, 802.1Q | Frame |
| **1** | Physical | Signals, media, connectors | Copper, fibre, radio | Bits |

> 🧠 **Mnemonic — top down:** *All People Seem To Need Data Processing.*

### 📦 Encapsulation Flow

```text
Application data
   ↓ Transport header
Segment
   ↓ IP header
Packet
   ↓ Ethernet header/trailer
Frame
   ↓ Physical transmission
Bits
```

---

## 🖧 Common Network Devices

| Device | Typical Layer | Purpose |
|---|---:|---|
| **Router** | 3 | Routes traffic between networks; may perform NAT, DHCP and ACL filtering |
| **Switch** | 2 / 3 | Forwards frames by MAC address; may route with SVIs |
| **Firewall** | 3–7 | Allows or blocks traffic according to policy |
| **Wireless AP** | 2 | Bridges wireless clients to the wired LAN |
| **Load Balancer** | 4 / 7 | Distributes requests across multiple servers |
| **IDS / IPS** | 3–7 | Detects or blocks suspicious traffic |
| **Proxy** | 7 | Intermediary for filtering, privacy, inspection and caching |
| **VPN Concentrator** | 3+ | Terminates and manages many encrypted tunnels |

> 💡 **Exam tip:** distinguish the device’s *primary function* from optional features built into modern appliances.

---

## ☁️ Cloud Concepts

### Service Models

| Model | Provider Manages | Customer Manages | Example Workload |
|---|---|---|---|
| **IaaS** | Hardware, virtualisation | OS, applications, data | Virtual machines |
| **PaaS** | Infrastructure and runtime | Application and data | Web application platform |
| **SaaS** | Entire service stack | Usage, data governance | Microsoft 365 |

### Deployment Models

- 🌍 **Public cloud:** shared provider infrastructure
- 🏢 **Private cloud:** dedicated to one organisation
- 🔄 **Hybrid cloud:** integrates public and private environments

### Connectivity

- 🔐 **Site-to-site VPN:** encrypted connection over the internet
- 🚇 **Private circuit:** dedicated provider connection such as ExpressRoute or Direct Connect
- 🕸️ **VPC/VNet:** isolated logical network inside a cloud platform
- 🧩 **NFV:** network functions delivered as virtual appliances or software

---

## 🔌 Core Ports and Protocols

| Protocol | Port | Transport | Purpose |
|---|---:|---|---|
| SSH / SFTP | 22 | TCP | Secure administration and file transfer |
| DNS | 53 | UDP/TCP | Name resolution and zone transfer |
| DHCP | 67/68 | UDP | Dynamic addressing |
| HTTP | 80 | TCP | Web traffic |
| HTTPS | 443 | TCP | Encrypted web traffic |
| SMTP | 25 | TCP | Sending mail |
| POP3 | 110 | TCP | Downloading mail |
| IMAP | 143 | TCP | Synchronised mail access |
| SNMP | 161/162 | UDP | Monitoring and traps |
| LDAP / LDAPS | 389/636 | TCP | Directory access |
| SMB | 445 | TCP | File and printer sharing |
| RDP | 3389 | TCP/UDP | Windows remote desktop |

### TCP vs UDP

- ✅ **TCP:** connection-oriented, acknowledgements, sequencing and retransmission
- ⚡ **UDP:** connectionless, low overhead, suitable for time-sensitive traffic

---

## 🧰 Common Network Services

### DHCP — DORA

```text
Discover → Offer → Request → Acknowledge
```

### DNS Records

| Record | Purpose |
|---|---|
| **A** | Hostname to IPv4 address |
| **AAAA** | Hostname to IPv6 address |
| **CNAME** | Alias to another hostname |
| **MX** | Mail exchanger |
| **PTR** | Reverse lookup |

### NAT and PAT

- **NAT:** translates one address space into another
- **PAT:** allows many private hosts to share one public IP using port numbers

### NTP and IPAM

- ⏱️ **NTP:** synchronises time for logs, authentication and event correlation
- 🗺️ **IPAM:** tracks address assignments, subnets, pools and utilisation

---

## 📣 Traffic Types

| Type | Communication Pattern | Typical Use |
|---|---|---|
| **Unicast** | One to one | Most client/server traffic |
| **Broadcast** | One to all in local IPv4 segment | ARP, DHCP Discover |
| **Multicast** | One to selected group | Streaming, routing updates |
| **Anycast** | One to nearest instance | DNS and distributed services |

---

## 🧭 Topologies and Network Types

### Topologies

- ⭐ **Star:** endpoints connect to a central switch
- 🚌 **Bus:** all nodes share one backbone
- 🔄 **Ring:** nodes form a loop
- 🕸️ **Mesh:** multiple redundant paths
- 🧬 **Hybrid:** combination of designs

### Network Types

- **LAN:** local office or building
- **WAN:** geographically distributed locations
- **MAN:** metropolitan area
- **CAN:** campus or multi-building organisation
- **PAN:** personal short-range network

---

## 🚀 Emerging Technologies

| Technology | Key Idea |
|---|---|
| **SDN** | Separates and centralises the control plane |
| **SD-WAN** | Policy-driven WAN path selection across multiple links |
| **Zero Trust** | Never trust by location; continuously verify identity and context |
| **IaC** | Defines infrastructure in version-controlled code |
| **VXLAN** | Extends Layer 2 segmentation across Layer 3 networks |
| **SASE** | Combines WAN and cloud-delivered security services |
| **SSE** | Security-focused part of SASE: SWG, CASB and ZTNA |

### IPv6 Transition

- 🔁 **Dual stack:** run IPv4 and IPv6 together
- 🚇 **Tunnelling:** carry IPv6 inside IPv4
- 🔄 **NAT64/DNS64:** enable IPv6 clients to reach IPv4-only services

---

## 🧠 Exam Focus

> **Memorise:** OSI layers, PDUs, common ports, cloud models, traffic types and basic network services.
>
> **Understand:** why one protocol, device or design is more appropriate than another in a scenario.

---

## ✅ Review Checklist

- [ ] I can explain every OSI layer without notes
- [ ] I can identify common ports and protocols
- [ ] I understand TCP vs UDP
- [ ] I can compare cloud service and deployment models
- [ ] I can explain DHCP, DNS, NAT, PAT, NTP and IPAM
- [ ] I can identify traffic types and network topologies
- [ ] I can explain SDN, SD-WAN, SASE and Zero Trust

---

<div align="center">

### 📘 Continue Your Journey

[🏠 Repository Home](../../README.md) • [➡️ Next: Network Implementation](../02-networking-implementation/README.md)

**Created by [Toan Nguyen](https://github.com/toannguyenitoz) • Adelaide, Australia**

[⬆ Back to Top](#1️⃣-domain-1--networking-concepts)

</div>
