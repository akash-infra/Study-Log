# 📘 Data Link Layer – Notes

## 🔹 1. Introduction
The Data Link Layer is the **2nd layer of the OSI model**.  
Its main job is to ensure **reliable transfer of data** across a physical link between two directly connected nodes.

**Services provided:**
- Framing
- Flow control
- Error control
- Physical addressing
- Access control (in shared networks)

---

## 🔹 2. Responsibilities of Data Link Layer
| Function | Explanation |
|---------|-------------|
| Framing | Divides bit stream into manageable units called frames |
| Error Control | Detects & corrects errors using ARQ + CRC |
| Flow Control | Prevents fast sender from overwhelming slow receiver |
| Addressing | Uses MAC addresses to identify devices |
| Media Access Control | Controls who can use the communication channel |

---

## 🔹 3. Sublayers of Data Link Layer (IEEE 802)
| Sublayer | Purpose |
|---------|---------|
| LLC (Logical Link Control) | Error & flow control |
| MAC (Media Access Control) | Access to shared medium + physical addressing |

---

## 🔹 4. Framing
A **frame** is a structured packet of data.

**Header** → addressing + control info  
**Trailer** → error check (CRC)

---

## 🔹 5. Flow Control Protocols
Flow control ensures sender does not exceed receiver capacity.

| Protocol | Type | Efficiency | Notes |
|----------|------|------------|------|
| Stop and Wait ARQ | Basic | Low | 1 frame at a time |
| Go Back N ARQ | Sliding Window | High | Retransmit from lost frame |
| Selective Repeat ARQ | Sliding Window | Very High | Retransmit only lost frame |

---

## 🔹 6. Error Control
### 📌 Error Detection
- Parity bit
- Checksum
- CRC (most widely used)

### 📌 Error Correction Method
- ARQ (Automatic Repeat Request)

---

## 🔹 7. Automatic Repeat Request (ARQ) Protocols
### 🔸 7.1 Stop and Wait ARQ
- Send one frame → wait for ACK
- Simple but inefficient

### 🔸 7.2 Go Back N ARQ (GBN)
- Sender transmits **multiple frames (window size N)** without waiting for ACK
- If an error occurs → **retransmit from missing frame onwards**

### 🔸 7.3 Selective Repeat ARQ (SR)
- Retransmits **only the damaged/missing frame**
- Requires more buffer & management

---

## 🔹 8. Sliding Window – Key Points
| Term | Meaning |
|------|---------|
| Sender Window | Range of frames allowed to be sent |
| Receiver Window | Range of frames allowed to be received |
| Sequence Number | Identifies frame order |
| ACK | Positive acknowledgement |
| NAK | Negative acknowledgement |

---

## 🔹 9. MAC Protocols (for sharing medium)
| Category | Protocols |
|----------|-----------|
| Random Access | ALOHA, Slotted ALOHA, CSMA/CD, CSMA/CA |
| Controlled Access | Reservation, Polling, Token Passing |
| Channelization | FDMA, TDMA, CDMA |

---

## 🔹 10. Devices used in Data Link Layer
| Device | Purpose |
|--------|---------|
| Switch | Filtering & forwarding frames using MAC address |
| Bridge | Connects multiple LANs |
| NIC | Network Interface Card for physical link |

---

## 📌 Summary
- DLL sits between Physical and Network layers.
- Focus on **framing, flow control, error control & MAC**.
- Most important exam topics:
  ✔ Go Back N ARQ  
  ✔ Selective Repeat ARQ  
  ✔ Sliding window numericals  
  ✔ CRC  

---

## 📚 Handwritten Notes / Practice Work


**General Frame Structure**

