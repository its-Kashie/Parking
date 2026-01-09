# 🚗 Smart Parking Allocation & Zone Management System

> **A High-Performance DSA Project for Urban Infrastructure Management**
> This project focuses on designing and implementing an in-memory smart parking system for a city divided into zones.

---

## 🏗️ System Architecture
The system follows a hierarchical spatial distribution to manage parking efficiently.

* **Logic:** C++ (Object-Oriented & custom Data Structures).
* **Storage:** In-memory only (Arrays, Linked Lists, Stacks, Queues).
* **Hierarchical Flow:** `Zone` ⮕ `ParkingArea` ⮕ `ParkingSlot` ⮕ `Vehicle`.
* **Constraint:** **No STL** graph or map containers are allowed for core logic.

---

## 👥 Team Roles & Responsibilities
Both students are responsible for system integration, testing, and documentation.

| 👤 Person A (Logic & DSA) | 👤 Person B (State & UI) |
| :--- | :--- |
| **Core Structure:** Zone, Area, and Slot classes. | **Lifecycle:** State machine implementation. |
| **Allocation Engine:** Same-zone & Cross-zone logic. | **Analytics:** Usage and utilization calculations. |
| **Rollback Manager:** Stack-based undo ($k$ operations). | **UI/Integration:** Interface and input validation. |

---

## 🔄 Parking Request Lifecycle
Each request follows a strict state machine to prevent invalid transitions.



**Allowed Transitions:**
1.  **Standard:** `REQUESTED` ⮕ `ALLOCATED` ⮕ `OCCUPIED` ⮕ `RELEASED`.
2.  **Cancellation:** `REQUESTED` ⮕ `CANCELLED` or `ALLOCATED` ⮕ `CANCELLED`.
3.  **Enforcement:** Invalid transitions (e.g., `RELEASED` ⮕ `CANCELLED`) must be explicitly prevented.

---

## ⚙️ Core Functional Requirements
1. **Zone Management:** City divided into zones; each zone contains multiple parking areas and slots.
2. **Allocation Logic:** Uses "First-available" strategy.Cross-zone allocation is allowed if the requested zone is full but incurs a penalty.
3.  **Rollback System:** Supports undoing the last $k$ allocation operations, restoring slot availability and request states.
4.  **Analytics:** Provides average duration, zone utilization rate, and peak usage zones.

---

## 📂 Project Structure 
```bash
​📂 Smart-Parking-System
├── 📂 src
│   ├── 📂 core
│   │   ├── 📄 Zone.h/cpp — Zone & adjacency definitions
│   │   ├── 📄 ParkingArea.h/cpp — Logic for area clusters
│   │   ├── 📄 ParkingSlot.h/cpp — Slot status (Available/Occupied)
│   │   ├── 📄 Vehicle.h/cpp — Vehicle IDs & preferences
│   │   └── 📄 ParkingRequest.h/cpp — State machine transitions
│   ├── 📂 engine
│   │   ├── 📄 AllocationEngine.h/cpp — Allocation algorithms
│   │   └── 📄 RollbackManager.h/cpp — Stack-based undo (k operations)
│   ├── 📂 system
│   │   └── 📄 ParkingSystem.h/cpp — Main system API
│   └── 📄 main.cpp — Application entry point
├── 📂 ui
│   ├── 📄 index.html / style.css / app.js — Frontend interface
├── 📂 tests
│   ├── 📄 test_cases.cpp — 10 mandatory test scenarios
├── 📂 reports
│   └── 📄 report-day1..7.md — Daily progress logs
├── 📂 docs
│   └── 📄 design.md — Complexity analysis & design strategy
└── 📄 README.md  
```

---

## 💻 Setup Terminal Command
Copy and paste this into your terminal to generate the compliant file structure:

```bash
mkdir -p Smart-Parking-System/{src/{core,engine,system},ui,tests,reports,docs} && \
touch Smart-Parking-System/src/core/{Zone,ParkingArea,ParkingSlot,Vehicle,ParkingRequest}.h \
Smart-Parking-System/src/core/{Zone,ParkingArea,ParkingSlot,Vehicle,ParkingRequest}.cpp \
Smart-Parking-System/src/engine/{AllocationEngine,RollbackManager}.h \
Smart-Parking-System/src/engine/{AllocationEngine,RollbackManager}.cpp \
Smart-Parking-System/src/system/ParkingSystem.h \
Smart-Parking-System/src/system/ParkingSystem.cpp \
Smart-Parking-System/src/main.cpp \
Smart-Parking-System/ui/{index.html,style.css,app.js} \
Smart-Parking-System/tests/test_cases.cpp \
Smart-Parking-System/reports/report-day{1..7}.md \
Smart-Parking-System/docs/{design.md,algorithms.md} \
Smart-Parking-System/{README.md,.gitignore}
