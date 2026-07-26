<div align="center">

# 3️⃣ Domain 3 — Network Operations

### *Documentation • monitoring • resilience • remote access • lifecycle*

[![Weight](https://img.shields.io/badge/Exam_Weight-19%25-EA1D2C?style=for-the-badge)](#-exam-focus)
[![Focus](https://img.shields.io/badge/Focus-Operations-0A66C2?style=for-the-badge)](#-learning-objectives)
[![Status](https://img.shields.io/badge/Notes-Ready-success?style=for-the-badge)](#)

[⬅️ Domain 2](../02-network-implementation/README.md) • [🏠 Home](../../README.md) • [➡️ Domain 4](../04-network-security/README.md)

</div>

---

## 🎯 Learning Objectives

- 🗺️ Maintain physical, logical, rack and cable documentation
- 🔄 Apply change, configuration and lifecycle management
- 📈 Monitor availability with SNMP, Syslog, NetFlow and packet capture
- 🧯 Explain RPO, RTO, backup strategies and disaster recovery sites
- 🔐 Compare VPN, tunnelling, RADIUS, TACACS+ and remote tools

---

## 🗺️ Documentation and Asset Management

| Document | Purpose |
|---|---|
| **Physical diagram** | Devices, ports, cables and locations |
| **Logical diagram** | Subnets, VLANs, routing and traffic relationships |
| **Rack diagram** | Rack units, power and equipment placement |
| **Cable map** | Patch panel, wall jack and endpoint mapping |
| **Asset register** | Model, serial, owner, location, warranty and lifecycle |
| **IPAM record** | Subnets, static assignments, pools and utilisation |

> ✍️ **Good documentation answers:** *what exists, where it is, how it connects, who owns it and when it changed.*

---

## 🔄 Change and Configuration Management

### Change Workflow

```text
Request → Risk review → Approval → Implementation plan
        → Communication → Testing → Validation → Documentation
```

Every production change should include:

- 🎯 Objective and scope
- ⚠️ Risk and impact assessment
- 🧪 Test plan
- ↩️ Rollback plan
- 🕒 Maintenance window
- 📣 Stakeholder communication
- ✅ Post-change validation

### Configuration Management

- 📏 Establish secure baseline configurations
- 🧾 Store configurations in version control
- 💾 Back up network-device configurations
- 🔍 Audit drift from approved standards
- 🔄 Track firmware, patches and end-of-life dates

---

## 🤝 Service Levels and Baselines

### SLA Measures

- **Availability:** percentage uptime
- **Response time:** how quickly support acknowledges an incident
- **Resolution target:** expected restoration time
- **Latency / throughput:** agreed network performance

### Performance Baseline

A baseline records normal behaviour for comparison:

- CPU and memory
- Interface utilisation
- Latency, jitter and packet loss
- Error and discard rates
- Application response time

> 📌 A threshold says *when to alert*. A baseline says *what normal looks like*.

---

## 📈 Monitoring Technologies

| Technology | What It Provides | Typical Port |
|---|---|---:|
| **SNMP** | Device status, counters, polling and traps | UDP 161/162 |
| **Syslog** | Centralised event messages | UDP 514 commonly |
| **NetFlow/sFlow/IPFIX** | Traffic-flow visibility and top talkers | Varies |
| **Packet capture** | Full packet-level analysis | N/A |
| **SIEM** | Log correlation, alerting and investigation | Platform-dependent |

### SNMP Components

- 🤖 **Agent:** runs on the monitored device
- 🖥️ **NMS:** collects and displays information
- 📚 **MIB:** structured collection of manageable objects
- 🔐 **SNMPv3:** authentication and encryption; preferred over v1/v2c

### Key Metrics

| Metric | Meaning |
|---|---|
| **Latency** | Time for traffic to travel |
| **Jitter** | Variation in delay |
| **Packet loss** | Percentage of packets not delivered |
| **Throughput** | Actual successful transfer rate |
| **Utilisation** | Used capacity as a percentage |
| **Error rate** | CRC errors, drops and interface faults |

---

## 🦈 Packet Capture and Port Mirroring

**Port mirroring / SPAN** copies traffic from selected interfaces or VLANs to an analyser port.

Use Wireshark or tcpdump to inspect:

- TCP retransmissions
- DNS failures
- DHCP DORA exchanges
- TCP handshakes and resets
- MTU and fragmentation problems
- Unexpected clear-text protocols

> ⚠️ Capture only traffic you are authorised to inspect and protect sensitive packet data.

---

## 🧯 Disaster Recovery and High Availability

### Recovery Metrics

| Metric | Question It Answers |
|---|---|
| **RPO** | How much data loss is acceptable? |
| **RTO** | How quickly must service return? |
| **MTTR** | How long does repair usually take? |
| **MTBF** | How long does equipment usually operate between failures? |

### Backup Types

| Type | Backup Speed | Restore Complexity |
|---|---|---|
| **Full** | Slowest | Simplest |
| **Incremental** | Fastest | Requires full plus each incremental |
| **Differential** | Medium | Requires full plus latest differential |

### Recovery Sites

- 🧊 **Cold site:** facility only; longest recovery time
- 🌤️ **Warm site:** partial infrastructure; restoration still required
- 🔥 **Hot site:** operational duplicate; fastest and most expensive

### Availability Models

- ⚖️ **Active-active:** multiple systems serve traffic simultaneously
- 💤 **Active-passive:** standby system takes over after failure
- 🔗 **Link redundancy:** dual uplinks, WAN links and aggregated links
- 🖥️ **Hardware redundancy:** dual PSUs, NICs, storage and clustered nodes

---

## 🔐 Remote Access and Site-to-Site Connectivity

| Technology | Best Fit |
|---|---|
| **Site-to-site IPsec** | Securely connects two networks |
| **Remote-access VPN** | Connects an individual user |
| **SSL/TLS VPN** | Browser or client-based remote access |
| **GRE** | Encapsulates routed traffic but does not encrypt by itself |
| **Split tunnelling** | Sends corporate traffic through VPN and other traffic directly |

### RADIUS vs TACACS+

| Feature | RADIUS | TACACS+ |
|---|---|---|
| Transport | UDP | TCP |
| Common Port | 1812 | 49 |
| Primary Use | Network access, VPN, 802.1X | Device administration |
| AAA Handling | Authentication/authorisation often combined | Separates AAA functions |

### Remote Management

- 🔐 **SSH:** secure CLI management
- 🪟 **RDP:** Windows graphical remote access
- 🖥️ **VNC:** cross-platform remote desktop
- 🚫 **Telnet:** clear text; avoid
- 🧰 **Out-of-band:** console server or KVM when production access fails

---

## 🧠 Exam Focus

> Expect scenarios asking which document, monitoring source, recovery metric, backup type or remote-access method best fits a business requirement.

---

## ✅ Review Checklist

- [ ] I can distinguish physical and logical diagrams
- [ ] I can explain change control and rollback planning
- [ ] I understand SNMP, Syslog, NetFlow and SIEM
- [ ] I can define latency, jitter, throughput and utilisation
- [ ] I know RPO, RTO, MTTR and MTBF
- [ ] I can compare cold, warm and hot sites
- [ ] I can compare RADIUS and TACACS+

---

<div align="center">

[⬅️ Previous](../02-network-implementation/README.md) • [🏠 Home](../../README.md) • [➡️ Next](../04-network-security/README.md)

**Created by [Toan Nguyen](https://github.com/toannguyenitoz) • Adelaide, Australia**

[⬆ Back to Top](#3️⃣-domain-3--network-operations)

</div>
