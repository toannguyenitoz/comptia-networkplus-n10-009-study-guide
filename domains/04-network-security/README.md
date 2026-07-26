<div align="center">

# 4️⃣ Domain 4 — Network Security

### *CIA • AAA • attacks • hardening • segmentation • access control*

[![Weight](https://img.shields.io/badge/Exam_Weight-14%25-EA1D2C?style=for-the-badge)](#-exam-focus)
[![Focus](https://img.shields.io/badge/Focus-Security-0A66C2?style=for-the-badge)](#-learning-objectives)
[![Status](https://img.shields.io/badge/Notes-Ready-success?style=for-the-badge)](#)

[⬅️ Domain 3](../03-network-operations/README.md) • [🏠 Home](../../README.md) • [➡️ Domain 5](../05-network-troubleshooting/README.md)

</div>

---

## 🎯 Learning Objectives

- 🔐 Explain CIA, AAA, Zero Trust and defence in depth
- 🚨 Recognise common social-engineering, malware, network and wireless attacks
- 🛡️ Apply device hardening, segmentation, secure protocols and ACLs
- 👤 Compare authentication methods, access-control models and directory services
- 🧪 Select practical mitigations for realistic scenarios

---

## 🔺 CIA Triad

| Principle | Objective | Typical Controls |
|---|---|---|
| **Confidentiality** | Prevent unauthorised disclosure | Encryption, permissions, segmentation |
| **Integrity** | Prevent or detect unauthorised change | Hashing, signatures, checksums |
| **Availability** | Keep systems and services accessible | Redundancy, failover, DDoS protection |

---

## 👤 AAA

- **Authentication:** proves identity
- **Authorisation:** determines permitted actions
- **Accounting:** records activity for audit and investigation

> 🧠 **Memory aid:** *Who are you? What may you do? What did you do?*

---

## 🧱 Defence in Depth and Zero Trust

### Defence in Depth

Use multiple independent layers so one failed control does not expose the entire environment:

```text
Physical security → Identity → Endpoint → Network → Application → Data → Monitoring
```

### Zero Trust

> **Never trust by location; always verify identity, device health, context and requested access.**

Core ideas:

- 🔎 Continuous verification
- 🎯 Least-privilege access
- 🧩 Micro-segmentation
- 📱 Device compliance
- 📊 Logging and behavioural analysis

---

## ⚠️ Risk Terminology

| Term | Meaning |
|---|---|
| **Threat** | Actor or event capable of causing harm |
| **Vulnerability** | Weakness that may be exploited |
| **Exploit** | Method used to take advantage of a vulnerability |
| **Risk** | Likelihood and impact of a threat exploiting a weakness |
| **Mitigation** | Control that reduces likelihood or impact |

---

## 🎣 Social Engineering

| Attack | Description |
|---|---|
| **Phishing** | Fraudulent message sent broadly |
| **Spear phishing** | Targeted message crafted for a victim |
| **Whaling** | Targets executives or senior leaders |
| **Smishing** | SMS-based phishing |
| **Vishing** | Voice-call phishing |
| **Pretexting** | Fabricated scenario used to gain trust |
| **Tailgating** | Following an authorised person into a restricted area |

### Mitigations

- 🎓 Awareness training
- 🔐 MFA
- ✉️ Mail filtering
- ☎️ Independent verification
- 🚪 Physical access controls

---

## 🦠 Malware and Availability Attacks

- **Virus:** attaches to a host file
- **Worm:** self-replicates across networks
- **Trojan:** appears legitimate but contains malicious functionality
- **Ransomware:** encrypts or steals data for extortion
- **Spyware / keylogger:** collects user or activity information
- **Rootkit:** conceals malicious presence or privileged control
- **DoS:** one source overwhelms a target
- **DDoS:** many distributed sources overwhelm a target

---

## 🕵️ Network Attacks

### Man-in-the-Middle

An attacker intercepts or manipulates communication between two parties.

**Mitigations:** TLS, IPsec, certificate validation, secure Wi-Fi and network inspection.

### ARP Spoofing

The attacker poisons ARP associations to redirect local traffic.

**Mitigations:** Dynamic ARP Inspection, DHCP snooping, segmentation and secure switching.

### MAC Flooding

The attacker overwhelms a switch CAM table to force excessive flooding.

**Mitigation:** switch port security and MAC limits.

### VLAN Hopping

The attacker attempts to access another VLAN through switch spoofing or double tagging.

**Mitigations:**

- Disable dynamic trunk negotiation
- Use explicit access/trunk modes
- Use an unused native VLAN
- Restrict allowed VLANs
- Avoid using VLAN 1 for normal user traffic

### DNS Poisoning

False DNS information redirects users to malicious destinations.

**Mitigations:** DNSSEC validation, secure resolvers, monitoring and endpoint protection.

### Rogue AP / Evil Twin

- **Rogue AP:** unauthorised access point connected to the network
- **Evil twin:** malicious AP impersonating a trusted WLAN

**Mitigations:** wireless IDS/IPS, 802.1X, certificate-based authentication and AP inventory.

---

## 🛡️ Network Hardening

### Device Checklist

- [ ] Change default credentials
- [ ] Patch firmware and operating systems
- [ ] Disable unused ports and services
- [ ] Use SSH, HTTPS and SNMPv3
- [ ] Restrict management access
- [ ] Back up configurations
- [ ] Send logs to a central platform
- [ ] Enforce secure time synchronisation

### Secure Protocol Replacements

| Avoid | Prefer |
|---|---|
| Telnet | SSH |
| HTTP management | HTTPS |
| FTP | SFTP / FTPS |
| SNMPv1/v2c | SNMPv3 |
| Unencrypted LDAP | LDAPS where supported |

---

## 🧩 Segmentation, ACLs and NAC

### VLAN Segmentation

Separate departments, guests, servers, management interfaces and IoT devices into distinct security zones.

### ACL Principles

- Rules are evaluated in order
- First matching rule normally wins
- Match source, destination, protocol and port
- An implicit deny often exists at the end
- Place rules deliberately and document intent

### Network Access Control

NAC checks identity and device posture before granting access.

Typical components:

- 802.1X supplicant
- Authenticator switch or AP
- RADIUS authentication server
- Dynamic VLAN or quarantine policy

---

## 🔥 Firewall Types

| Type | Capability |
|---|---|
| **Stateless packet filter** | Evaluates packet headers independently |
| **Stateful firewall** | Tracks established sessions |
| **Next-generation firewall** | Adds application awareness and deep inspection |
| **Host firewall** | Protects an individual endpoint |
| **FWaaS** | Cloud-delivered firewall service |

---

## 🔑 Authentication and Access Control

### Authentication Factors

- 🧠 Something you know — password or PIN
- 📱 Something you have — phone, token or smartcard
- 🧬 Something you are — biometric characteristic

### Access Models

| Model | Decision Basis |
|---|---|
| **RBAC** | User’s assigned role |
| **ABAC** | Attributes of user, resource, device and context |
| **Least privilege** | Minimum access required for the task |

### Directory and Authentication Services

- **LDAP 389 / LDAPS 636:** directory query protocols
- **Active Directory:** Microsoft identity, policy and resource directory
- **RADIUS:** common for VPN, Wi-Fi and 802.1X access
- **TACACS+:** commonly used for granular network-device administration
- **PKI/X.509:** certificate-based trust and authentication

---

## 🧠 Exam Focus

> Match each attack to its strongest practical mitigation. Pay attention to whether the scenario concerns identity, Layer 2 switching, wireless access, DNS, device management or traffic filtering.

---

## ✅ Review Checklist

- [ ] I can define CIA and AAA
- [ ] I understand Zero Trust and defence in depth
- [ ] I can identify phishing and malware types
- [ ] I can explain ARP spoofing, MAC flooding and VLAN hopping
- [ ] I know secure replacements for clear-text protocols
- [ ] I understand VLAN segmentation, ACLs and NAC
- [ ] I can compare RADIUS and TACACS+

---

<div align="center">

[⬅️ Previous](../03-network-operations/README.md) • [🏠 Home](../../README.md) • [➡️ Next](../05-network-troubleshooting/README.md)

**Created by [Toan Nguyen](https://github.com/toannguyenitoz) • Adelaide, Australia**

[⬆ Back to Top](#4️⃣-domain-4--network-security)

</div>
