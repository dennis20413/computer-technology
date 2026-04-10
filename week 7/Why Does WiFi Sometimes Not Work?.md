# Unit 4: Why Does WiFi Sometimes Not Work? 
### 🌐 A Data Science Perspective on Network Architecture & Troubleshooting

## 🎯 The Core Problem: "Connected, No Internet"
We have all experienced it: your phone shows full WiFi bars, yet the page won't load. This isn't one random glitch—it's a breakdown in a complex **7-layer communication process**. For a Data Science student, understanding this is the key to building robust data pipelines and low-latency financial systems.

---

## 🧠 The "Postal System" Analogy (OSI 7-Layers)
To understand how data moves, imagine sending a physical letter:


| Layer | Name | Life Example (The Mail) | Technical Function |
| :--- | :--- | :--- | :--- |
| **L7** | **Application** | The actual message written in the letter. | HTTP, DNS, SMTP (What you see). |
| **L6** | **Presentation** | Translating the letter or encrypting it. | Encryption (SSL/TLS), Compression. |
| **L5** | **Session** | Remembering you are talking to the same person. | Authentication & connection state. |
| **L4** | **Transport** | Choosing "Registered Mail" vs "Regular Mail". | TCP (Reliable) vs UDP (Fast). |
| **L3** | **Network** | The Address on the envelope (Street/Zip). | IP Addresses and Routing. |
| **L2** | **Data Link** | The delivery truck moving between two hubs. | MAC Addresses (Hardware ID). |
| **L1** | **Physical** | The actual road, tires, and gasoline. | Cables, Fiber, Radio Waves (WiFi). |

---

## 🧪 Technical Insights & Daily Life Connection

### 1. DNS: The Internet's GPS 📍
**Life Example:** You want to go to "McDonald's," but your GPS only understands Latitude/Longitude coordinates.
**Technical:** You type `github.com`, but the internet only understands `140.82.114.4`. 
* **Connection to Daily Life:** If your DNS fails, you are "connected" to the WiFi road, but your GPS is broken. You can't reach your destination because you don't know the "number" behind the "name."

### 2. TCP vs. UDP: Financial Data Trade-offs 💹
In **Quantitative Finance**, the protocol choice defines the strategy:
* **TCP (Transmission Control Protocol):** Like a **Bank Transfer**. It ensures every bit arrives perfectly. If a packet is lost, it stops and resends.
* **UDP (User Datagram Protocol):** Like a **Live Stock Ticker**. It’s incredibly fast. If you miss one price update, you don't care—you just want the *next* most recent one.
<img width="774" height="582" alt="image" src="https://github.com/user-attachments/assets/c1da5016-5f22-45c5-a0f9-4c3d1a2ba006" />

### 3. NAT & Private IPs: The "Mailroom" 🏢
**Life Example:** A massive office building has one street address (Public IP), but 100 different desks (Private IPs).
**Technical:** Your home router uses **NAT**. Google only sees your "Public IP," and your router acts as a "Mailroom Clerk," forwarding data to the correct device in your house.

---

## 🚀 Lab 20 Extension: The "Full Journey" Analysis
Building on the **Grand Challenge**, we can trace a single request through the entire stack. When I access a Data Science dataset on GitHub:
1. **The Request (L7-L5):** My browser asks for a CSV file (HTTPS).
2. **The Security (L6):** TLS encrypts my login credentials.
3. **The Logistics (L4-L2):** The data is chopped into 1,500-byte **packets**. Each packet is addressed (IP) and framed for my local hardware (MAC).
4. **The Physical (L1):** These packets become light pulses in an undersea fiber-optic cable, traveling from Taiwan to a US server in ~150ms.

---

## 🔧 7-Step Troubleshooting Checklist
When the WiFi fails, we debug from the bottom (Physical) to the top (Application):

1.  **L1 Physical:** Is the cable loose? Is the router overheated?
2.  **L3 Network (Local):** Do I have an IP? (Check `ipconfig`). If it's `169.254...`, the router isn't talking to you.
3.  **L3 Network (Gateway):** Can I "ping" my router? (`ping 192.168.1.1`).
4.  **L3 Network (Internet):** Can I reach the outside world? (`ping 8.8.8.8`).
5.  **L7 DNS:** Can I turn a name into a number? (`nslookup google.com`).
6.  **L4/L7 Service:** Is the website's server down (Error 500)?
7.  **L6/L7 Security:** Is a Firewall or VPN blocking the specific port?

---

## 📊 Lab Execution Gallery
*Below are the consolidated results from the 20 Python simulation labs, demonstrating packet construction, latency mapping, and network evolution.*
<img width="1495" height="480" alt="image" src="https://github.com/user-attachments/assets/90bd0054-8f4c-4ff4-ae26-c558492b7cf6" />
<img width="1493" height="550" alt="image" src="https://github.com/user-attachments/assets/67b677ff-96bf-4916-bf16-c605d48ebd47" />
<img width="1507" height="600" alt="image" src="https://github.com/user-attachments/assets/da9750d3-72c8-4f8e-b31a-3e4ccdca3bf1" />
<img width="1502" height="579" alt="image" src="https://github.com/user-attachments/assets/0f17525b-1560-4c8e-a89a-2867efdf6a45" />
<img width="1503" height="596" alt="image" src="https://github.com/user-attachments/assets/66f2e19d-e9da-45f5-b30c-a1363cadda5c" />
<img width="1506" height="634" alt="image" src="https://github.com/user-attachments/assets/36f48710-1c4b-4789-b786-bc7c0db9c59a" />
<img width="1493" height="543" alt="image" src="https://github.com/user-attachments/assets/d7ca6d54-97a3-4489-84cc-6f5c1ccddf5d" />
<img width="1500" height="588" alt="image" src="https://github.com/user-attachments/assets/d374c644-6eeb-4487-831d-2098bea7b651" />
<img width="1506" height="679" alt="image" src="https://github.com/user-attachments/assets/c62ac1e3-a645-4a8c-a2f2-c7d6aaa6540e" />
<img width="1480" height="807" alt="image" src="https://github.com/user-attachments/assets/c7b7b1ac-cd67-4c9f-b203-87d03d2c1264" />
<img width="1496" height="653" alt="image" src="https://github.com/user-attachments/assets/08d4003c-a29e-4808-b76b-84b4dd1b4998" />
<img width="1502" height="594" alt="image" src="https://github.com/user-attachments/assets/2f64c509-f7c3-49fc-86d7-056782637efc" />
<img width="1499" height="556" alt="image" src="https://github.com/user-attachments/assets/8083b3ad-cd01-4727-aa2e-eeced996627e" />
<img width="1503" height="442" alt="image" src="https://github.com/user-attachments/assets/f798ae2f-43ce-49ae-a05f-d3f37f2f3722" />
<img width="1501" height="703" alt="image" src="https://github.com/user-attachments/assets/9e1ae6a8-5f1e-4c5f-832b-6dc8a09976aa" />
<img width="1503" height="626" alt="image" src="https://github.com/user-attachments/assets/5d07cfbd-b9b2-4920-a4ff-fe4646ce71ca" />
<img width="1503" height="596" alt="image" src="https://github.com/user-attachments/assets/330ad5a6-3926-47a8-ad8d-84a44bcda46c" />
<img width="1497" height="521" alt="image" src="https://github.com/user-attachments/assets/8d894397-4c8f-454d-a6f2-5f89ce4a8788" />
<img width="1501" height="508" alt="image" src="https://github.com/user-attachments/assets/5b9545b3-6e25-457c-bb16-91ce72a3211d" />
<img width="1496" height="707" alt="image" src="https://github.com/user-attachments/assets/54d11fff-db85-4a9e-b321-dc06d6b9b24a" />



---
**Course:** Network Communications & PBL  
**Focus:** Data Science / Quantitative Finance Infrastructure
