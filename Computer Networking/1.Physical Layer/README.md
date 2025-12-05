# 🌐 Physical Layer — Revision Notes

## 🔹 What is Physical Layer?
The **Physical Layer (Layer 1 of OSI)** is responsible for **transmitting raw bits (0s and 1s) over the physical medium**.  
It deals with **hardware, voltages, cables, connectors, modulation, transmission rate & physical signaling**.

---

## 🔹 Roles & Responsibilities
| Function | Meaning |
|---------|---------|
| Bit Transmission | Converts frames → bits and sends over medium |
| Topology | Bus / Star / Ring layout support |
| Data Rate | Bits per second supported |
| Synchronization | Clocking between sender/receiver |
| Physical Medium | Copper / Coaxial / Fiber |
| Modulation & Encoding | Digital ↔ Analog conversion, Manchester, NRZ etc. |

---

## 🔹 Network Devices & Functionalities

| Device | OSI Layer | Purpose | Pros | Cons | Where Used |
|--------|-----------|---------|------|------|------------|
| **Repeater** | L1 | Regenerates weak signals | Extends distance | No traffic filtering | Large LAN distances |
| **Hub** | L1 | Broadcasts packets to all | Cheap | Causes collisions | Lab networks |
| **Bridge** | L2 | Divides LAN into segments | Reduces collisions | Limited scalability | Small LAN separation |
| **Switch** | L2 | Filters & forwards using MAC | Fast, secure, removes collisions | Broadcast storms possible | Modern LANs |
| **Router** | L3 | Forwards packets using IP | Stops broadcasts | Expensive | Internet & WAN |
| **Gateway** | L5-7 | Protocol conversion | High flexibility | Complex | VoIP, HTTP, Email |
| **Firewall** | L3-7 | Blocks unauthorized traffic | High security | Misconfiguration risk | Enterprise security |
| **IDS** | L3-7 | Detects intrusion attempts | Attack monitoring | Only detects | Security alerting |
| **Modem** | L1 | Digital ↔ Analog conversion | Works over telephone | Slower vs fiber | Home internet services |

---

### 🔸 Communication Handling
| Device | Unicast | Broadcast | Filtering |
|--------|---------|-----------|-----------|
| Hub | ✔ | Always | ❌ |
| Switch | ✔ | ✔ | ✔ |
| Router | ✔ | ❌ (blocks) | ✔ |
| Gateway | ✔ | ❌ | ✔ |
| Firewall | ✔ | ❌ | ✔ |

---

## 🔹 Cables & Connectors

| Cable Type | Category | Connector | Speed | Use Case |
|------------|----------|-----------|--------|----------|
| **Twisted Pair (UTP/STP)** | Cat5 / Cat5e / Cat6 / Cat7 | **RJ-45** | Up to 10 Gbps | LAN |
| **Coaxial** | Thicknet / Thinnet | **BNC** | Up to 10 Mbps | CCTV, ISP |
| **Fiber Optic** | Single-mode / Multi-mode | **LC / SC / ST** | Up to Tbps | Data centers |

🔹 **UTP** = Low cost, **STP** = EMI protection  
🔹 **Fiber** = fastest & longest distance

---

## 🔹 Quick 10Base-T Summary

10 → 10 Mbps

Base → Baseband transmission

T → Twisted-Pair cable

Max length → 100 meters

Topology → Star (Switch/Hub)

Connector → RJ-45


---

## 🧠 Cloud / Interview Notes
- Switch → filters by **MAC**, Router → routes by **IP**.
- Router reduces **broadcast domain**, Switch reduces **collision domain**.
- UTP is the **most used cable in LAN**, Fiber is **fastest for WAN/backbone**.
- Firewalls & IDS are **critical in Cloud VPC network security**.
- Modems enable **internet access**, but routers enable **network-to-network communication**.

---

## ⚡ Final 5-line Revision
Physical Layer transmits raw bits as electrical/optical signals.
Switch removes collisions; Router blocks broadcast & routes IP.
UTP + RJ45 = 10Base-T → 10 Mbps, 100 m, Star topology.
Fiber = highest speed & best long-distance medium.
Repeater regenerates signals; Hub broadcasts to all ports.

---
