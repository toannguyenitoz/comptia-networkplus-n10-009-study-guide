<div align="center">

# 5️⃣ Domain 5 — Network Troubleshooting

### *Methodology • physical faults • services • performance • tools*

[![Weight](https://img.shields.io/badge/Exam_Weight-24%25-EA1D2C?style=for-the-badge)](#-exam-focus)
[![Priority](https://img.shields.io/badge/Priority-Highest-0A66C2?style=for-the-badge)](#-learning-objectives)
[![Status](https://img.shields.io/badge/Notes-Ready-success?style=for-the-badge)](#)

[⬅️ Domain 4](../04-network-security/README.md) • [🏠 Home](../../README.md) • [🧪 Labs](../../labs/README.md)

</div>

---

## 🎯 Learning Objectives

- 🧭 Apply the six-step troubleshooting methodology
- 🔌 Diagnose cable, transceiver, interface and duplex faults
- 🌍 Resolve DHCP, DNS, gateway, routing, NAT and VLAN issues
- 📈 Identify latency, jitter, loss, saturation and wireless problems
- 🧰 Select the correct command or hardware tool for the symptom

---

## 🧭 Six-Step Methodology

1. **Identify the problem** — gather symptoms, scope, logs and recent changes.
2. **Establish a theory** — start with the simplest probable cause and use the OSI model.
3. **Test the theory** — isolate variables and confirm or reject the cause.
4. **Plan and implement** — assess impact, obtain approval and prepare rollback.
5. **Verify functionality** — test the service end to end and confirm with users.
6. **Document findings** — record cause, action, evidence and prevention.

> 🧠 **Golden rule:** do not change several variables at once. A fix without proof is only a guess.

---

## 🔌 Physical and Interface Issues

| Symptom | Probable Cause | Test / Action |
|---|---|---|
| No link light | Cable, port, power or transceiver failure | Swap known-good components |
| CRC errors | Interference, damaged cable or connector | Check counters and cable quality |
| Late collisions | Duplex mismatch | Match speed and duplex settings |
| Interface flapping | Bad cable, SFP, port or power | Review logs and replace components |
| Runts / giants | Framing, MTU or hardware issue | Inspect counters and packet captures |
| Weak fibre signal | Dirty connector, bend or wrong optic | Clean, inspect and test optical path |

### Copper and Fibre Limits

- Standard copper Ethernet channel: typically **100 metres maximum**
- Match single-mode optics to single-mode fibre
- Match multimode optics to supported multimode fibre
- Respect fibre bend radius and connector cleanliness

---

## 🧰 Physical Tools

| Tool | Best Use |
|---|---|
| **Cable tester** | Continuity, wire map and pinout |
| **TDR** | Distance to copper fault |
| **OTDR** | Fibre loss and break location |
| **Tone generator/probe** | Trace an unknown cable |
| **Loopback plug** | Test a port or interface |
| **Multimeter** | Electrical checks where appropriate |

---

## 🌍 Service Troubleshooting Matrix

### DHCP

**Symptoms:** APIPA address, missing gateway, no network access.

**Check:** scope utilisation, server status, VLAN, relay/helper address, security controls.

```powershell
ipconfig /all
ipconfig /release
ipconfig /renew
```

### DNS

**Symptoms:** IP addresses work but hostnames fail.

**Check:** configured resolver, suffix, record, recursion, firewall and cache.

```powershell
nslookup example.com
ipconfig /displaydns
ipconfig /flushdns
```

### Gateway and Routing

**Symptoms:** local access works but remote networks fail.

**Check:** default gateway, route table, next hop, routing protocol and ACL.

```powershell
ping <gateway>
tracert <destination>
route print
```

### NAT and Firewall

**Symptoms:** internal users cannot reach the internet or published services fail.

**Check:** translation rules, direction, ACL order, port mapping and session logs.

### VLAN and Trunk

**Symptoms:** same-department hosts cannot communicate or a VLAN disappears across switches.

**Check:** access VLAN, trunk state, allowed VLAN list, native VLAN and STP.

```text
show vlan brief
show interfaces trunk
show spanning-tree
```

---

## 📦 MTU Problems

Typical clues:

- Small packets succeed but large packets fail
- Some web pages partially load
- VPN users reach only selected resources

Windows test example:

```powershell
ping 8.8.8.8 -f -l 1472
```

Reduce the payload until the packet succeeds without fragmentation, then account for protocol headers.

---

## 📈 Performance Issues

| Problem | Observable Effect | Common Causes |
|---|---|---|
| **High latency** | Slow response | Congestion, long path, overloaded device |
| **Jitter** | Choppy voice/video | Variable queuing and congestion |
| **Packet loss** | Drops and retransmissions | Faulty media, interference, congestion |
| **Saturation** | Peak-hour slowdown | Backups, streaming, top talkers |
| **Low throughput** | Transfer below expected speed | Loss, duplex, shaping, server bottleneck |

### Wireless Symptoms

- 📶 **Poor signal:** adjust AP position, power and coverage
- 📻 **Co-channel interference:** redesign channels and cell sizes
- 👥 **AP overload:** distribute clients and add capacity
- 🚶 **Roaming failure:** check overlap, security consistency and 802.11k/r/v support
- 🔐 **Authentication delay:** inspect RADIUS, certificates and time synchronisation

---

## 💻 Command-Line Toolbox

| Tool | Purpose |
|---|---|
| `ping` | Reachability, latency and loss |
| `tracert` / `traceroute` | Path and hop analysis |
| `ipconfig` / `ip` | Addressing and interface state |
| `nslookup` / `dig` | DNS testing |
| `netstat` / `ss` | Connections and listening ports |
| `arp` / `ip neigh` | Local IP-to-MAC mappings |
| `route print` / `ip route` | Routing table |
| `pathping` | Combined path and loss analysis on Windows |
| `tcpdump` / Wireshark | Packet capture and protocol analysis |

---

## 🧪 Scenario Workflow

> **User report:** “The internet is down.”

1. Confirm whether the issue affects one device, one VLAN, one site or everyone.
2. Check link, IP address, gateway and DNS configuration.
3. Ping loopback, local IP, gateway, remote IP and hostname—in that order.
4. Trace the route and inspect firewall/NAT logs.
5. Compare with a working device and recent changes.
6. Apply the smallest safe fix, verify and document.

---

## 🧠 Exam Focus

> Domain 5 rewards **ordered thinking**. Identify the most likely cause from the evidence, then select the least disruptive test or correction.

Watch for qualifiers such as **FIRST**, **BEST**, **MOST likely** and **NEXT**.

---

## ✅ Review Checklist

- [ ] I can recite the six troubleshooting steps
- [ ] I can interpret CRC, collision and flapping symptoms
- [ ] I can diagnose DHCP, DNS and gateway failures
- [ ] I understand VLAN, trunk, NAT and MTU issues
- [ ] I can distinguish latency, jitter, loss and saturation
- [ ] I know which command or physical tool to use
- [ ] I document root cause and verification evidence

---

<div align="center">

[⬅️ Previous](../04-network-security/README.md) • [🏠 Home](../../README.md) • [🧪 Practise Labs](../../labs/README.md)

**Created by [Toan Nguyen](https://github.com/toannguyenitoz) • Adelaide, Australia**

[⬆ Back to Top](#5️⃣-domain-5--network-troubleshooting)

</div>
