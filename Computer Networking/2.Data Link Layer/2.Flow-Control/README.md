# 📌 Flow Control – Data Link Layer (DLL)

Flow control ensures that the **sender does not overwhelm the receiver** with more data than it can process and store. It regulates the transmission rate so frames are delivered smoothly without buffer overflow.

---

## 🔹 Quick Definitions
- **Flow Control:** Mechanism to match sender speed to receiver capacity.
- **ARQ (Automatic Repeat reQuest):** Family of protocols combining retransmissions with flow control (used in noisy channels).
- **Sliding Window:** Technique that allows multiple outstanding (unacknowledged) frames in transmission.

---

## 🔥 Techniques of Flow Control

### A. Noiseless Channel
> Channel assumed free of transmission errors. *Theoretical* models.

#### 1. Simplest Protocol
- No restriction on sender transmission.
- Receiver may overflow if slower.
- Used only for conceptual understanding.

#### 2. Stop-and-Wait (Noiseless)
- Sender transmits **one frame at a time** and waits for an **ACK**.
- Guarantees ordering and prevents overflow.
- **Drawback:** Low efficiency because link remains idle while waiting for ACK.

---

### B. Noisy Channel (ARQ Techniques)
> Channel may corrupt or lose frames.

#### 1. Stop-and-Wait ARQ
- Sender sends a frame → waits for ACK.
- If ACK not received (timeout) or NACK received → retransmit.
- Ensures reliable and ordered delivery.
- Simple but inefficient on long-delay or high-speed links.

#### 2. Go-Back-N ARQ (GBN)
- Sender transmits multiple frames before receiving ACKs (window size: N).
- Receiver accepts **in-order** frames only.
- If a frame is lost/corrupted, receiver discards subsequent frames and keeps acknowledging the last correctly received frame.
- On timeout of missing frame → sender **retransmits that frame and all subsequent frames**.
- **Advantage:** Simple receiver.
- **Drawback:** Unnecessary retransmissions reduce efficiency.

**Diagram (GBN behavior example):**

Frame Lost → Receiver discards later frames
|
v
Sender retransmits: Lost frame + all after it

#### 3. Selective Repeat ARQ (SR) — Sliding Window
- Sender transmits multiple frames (window size N).
- Receiver may **accept out-of-order frames** and store them in buffer.
- Lost/corrupted frames are individually retransmitted (not entire window).
- Highest efficiency among ARQ techniques.

**Diagram (SR behavior example):**

Lost Frame → Only that frame retransmitted

Other correctly received frames stay buffered

---

## 🧠 Comparison Summary

| Feature | Stop & Wait ARQ | Go-Back-N ARQ | Selective Repeat ARQ |
|--------|------------------|---------------|-----------------------|
| Multiple frames allowed | ❌ | ✔ | ✔ |
| Receiver buffers out-of-order frames | ❌ | ❌ | ✔ |
| On frame loss | Retransmit same frame | Retransmit lost + later frames | Retransmit only lost frame |
| Complexity | Low | Medium | High |
| Efficiency | Low | Medium | High |

---

## ⚙️ Important Practical Facts (Memory Notes)
- All ARQ methods rely on:
  - **Timeout for missing frames**
  - **ACKs (or NACKs)**
- **GBN wastes bandwidth** due to repeated retransmission of already received frames.
- **SR needs large buffer** because out-of-order frames are held temporarily.
- **Stop & Wait is rarely used in real systems** because of poor throughput, but it teaches fundamentals.

---

## 🔎 Simple Text Diagrams

### Stop-and-Wait

S: ----Frame0----> (wait) <----ACK0----

----Frame1----> (wait) <----ACK1----

### Go-Back-N
0 1 [2 lost] 3 4 5 ...

Receiver discards 3,4,5...

Sender retransmits: 2,3,4,5...


### Selective Repeat
0 1 2 [3 lost] 4 5 ...

Receiver stores 4,5

Sender retransmits only 3

Receiver delivers 3,4,5 in order

---

## 💬 Typical Theory Questions (Exam & Interview)
- Define Flow Control.
- Explain Stop-and-Wait protocol.
- Differences between Go-Back-N and Selective Repeat.
- Why does GBN retransmit multiple frames when only one is lost?
- Why does SR require more memory at the receiver?
- What is Sliding Window? How does it improve throughput?

---

## ☁️ Cloud / DevOps Relevance
This topic helps in understanding:
- **TCP sliding window mechanism**, used in all cloud networking.
- **Throughput tuning** for long-distance cloud replication.
- **Diagnosing high latency & retransmission patterns** in logs.
- **Network performance optimization** across hybrid cloud or VPN connections.

---

## 📝 Revision Notes (Short & Sharp)
- Stop & Wait → 1 frame at a time → Simple but slow.
- Go Back N → Multiple frames → Discard out-of-order → Retransmit window.
- Selective Repeat → Multiple frames → Accept out-of-order → Retransmit only missing.
- Sliding window = backbone of modern reliable transport (TCP).

---

### 👍 Best Way to Remember
Stop & Wait = Wait every time

GBN = If 1 mistake → start again

SR = If 1 mistake → correct only that

