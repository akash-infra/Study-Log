# 📌 Error Control – Data Link Layer (DLL)

Error control ensures that data received is **accurate, reliable, and free from corruption**.  
It uses **error detection** and **error correction** methods.

---

## 🔹 Why Errors Occur
Errors in bits occur due to:
- Noise
- Signal attenuation
- Crosstalk
- Electromagnetic interference

---

## 🔥 Types of Error-Control Techniques
| Category | Meaning |
|----------|---------|
| **Error Detection** | Detects if an error occurred |
| **Error Correction** | Locates & corrects the bit error |

This topic focuses on **error detection codes**: **VRC, LRC, Checksum, CRC**.

---

## 1️⃣ VRC – **Vertical Redundancy Check (Parity Bit)**
- Adds **1 extra bit (parity bit)** to each data unit.
- Maintains **even** or **odd** number of 1s.

📌 **Example (Even Parity):**

Data: 1010011 → Number of 1s = 4 (even)
Parity bit = 0 → Final transmission: 10100110


✔ **Detects single-bit errors**  
❌ **Fails for burst errors & even number of bit errors**

---

## 2️⃣ LRC – **Longitudinal Redundancy Check**
- Groups data into **rows** and adds **parity for each column**.
- Final row = **LRC word**.

📌 **Example:**

Data rows:
1010101
1100110
1001101

LRC: 0111110 (column-wise parity)


✔ Better than VRC  
❌ Still fails for some burst error patterns

---

## 3️⃣ Checksum (Used in UDP, TCP, IP)
- Breaks data into **k-bit words**, then **adds them using 1’s complement arithmetic**.
- Complement of sum is sent = **Checksum**.

📌 **Example:**

Words: 1001 + 1100 = 1 0101 (carry 1 + 0101 = 0110)
Checksum = 1's complement = 1001


✔ Good for detecting burst errors  
❌ Not suitable for high-accuracy sensitive applications

---

## 4️⃣ CRC – **Cyclic Redundancy Check (Most Powerful)**
CRC treats the data as a **long binary number**, divides it by a **generator polynomial**, and appends the **remainder as CRC bits**.

🧠 **Polynomial Example:**
G(x) = x^3 + x + 1 → Binary = 1011


### 📌 Block Diagram of CRC (Conceptual)
Message bits → [Binary Division using Generator Polynomial] → Remainder → Append → Transmitted Frame


### 📌 CRC Frame Format
| Data bits | CRC bits (r bits) |
where r = degree of generator polynomial


---

### 🔍 CRC Example (Exact & Simple)
Let:
Data = 110101
Generator Polynomial G = 1011 (degree = 3 → append 000)

**Step 1: Append zeros**
110101 000

**Step 2: Binary division using XOR**

1101 ⊕ 1011 = 0110

Bring next bit ↓

0110 ⊕ 1011 = 1101

Bring next bit ↓

1101 ⊕ 1011 = 0110

Bring next bit ↓

0110 ⊕ 1011 = 1101

Bring next bit ↓

1101 ⊕ 1011 = 0110

Bring last bit ↓

0110 ⊕ 1011 = 1101

Final remainder (CRC) = 101

**Step 3: Final transmitted frame**
110101 101

🔑 **At receiver end**
Receiver performs division again →  
If **remainder = 000** → **No error**  
Else → **Error detected**

---

## 🧠 When to Use Which?
| Technique | Good For | Not Good For |
|----------|----------|--------------|
| VRC | Simple single-bit error detection | Burst errors |
| LRC | Detects longer errors than VRC | Complex patterns |
| Checksum | TCP/UDP networking | Extremely noisy channels |
| CRC | High reliability (Ethernet, Wi-Fi, storage) | None (best for detection) |

---

## 📌 Real-World Uses
| Method | Used In |
|--------|---------|
| VRC / Parity | RAM memory checking |
| LRC | Magnetic storage |
| Checksum | TCP/UDP/IP packets |
| **CRC** | **Ethernet, Wi-Fi, Bluetooth, USB, Hard disks, Cloud networking** |

---

## ⭐ Interview Short Notes
- CRC is the **most powerful error detection code**.
- CRC is based on **polynomial division / modulo-2 arithmetic**.
- **Even if 1 bit flips**, CRC detects it with high probability.
- **Burst error detection capability ≈ r bits** (where r = CRC length).

---

## 🔚 Summary
> **Error-control adds redundant bits to detect corrupted data. CRC is the strongest and most widely used in networking & storage.**

---

### 🔥 Practice Question
**Data = 1011001, Generator = 1101**  
🔹 Find CRC bits  
🔹 Write final transmitted frame

*Hint: Append 3 zeros → perform binary division → remainder = CRC*

---
