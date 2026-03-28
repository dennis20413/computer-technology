# 💻 Unit 02: OS Explorer — Why Do Mac, Windows, and Linux Look Different?

## 📝 Overview: The Hardware Manager
[cite_start]An **Operating System (OS)** is the core engine that manages a computer's CPU and RAM[cite: 6, 7]. [cite_start]While user interfaces differ across platforms, the underlying responsibility remains the same: mediating the relationship between hardware and software[cite: 9].

---

## 🔑 Weekly Glossary (OS Architecture)

| English Term | 繁體中文名詞 | Technical Role |
| :--- | :--- | :--- |
| **Kernel** | 核心 | [cite_start]The OS engine that manages hardware and software[cite: 9]. |
| **Process** | 行程 | [cite_start]A running instance of a program[cite: 9]. |
| **Thread** | 執行緒 | [cite_start]The smallest execution unit within a process[cite: 9]. |
| **Shell** | 殼層 | [cite_start]The interface for human-OS communication[cite: 9]. |
| **Multitasking** | 多工 | [cite_start]Executing multiple programs simultaneously[cite: 9]. |
| **Docker** | 容器 | [cite_start]A lightweight virtualization tool[cite: 9]. |

---

## 🧪 Foundation Labs: OS Fingerprinting & Management (01-05)

### 1. OS Fingerprint Detection
[cite_start]By running the `platform` and `sys` modules, we identified that **Google Colab runs on Linux** (specifically x86_64 architecture)[cite: 18, 32, 34].
* [cite_start]**Insight:** Most global servers run Linux because of its stability and efficiency[cite: 30, 39].

### 2. The Process Manager & Time Slicing
[cite_start]How does a mobile phone with only 8 cores run 30+ apps? [cite: 44]
* [cite_start]**Mechanism:** The OS uses **Time Slicing**, giving each process tiny turns (measured in milliseconds) to execute[cite: 77, 79].
* [cite_start]**Status States:** Processes are categorized as *Running*, *Heavy* (high CPU/RAM), or *Hung* (unresponsive)[cite: 59, 61, 63].



### 3. Thread Race & Process Isolation
* [cite_start]**The Sandbox Rule:** Modern browsers like Chrome run each tab as a **separate process**[cite: 123, 124].
* [cite_start]**Resilience:** If one tab crashes, the others survive because their memory spaces are isolated[cite: 125].

### 4. File Permission Decoder (`chmod`)
[cite_start]Permissions are represented by 3-bit digits: **Read (4), Write (2), and Execute (1)**[cite: 156, 177].
* [cite_start]**Common Codes:** `755` (Owner can do everything, others read/execute) or `644` (Owner read/write, others read)[cite: 166, 167].
* [cite_start]**Security Warning:** `chmod 777` is extremely dangerous on servers as it allows everyone full access[cite: 162, 180].

---

## 🚀 Intermediate & Advanced Labs: Virtualization & Automation (06-20)

### 1. Linux Mastery on Colab
[cite_start]Since Colab is a Linux environment, we can use `subprocess` to run native terminal commands[cite: 231, 234]:
* [cite_start]`whoami`: Identifies the current user[cite: 235].
* [cite_start]`uname -r`: Checks the Kernel version[cite: 235].
* [cite_start]`free -h`: Audits system memory usage[cite: 241].

### 2. Docker Containers vs. Virtual Machines (VM)
* [cite_start]**Virtual Machine:** Simulates a full computer including a "Guest OS" (e.g., Windows inside Linux), leading to high RAM overhead (~2 GB) and large file sizes (~20 GB)[cite: 378, 384, 412].
* [cite_start]**Docker Container:** Lightweight (~200 MB) and fast (boots in ~1 second) because it **shares the host OS kernel**[cite: 400, 406, 409, 416].



### 3. The Process Lifecycle
[cite_start]An OS manages thousands of lifecycles simultaneously through five key stages[cite: 301, 328]:
1. [cite_start]**Created:** Memory allocated[cite: 307].
2. [cite_start]**Ready:** Waiting for CPU[cite: 309].
3. [cite_start]**Running:** CPU executing code[cite: 311].
4. [cite_start]**Waiting:** Waiting for I/O (disk/network)[cite: 312].
5. [cite_start]**Terminated:** Memory freed[cite: 315].

### 4. System Calls & Boot Sequence
* [cite_start]**System Calls:** Apps never touch hardware directly; they must ask the Kernel via calls like `open()`, `read()`, or `write()`[cite: 624, 654, 656].
* [cite_start]**Boot Stages:** Power On → BIOS/UEFI → Boot Loader (GRUB) → Kernel → Init System → Login[cite: 668, 672, 676, 679, 683, 688].

---

## 💡 Student Life Transformation (Reflection)
Applying OS concepts to my Data Science and professional journey:
1. [cite_start]**Environment Security:** Never hardcode API keys or passwords; instead, use **Environment Variables** (`os.environ`) to keep secrets out of the codebase[cite: 426, 448].
2. [cite_start]**Server Management:** Understanding why **SSDs are the #1 upgrade** for old computers—they drastically reduce wait times during the Kernel initialization stage of booting[cite: 704, 706].
3. [cite_start]**Efficiency Trade-offs:** Recognizing the difference between **iOS** (kills background apps to save RAM) and **Android** (keeps apps cached for speed)[cite: 779, 782]. [cite_start]Neither is wrong; they are just different design philosophies[cite: 783].

---

## 🛠️ Tech Stack & Skills
* [cite_start]**Environment:** Linux (via Google Colab)[cite: 38].
* [cite_start]**Automation:** Shell Scripting (`bash`), Cron Jobs for scheduled tasks[cite: 335, 492].
* [cite_start]**Monitoring:** `psutil` for real-time CPU, RAM, and Disk auditing[cite: 792].
