<div align="center">

# 🧪 Network+ Hands-On Labs

### *Build it • break it • observe it • troubleshoot it • document it*

[![Labs](https://img.shields.io/badge/Labs-Practical-0A66C2?style=for-the-badge)](#-lab-roadmap)
[![Platforms](https://img.shields.io/badge/Tools-Packet_Tracer_%7C_Wireshark_%7C_CLI-EA1D2C?style=for-the-badge)](#-recommended-tools)
[![Status](https://img.shields.io/badge/Status-Expanding-success?style=for-the-badge)](#)

[🏠 Home](../README.md) • [⚡ Cheat Sheets](../cheat-sheets/README.md) • [🛠️ Troubleshooting](../domains/05-network-troubleshooting/README.md)

</div>

---

## 🎯 Purpose

These labs turn theory into evidence. Each activity should produce a configuration, packet capture, screenshot, verification command or troubleshooting record suitable for a technical portfolio.

> 📋 **Lab standard:** objective → topology → configuration → verification → fault injection → resolution → lessons learned.

---

## 🧰 Recommended Tools

- 🖧 **Cisco Packet Tracer** — routing, switching, VLAN and wireless simulation
- 🦈 **Wireshark** — packet capture and protocol analysis
- 🪟 **Windows PowerShell / Command Prompt** — endpoint diagnostics
- 🐧 **Linux terminal** — `ip`, `dig`, `ss`, `tcpdump`, `traceroute`
- 🧱 **VirtualBox / VMware** — isolated client/server environments
- 📝 **Markdown** — lab documentation and evidence

---

## 🗺️ Lab Roadmap

| Lab | Topic | Primary Skill | Difficulty |
|---:|---|---|---|
| 01 | Local IP investigation | `ipconfig`, gateway and DNS | 🟢 Beginner |
| 02 | DNS resolution | `nslookup`, cache and records | 🟢 Beginner |
| 03 | Path analysis | `ping`, `tracert`, `pathping` | 🟢 Beginner |
| 04 | VLAN segmentation | Access ports and VLANs | 🟡 Intermediate |
| 05 | 802.1Q trunking | Multi-switch VLAN transport | 🟡 Intermediate |
| 06 | Inter-VLAN routing | Router-on-a-stick or SVI | 🟡 Intermediate |
| 07 | DHCP relay | Multi-subnet address assignment | 🟡 Intermediate |
| 08 | STP redundancy | Root bridge and blocked paths | 🟡 Intermediate |
| 09 | Link aggregation | LACP and failover | 🟠 Advanced |
| 10 | Wireshark protocol analysis | DNS, DHCP and TCP | 🟡 Intermediate |
| 11 | ACL segmentation | Permit/deny traffic policy | 🟠 Advanced |
| 12 | Troubleshooting challenge | Multi-fault diagnosis | 🔴 Scenario |

---

## 🧪 Lab 01 — Windows Network Baseline

### Objective

Document a Windows endpoint’s addressing, gateway, DNS and active connections.

### Commands

```powershell
hostname
ipconfig /all
route print
arp -a
netstat -ano
```

### Evidence

- Interface name and MAC address
- IPv4/IPv6 addresses
- DHCP status and lease information
- Default route
- DNS server
- ARP entries

### Fault Injection

Configure an incorrect DNS server, observe the symptoms, then restore the correct setting.

---

## 🧪 Lab 02 — DNS Resolution

```powershell
nslookup example.com
nslookup -type=mx example.com
ipconfig /displaydns
ipconfig /flushdns
```

### Questions

1. Which DNS server answered?
2. Was the response authoritative or recursive?
3. What changes after flushing the cache?
4. Can the host ping an IP when hostname resolution fails?

---

## 🧪 Lab 03 — Layered Connectivity Test

Test in this order:

```text
1. Loopback
2. Local interface
3. Default gateway
4. Remote IP
5. Remote hostname
6. Application service
```

This sequence separates local TCP/IP, LAN, routing, DNS and application failures.

---

## 🧪 Lab 04 — VLAN and Trunk

### Suggested Topology

```text
PC-A ─ SW1 ═══ 802.1Q trunk ═══ SW2 ─ PC-B
        VLAN 10                   VLAN 10
```

### Verification

```text
show vlan brief
show interfaces trunk
show interfaces switchport
show mac address-table
```

### Faults to Introduce

- Wrong access VLAN
- VLAN missing from trunk allowed list
- Native VLAN mismatch
- Trunk configured as access

---

## 🧪 Lab 05 — Wireshark Analysis

Capture and identify:

- DHCP Discover, Offer, Request and Acknowledge
- DNS query and response
- TCP three-way handshake
- ICMP echo request and reply
- TLS session establishment metadata

### Useful Display Filters

```text
dhcp
dns
icmp
tcp.flags.syn == 1
tcp.analysis.retransmission
```

> 🔐 Do not upload packet captures containing credentials, personal data or confidential traffic.

---

## 🧪 Lab 06 — Troubleshooting Ticket

### Scenario

A user receives `169.254.x.x`, cannot reach the gateway and reports that “Wi-Fi is connected but nothing works”.

### Required Output

- Incident summary
- Scope and impact
- Evidence collected
- Probable cause
- Tests performed
- Resolution
- Verification
- Prevention or follow-up action

---

## 📄 Lab Documentation Template

```markdown
# Lab XX — Title

## Objective
## Environment / Topology
## Prerequisites
## Configuration
## Verification Commands
## Expected Result
## Fault Introduced
## Troubleshooting Process
## Resolution
## Evidence
## Lessons Learned
```

---

## ✅ Completion Standard

A lab is complete when:

- [ ] The objective is clear
- [ ] The topology is documented
- [ ] Commands and configurations are reproducible
- [ ] Verification proves success
- [ ] At least one fault is diagnosed
- [ ] Sensitive information is removed
- [ ] Lessons learned are recorded

---

<div align="center">

[🏠 Repository Home](../README.md) • [⚡ Review Cheat Sheets](../cheat-sheets/README.md)

**Created by [Toan Nguyen](https://github.com/toannguyenitoz) • Adelaide, Australia**

[⬆ Back to Top](#-network-hands-on-labs)

</div>
