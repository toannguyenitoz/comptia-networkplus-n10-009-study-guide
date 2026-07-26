<div align="center">

# 2️⃣ Domain 2 — Network Implementation

### *Routing • switching • wireless • addressing • physical design*

[![Weight](https://img.shields.io/badge/Exam_Weight-20%25-EA1D2C?style=for-the-badge)](#-exam-focus)
[![Focus](https://img.shields.io/badge/Focus-Hands--On-0A66C2?style=for-the-badge)](#-learning-objectives)
[![Status](https://img.shields.io/badge/Notes-Ready-success?style=for-the-badge)](#)

[⬅️ Domain 1](../01-networking-concepts/README.md) • [🏠 Home](../../README.md) • [➡️ Domain 3](../03-network-operations/README.md)

</div>

---

## 🎯 Learning Objectives

- 🧭 Compare static and dynamic routing
- 🔀 Configure and verify VLANs, trunks, STP and link aggregation
- 📡 Select wireless standards, channels and security modes
- 🌍 Explain DHCP, DNS, NTP, IPAM and APIPA
- 🧱 Compare physical and logical topologies

---

## 🧭 Routing Technologies

### Static vs Dynamic Routing

| Type | Strength | Limitation | Best Use |
|---|---|---|---|
| **Static** | Predictable, low overhead | Manual changes, limited scalability | Small or stub networks |
| **Dynamic** | Learns and adapts automatically | CPU, memory and protocol overhead | Medium and large networks |

### Major Protocols

| Protocol | Type | Metric / Decision | Key Point |
|---|---|---|---|
| **RIP** | Distance-vector | Hop count | Maximum 15 hops |
| **OSPF** | Link-state | Cost | Fast convergence and areas |
| **EIGRP** | Advanced distance-vector | Bandwidth and delay | Common in Cisco environments |
| **BGP** | Path-vector | Path attributes and policy | Internet and inter-AS routing |

### Administrative Distance

> Lower administrative distance means the route source is considered more trustworthy.

| Source | Typical AD |
|---|---:|
| Connected | 0 |
| Static | 1 |
| eBGP | 20 |
| EIGRP | 90 |
| OSPF | 110 |
| RIP | 120 |

### Longest Prefix Match

A router prefers the **most specific matching route**. For example, `/24` is preferred over `/16` for an address that matches both.

---

## ⚖️ Bandwidth Management and QoS

- 🚦 **Classification:** identify traffic by application, port, protocol, user or address
- 🏷️ **Marking:** apply DSCP or CoS values
- 📥 **Queuing:** prioritise selected traffic
- 🌊 **Shaping:** buffer and delay excess traffic
- 🚨 **Policing:** drop or remark traffic exceeding a limit

> 🎧 **Scenario:** voice traffic needs low latency, low jitter and low packet loss—not merely high bandwidth.

---

## 🔀 VLANs and Trunking

| Port Type | Behaviour |
|---|---|
| **Access** | Carries one VLAN for an endpoint |
| **Trunk** | Carries multiple VLANs using 802.1Q tags |
| **Native VLAN** | Untagged VLAN on an 802.1Q trunk |

### Inter-VLAN Routing

- 🧩 **Router-on-a-stick:** router subinterfaces provide gateways for multiple VLANs
- ⚡ **Layer 3 switch:** switch virtual interfaces route between VLANs

### Verification Commands

```text
show vlan brief
show interfaces trunk
show interfaces switchport
show ip interface brief
show ip route
```

---

## 🌳 Spanning Tree Protocol

STP prevents Layer 2 loops by selecting a loop-free topology and blocking redundant paths.

### Key Terms

- 👑 **Root bridge:** switch with the lowest bridge ID
- 🌱 **Root port:** best path from a non-root switch to the root
- 🎯 **Designated port:** forwarding port for a segment
- ⛔ **Alternate/blocking port:** redundant path held in reserve

### Versions and Enhancements

| Feature | Purpose |
|---|---|
| **802.1D STP** | Original spanning tree |
| **802.1w RSTP** | Faster convergence |
| **802.1s MSTP** | Maps multiple VLANs to spanning-tree instances |
| **PortFast** | Rapid forwarding for endpoint ports |
| **BPDU Guard** | Shuts an edge port receiving unexpected BPDUs |

---

## 🔗 Link Aggregation and Redundancy

- **LACP (802.3ad/802.1AX):** standards-based link aggregation
- **PAgP:** Cisco proprietary negotiation protocol
- **HSRP:** Cisco active/standby gateway redundancy
- **VRRP:** standards-based master/backup redundancy
- **GLBP:** gateway redundancy with load balancing

---

## 🔐 Switch Port Security

Port security limits which MAC addresses may use a switch port.

| Violation Mode | Result |
|---|---|
| **Protect** | Drops unauthorised traffic silently |
| **Restrict** | Drops traffic and records the violation |
| **Shutdown** | Places the port into an error-disabled state |

---

## ⚡ Power over Ethernet

| Standard | Common Name | Approximate Power |
|---|---|---:|
| 802.3af | PoE | 15.4 W at source |
| 802.3at | PoE+ | 30 W at source |
| 802.3bt | PoE++ | Up to 60–90 W by type |

Typical devices include access points, IP phones, cameras and access-control readers.

---

## 📡 Wireless Technologies

### Standards Overview

| Standard | Bands | Key Feature |
|---|---|---|
| 802.11a | 5 GHz | Legacy 54 Mbps |
| 802.11b/g | 2.4 GHz | Legacy compatibility |
| 802.11n | 2.4/5 GHz | MIMO |
| 802.11ac | 5 GHz | Wider channels and MU-MIMO |
| 802.11ax | 2.4/5/6 GHz | OFDMA and improved density |

### Channel Planning

- 📻 **2.4 GHz:** broad coverage but greater interference; commonly use non-overlapping channels 1, 6 and 11 where applicable
- 🚀 **5 GHz:** more channels and less interference; shorter practical range
- ✨ **6 GHz:** clean spectrum for Wi-Fi 6E/7-capable devices

### Security

| Security | Status |
|---|---|
| **WEP** | Broken and deprecated |
| **WPA/TKIP** | Legacy and not recommended |
| **WPA2/AES** | Widely supported secure baseline |
| **WPA3/SAE** | Stronger modern protection |
| **802.1X + RADIUS** | Enterprise per-user/device authentication |

### Wireless Identifiers

- **SSID:** network name
- **BSSID:** MAC address of a specific AP radio
- **ESS:** multiple APs providing a common WLAN for roaming

---

## 🌍 Network Services

### DHCP Options

| Option | Meaning |
|---:|---|
| 3 | Default gateway |
| 6 | DNS server |
| 15 | Domain name |

> 🔁 A **DHCP relay** forwards broadcast-based client requests to a server on another subnet.

### APIPA

`169.254.0.0/16` indicates that an IPv4 client could not obtain a DHCP lease and self-assigned a link-local address.

---

## 🧱 Physical and Logical Topologies

- ⭐ **Star:** central switch; common and scalable
- 🕸️ **Mesh:** multiple paths; resilient but more costly
- 🔄 **Ring:** each node links to the next
- 🚌 **Bus:** shared backbone; largely legacy
- 🧬 **Hybrid:** combines multiple topology types
- ➡️ **Point-to-point:** direct connection between two endpoints
- 📡 **Point-to-multipoint:** one central endpoint serves many remotes

---

## 🧠 Exam Focus

> Be ready to diagnose a scenario from configuration clues: wrong VLAN, missing allowed VLAN, native VLAN mismatch, STP block, DHCP relay error, unsuitable wireless channel or routing-table choice.

---

## ✅ Review Checklist

- [ ] I can compare RIP, OSPF, EIGRP and BGP
- [ ] I understand administrative distance and longest-prefix match
- [ ] I can explain access ports, trunks and native VLANs
- [ ] I understand STP roles and protections
- [ ] I can compare LACP, HSRP and VRRP
- [ ] I know wireless bands, standards and security modes
- [ ] I understand DHCP relay and common DHCP options

---

<div align="center">

[⬅️ Previous](../01-networking-concepts/README.md) • [🏠 Home](../../README.md) • [➡️ Next](../03-network-operations/README.md)

**Created by [Toan Nguyen](https://github.com/toannguyenitoz) • Adelaide, Australia**

[⬆ Back to Top](#2️⃣-domain-2--network-implementation)

</div>
