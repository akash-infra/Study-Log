# CControlled Access Protocols (Data Link Layer)
  
In Controlled Access, a station can transmit **only when it is allowed** – preventing random collisions.

There 3 types of controlled access protocols:
- Reservation Method
- Polling Method
- Token Passing Method


---

## 1️⃣ Reservation Method
Stations **reserve** the channel before actual transmission.

### 🔹 Short Explanation
- The time is divided into fixed slots.
- In the beginning of each frame, stations announce transmission requests.
- Slots are assigned → data is transmitted **without collision**.

### 🔹 Important Points
- Works efficiently under **high network load**.
- Provides **fairness**, every station gets a chance.
- Requires a **reservation interval** before each frame.

### 🔹 Advantages
| Benefit | Reason |
|--------|--------|
| Zero collision during transmission | Slots are pre-allocated |
| Fair access | All requesting stations get a slot |
| High efficiency in heavy traffic | Many transmissions already queued |

### 🔹 Drawbacks
| Drawback | Why |
|----------|------|
| Reservation overhead | Slow when few stations are active |
| Complex scheduling | Needs control information & management |

### 🔹 Formula (Approx.)

Throughput η ≈ (Useful transmission time) / (Frame time)
η increases with increasing traffic load


---

## 2️⃣ Polling Method
A **central controller (Primary station)** decides which device may send next.

### 🔹 Short Explanation
- One station is **Primary (controller)** & others are **Secondary**.
- Primary polls stations one-by-one to check who wants to transmit.
- Only the **polled station** transmits.

### 🔹 Important Points
- No simultaneous access → **collision-free**.
- Primary must remain active → system dependent on it.

### 🔹 Advantages
| Benefit | Reason |
|--------|--------|
| No collisions | Only one active transmitter |
| Suitable for priority traffic | Primary can choose polling order |
| Good for low → medium traffic | Avoids idle broadcast |

### 🔹 Drawbacks
| Drawback | Why |
|----------|------|
| Single point of failure | If Primary fails → network stops |
| Polling delay | Wait time increases when stations are many |
| Slower at high traffic | Sequential turn-taking bottleneck |

### 🔹 Formula (Approx.)
Delay ≈ (Polling cycle time) / Number of active stations
Delay increases with more nodes


---

## 3️⃣ Token Passing Method
A **token (special frame)** circulates among stations → only the station holding the token may transmit.

### 🔹 Short Explanation
- Stations are arranged in a **logical ring**.
- A small control frame called a **Token** moves around.
- A station transmits only when it **captures the token**, then forwards it after use.

### 🔹 Important Points
- No central controller.
- Token must be managed carefully (lost, duplicate token must be handled).

### 🔹 Advantages
| Benefit | Reason |
|--------|--------|
| No collisions | Only token holder transmits |
| High fairness | Token visits everyone |
| Performs well under heavy load | Continuous transmission by active stations |

### 🔹 Drawbacks
| Drawback | Why |
|----------|------|
| Token loss / duplication issues | Protocol becomes complicated |
| Delay under light load | Token must circulate even if no one wants to send |
| Performance depends on ring size | Too many nodes → large token rotation time |

### 🔹 Formula (Approx.)
Token Rotation Time (TRT) = Time for token to visit all stations once
Throughput ∝ 1 / TRT
S=Throughput=1/(1+a/N); for a<1
S=t/a(1+1/N); for a>1
a=Tp/Tt; Tp=Propgation Time 
         Tt=Transmisson time
         N=Number of stations
---

---

## 🔥 Comparison of Reservation vs Polling vs Token Passing

| Feature / Method | Reservation | Polling | Token Passing |
|------------------|-------------|---------|---------------|
| Collision occurrence | ❌ None | ❌ None | ❌ None |
| Control | Distributed | Centralized | Distributed |
| Best Traffic Load | Heavy | Low–Medium | Heavy |
| Delay Under Light Load | High | Moderate | High |
| Risk Points | Reservation overhead | Primary failure | Token loss |
| Fairness | High | Medium | Very High |
| Complexity | Medium | Medium | High |

---

## 🧠 Summary — For Exams / Interviews
- **Reservation** → stations reserve slots before transmission → **best for heavy traffic**.
- **Polling** → primary controls who sends → **risk of central failure**.
- **Token Passing** → token authorizes transmission → **fair & collision-free but complex**.

---



    
