# 🌐 Introduction to Computer Networks (CN)

Computer Networks enable communication and resource sharing between devices such as computers, servers, mobile phones, and IoT devices.

---

## 📌 What is a Computer Network?
A **Computer Network** is a collection of interconnected devices (nodes) that communicate and share resources using communication links.

🔹 Easy recall analogy → **A network is like a transportation system**:  
Devices = cities,  
Communication links = roads,  
Data = vehicles traveling between cities.

---

## 🌟 Why Do We Use Networks? (Characteristics)
| Characteristic | Meaning | Quick Example |
|---------------|---------|---------------|
| Sharing Resources | Share files, printers, storage | Printer shared among office PCs |
| Communication | Exchange messages/data | Email, WhatsApp, VoIP |
| Scalability | Network can grow easily | Add new computers to office network |
| Reliability | Backup paths if one fails | Automatic failover in cloud |
| Performance | Faster data processing via sharing load | Distributed processing |
| Cost Efficiency | Shared resources → lower cost | Shared cloud storage instead of buying disks |

---

## 🔥 Types of Computer Networks (Very Short & Recallable)

| Type | Coverage | Analogy / Example |
|------|----------|-------------------|
| PAN | Few meters | Personal hotspot between phone & laptop |
| LAN | Within a building/campus | Wi-Fi in home/college/office |
| MAN | City-wide | City broadband / institutional network |
| WAN | Country/continent | Internet, AWS global VPC peering |

**Shortcut to remember** → **P-L-M-W** =  
**Personal → Local → Metropolitan → Worldwide**

---

## 🔁 Data Flow Directions
| Mode | Meaning | Example |
|------|---------|---------|
| Simplex | One-way only | TV broadcast |
| Half Duplex | Two-way but not at same time | Walkie-talkie |
| Full Duplex | Two-way simultaneously | Phone call / Zoom call |

---

## 🎯 Message Delivery Options
| Mode | Receiver Type | Example |
|------|---------------|---------|
| Unicasting | One-to-one | Email to single user |
| Multicasting | One-to-group | Webinar / IPTV |
| Broadcasting | One-to-all | ARP request in LAN |

---

## 🤝 Network Models
### 🔹 Peer-to-Peer (P2P)
- All nodes have equal authority; share resources directly.
- Example: Torrent/file sharing between two PCs.

### 🔹 Client–Server
- Clients request services; server provides them.
- Example: Gmail, AWS EC2 hosting website accessed by clients.

---

## 🧱 Components of CN
| Component | Description |
|-----------|-------------|
| Nodes | Devices that send/receive data — PC, router, server |
| Transmission Media | Wired (Ethernet/fiber) or wireless (Wi-Fi/radio) |
| Network Services | Authentication, DNS, File sharing, Email |
| Protocols | Rules for communication — TCP, UDP, HTTP, FTP |
| Topology | Arrangement of nodes — Bus, Star, Ring, Mesh |

---

## 🔺 Network Topologies (1-line Revision)
| Topology | Key Point |
|----------|-----------|
| Bus | Single common backbone cable — cheap but collision-prone |
| Star | All nodes to central switch — reliable & modern |
| Ring | Circular connection — failure affects whole loop |
| Mesh | Every node connected — super reliable but costly |
| Hybrid | Mix of multiple topologies — used in enterprises |

---

## ⚙️ Common Protocol Groups
| Layer | Protocols Examples |
|-------|--------------------|
| Application | HTTP, DNS, SMTP, FTP |
| Transport | TCP, UDP |
| Network | IP, ICMP |
| Data Link | Ethernet, PPP, Wi-Fi (802.11) |

---

## 🧠 Cloud / DevOps Relevance
Understanding CN helps in:
- VPC, Subnets, Security Groups (AWS/Azure)
- Load balancers and web servers (Client–server communication)
- VPN, Direct Connect, Peering (WAN concepts)
- Monitoring latency, packet loss, throughput
- TCP vs UDP decisions in app deployment

---

## 🔥 Quick Interview / Viva Questions (Highly Asked)
- Define computer network.
- What are advantages of networking?
- Difference between LAN / MAN / WAN.
- Define simplex, half duplex, full duplex.
- Difference between unicast, multicast, broadcast.
- What is Client-Server model vs Peer-to-Peer?
- What is network topology? Which one is most used today?
- Name components of a network.
- Why is network knowledge important in cloud computing?

---

## 📝 Final Revision (Memory Map)

CN = Connected devices sharing resources

Types = PAN → LAN → MAN → WAN

Data flow = Simplex / Half Duplex / Full Duplex

Delivery = Unicast / Multicast / Broadcast

Models = P2P / Client–Server

Components = Nodes + Media + Services + Protocols + Topology
