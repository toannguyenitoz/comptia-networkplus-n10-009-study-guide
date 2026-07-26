<div align="center">

# ⚡ Network+ N10-009 Cheat Sheets

### *Fast revision for ports, models, services, routing, wireless and troubleshooting*

[![Format](https://img.shields.io/badge/Format-Quick_Reference-0A66C2?style=for-the-badge)](#-quick-reference)
[![Exam](https://img.shields.io/badge/Exam-N10--009-EA1D2C?style=for-the-badge)](../README.md)
[![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)](#)

[🏠 Home](../README.md) • [🧪 Labs](../labs/README.md) • [📚 Glossary](../glossary/README.md)

</div>

---

## 🧱 OSI at a Glance

| Layer | Name | Key Words | Device / Protocol Examples |
|---:|---|---|---|
| 7 | Application | User services | HTTP, DNS, SMTP |
| 6 | Presentation | Encryption, format | TLS, encoding |
| 5 | Session | Establish, maintain | RPC, NetBIOS |
| 4 | Transport | Ports, reliability | TCP, UDP |
| 3 | Network | IP, routing | Router, ICMP, OSPF |
| 2 | Data Link | Frames, MAC, VLAN | Switch, Ethernet |
| 1 | Physical | Signal, cable, radio | Hub, fibre, copper |

> 🧠 *All People Seem To Need Data Processing.*

---

## 🔌 Essential Ports

| Service | Port | Service | Port |
|---|---:|---|---:|
| FTP | 20/21 | SSH/SFTP | 22 |
| Telnet | 23 | SMTP | 25 |
| DNS | 53 | DHCP | 67/68 |
| HTTP | 80 | POP3 | 110 |
| NTP | 123 | IMAP | 143 |
| SNMP | 161/162 | HTTPS | 443 |
| SMB | 445 | Syslog | 514 |
| LDAP/LDAPS | 389/636 | RADIUS | 1812 |
| TACACS+ | 49 | RDP | 3389 |

---

## 🌍 IPv4 Quick Reference

### Private Address Ranges

```text
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
```

### Special Addresses

- `127.0.0.1` — loopback
- `169.254.0.0/16` — APIPA/link-local
- `0.0.0.0` — unspecified/default context
- `255.255.255.255` — limited broadcast

---

## 🔀 Switching Quick Reference

- **Access port:** one VLAN
- **Trunk port:** multiple VLANs with 802.1Q
- **Native VLAN:** untagged VLAN on trunk
- **STP:** prevents Layer 2 loops
- **LACP:** combines links for bandwidth and redundancy
- **Port security:** limits MAC addresses on a port
- **Inter-VLAN routing:** router subinterfaces or Layer 3 SVIs

---

## 🧭 Routing Quick Reference

| Protocol | Type | Metric / Behaviour |
|---|---|---|
| RIP | Distance-vector | Hop count, maximum 15 |
| OSPF | Link-state | Cost and areas |
| EIGRP | Advanced distance-vector | Bandwidth + delay |
| BGP | Path-vector | Policy and path attributes |

> 🎯 **Longest-prefix match** selects the most specific route before administrative distance is considered between competing route sources for that prefix.

---

## 📡 Wireless Quick Reference

- **2.4 GHz:** longer range, more interference
- **5 GHz:** more channels, higher capacity, shorter practical range
- **6 GHz:** cleaner spectrum for compatible devices
- **WPA2:** AES-based secure baseline
- **WPA3:** SAE and stronger modern security
- **802.1X:** enterprise authentication through RADIUS
- **SSID:** network name
- **BSSID:** AP radio MAC address

---

## 📈 Monitoring Quick Reference

| Tool | Best For |
|---|---|
| SNMP | Counters, status and traps |
| Syslog | Centralised event messages |
| NetFlow/IPFIX | Conversations and top talkers |
| Wireshark | Full packet analysis |
| SIEM | Correlation and security alerting |

---

## 🛡️ Security Quick Reference

- **CIA:** Confidentiality, Integrity, Availability
- **AAA:** Authentication, Authorisation, Accounting
- **Zero Trust:** verify every request; minimise trust and privilege
- **NAC:** validate identity/device before network access
- **ACL:** ordered permit/deny rules with implicit deny
- **Defence in depth:** multiple independent security layers

---

## 🧰 Troubleshooting Order

```text
Identify → Theory → Test → Plan/Implement → Verify → Document
```

### Windows Command Sequence

```powershell
ipconfig /all
ping 127.0.0.1
ping <local-IP>
ping <gateway>
ping 8.8.8.8
nslookup example.com
tracert example.com
route print
netstat -ano
```

---

## ✅ Final Review

- [ ] Ports and protocols
- [ ] OSI layers and PDUs
- [ ] VLAN, trunk and STP
- [ ] Routing protocol differences
- [ ] Wireless bands and security
- [ ] Monitoring tools and metrics
- [ ] CIA, AAA and Zero Trust
- [ ] Six-step troubleshooting process

---

<div align="center">

[🏠 Repository Home](../README.md) • [🧪 Apply It in Labs](../labs/README.md)

**Created by [Toan Nguyen](https://github.com/toannguyenitoz) • Adelaide, Australia**

[⬆ Back to Top](#-network-n10-009-cheat-sheets)

</div>
