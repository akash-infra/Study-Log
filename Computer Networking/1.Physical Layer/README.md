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
# 🔀 Switching Techniques — Computer Networks

Switching is the method of **transferring data across a network** by selecting a specific path from **source to destination**.  
It decides *how* data should travel inside a network efficiently.

---

## 🔹 Types of Switching Techniques
Switching is mainly classified into:

| Switching Type | Data Transferred As | Path Type | Delay | Example Use |
|----------------|---------------------|-----------|--------|-------------|
| **Circuit Switching** | Continuous signal (bit stream) | Dedicated path | High setup latency, low transmission delay | PSTN (Telephone) |
| **Packet Switching** | Packets (chunks) | Shared path | Variable delay | Internet |
| **Message Switching** | Full message | Store-and-forward (hop-by-hop) | Very high delay | Telegram-like systems |

---

## 🔹 1️⃣ Circuit Switching
A **dedicated physical path** is established before communication begins.

### Stages
1. Circuit Establishment  
2. Data Transfer  
3. Circuit Disconnection  

### Pros
- No congestion once path is established  
- Predictable delay (constant bandwidth)

### Cons
- Wastage of bandwidth if line is idle  
- Connection setup delay  

### Example
Telephone networks (voice calls).

📌 **Analogy:** Reserving a private taxi for the whole journey — nobody else can use it.

---

## 🔹 2️⃣ Packet Switching
Data is broken into **packets**, each containing:

Header + Payload + Trailer
No dedicated path; packets choose the **best available route** dynamically.

### Types
| Type | How Packets Travel | Delay | Reliability |
|------|--------------------|-------|-------------|
| **Datagram** | Each packet takes different route | Variable | Low |
| **Virtual Circuit** | Path reserved before first packet | Moderate | High |

### Pros
- Efficient bandwidth usage  
- High reliability (alternative path exists)

### Cons
- Variable delay & jitter  
- Packets may arrive out of order

### Example
Internet & cloud networks.

📌 **Analogy:** Sending letters through postal service — each may take a different path but reaches the destination.

---

## 🔹 3️⃣ Message Switching (Store-and-Forward)
Data is sent **as an entire message** from one node to the next.  
Each intermediate node **stores the complete message** before forwarding.

### Pros
- No need for dedicated path  
- Efficient for extremely long messages

### Cons
- Very high delay; high memory usage  
- Not suitable for real-time communication

### Example
Early telegraph systems.

📌 **Analogy:** A bus that stops at every terminal and unloads everything before moving ahead.

---

## 🔥 Circuit vs Packet vs Message Switching — Comparison

| Feature | Circuit Switching | Packet Switching | Message Switching |
|--------|--------------------|------------------|-------------------|
| Path | Dedicated | Not dedicated | Not dedicated |
| Data Unit | Bit stream | Packets | Full Message |
| Delay | Low (after setup) | Variable | Very High |
| Storage at Nodes | Not required | Needed for packets | Large storage needed |
| Real-time Support | ✔ | ✔ (with QoS) | ❌ |
| Bandwidth Usage | Inefficient | Efficient | Very inefficient |

---

## 📌 Interview Key Points (Highly Useful for Cloud / Networking Roles)
- Packet switching is the **foundation of the Internet**.
- Cloud (AWS/Azure/GCP) VPC uses **packet switching with virtual circuits (tunnels / routing rules)**.
- Circuit switching is used in **traditional voice networks**; packet switching in **VoIP**.
- Datagram packet switching = **connectionless**, Virtual circuit = **connection-oriented**.
- Real-time apps (Zoom, Teams) require **low latency → packet switching + QoS**.

---

## ⚡ 5-Line Final Revision
Switching decides how data travels from sender to receiver across a network.

Circuit Switching = dedicated path — predictable delay — used in telephony.

Packet Switching = packets share multiple routes — used in the Internet & cloud.

Datagram = no fixed path; Virtual Circuit = fixed logical path.

Message Switching = store & forward of full messages — too slow for real-time.

---
# 🔁 Collision Domain vs 📣 Broadcast Domain

Understanding **collision domain** and **broadcast domain** helps in network design and device selection.

---

## 🔹 Collision Domain
A collision domain is an area of the network **where data packets can collide** if two or more devices transmit at the same time.

### Key Points
- Collisions degrade performance.
- Each device **competes** for the medium.
- Works mainly in **half-duplex** networks.

### Example
- **Hub**: All ports share one collision domain.
- **Switch**: Each port has its own collision domain (removes collisions).

📌 **Analogy:** One person speaking at a time in a small room — if many speak together they collide.

---

## 🔹 Broadcast Domain
A broadcast domain is a network area **where a broadcast packet is received by all devices**.

### Key Points
- Broadcasts consume bandwidth.
- Too many broadcasts → congestion.
- Routers **stop** broadcasts.

### Example
- **Switch**: All ports share one broadcast domain (unless VLAN configured).
- **Router**: Breaks broadcast domains.

📌 **Analogy:** Teacher sending an announcement to the whole class — all must listen.

---

## 🔥 Quick Comparison

| Feature | Collision Domain | Broadcast Domain |
|--------|------------------|------------------|
| What happens | Packet collisions | Broadcast packet propagation |
| Devices affected | Devices on same shared medium | All hosts in same subnet |
| Eliminated by | Switch/Full-duplex | Routers / VLAN |
| Impact | Reduces speed | Consumes network bandwidth |

---

## ⚡ Final 4 Revision Lines
Collision domain — packets crash on shared medium; fixed by switches.

Broadcast domain — broadcast reaches all devices; fixed by routers.

Hub = 1 collision domain, Switch = per port collision domain.

Router = separates broadcast domains; Switch = single broadcast unless VLAN used.

---


