# 🚗 Smart Parking Allocation & Zone Management System

> **A High-Performance DSA Project for Urban Infrastructure Management**
> [span_0](start_span)This project focuses on designing and implementing an in-memory smart parking system for a city divided into zones[span_0](end_span).

---

## 🏗️ System Architecture
[span_1](start_span)The system follows a hierarchical spatial distribution to manage parking efficiently[span_1](end_span).

* **Logic:** C++ (Object-Oriented & custom Data Structures).
* **[span_2](start_span)Storage:** In-memory only (Arrays, Linked Lists, Stacks, Queues)[span_2](end_span).
* **[span_3](start_span)Hierarchical Flow:** `Zone` ⮕ `ParkingArea` ⮕ `ParkingSlot` ⮕ `Vehicle`[span_3](end_span).
* **[span_4](start_span)Constraint:** **No STL** graph or map containers are allowed for core logic[span_4](end_span).

---

## 👥 Team Roles & Responsibilities
[span_5](start_span)Both students are responsible for system integration, testing, and documentation[span_5](end_span).

| 👤 Person A (Logic & DSA) | 👤 Person B (State & UI) |
| :--- | :--- |
| **[span_6](start_span)Core Structure:** Zone, Area, and Slot classes[span_6](end_span). | **[span_7](start_span)Lifecycle:** State machine implementation[span_7](end_span). |
| **[span_8](start_span)Allocation Engine:** Same-zone & Cross-zone logic[span_8](end_span). | **[span_9](start_span)Analytics:** Usage and utilization calculations[span_9](end_span). |
| **[span_10](start_span)Rollback Manager:** Stack-based undo ($k$ operations)[span_10](end_span). | **[span_11](start_span)UI/Integration:** Interface and input validation[span_11](end_span). |

---

## 🔄 Parking Request Lifecycle
[span_12](start_span)Each request follows a strict state machine to prevent invalid transitions[span_12](end_span).



**Allowed Transitions:**
1.  **[span_13](start_span)Standard:** `REQUESTED` ⮕ `ALLOCATED` ⮕ `OCCUPIED` ⮕ `RELEASED`[span_13](end_span).
2.  **[span_14](start_span)Cancellation:** `REQUESTED` ⮕ `CANCELLED` or `ALLOCATED` ⮕ `CANCELLED`[span_14](end_span).
3.  **[span_15](start_span)Enforcement:** Invalid transitions (e.g., `RELEASED` ⮕ `CANCELLED`) must be explicitly prevented[span_15](end_span).

---

## ⚙️ Core Functional Requirements
1.  **[span_16](start_span)Zone Management:** City divided into zones; each zone contains multiple parking areas and slots[span_16](end_span).
2.  **Allocation Logic:** Uses "First-available" strategy. [span_17](start_span)Cross-zone allocation is allowed if the requested zone is full but incurs a penalty[span_17](end_span).
3.  **[span_18](start_span)Rollback System:** Supports undoing the last $k$ allocation operations, restoring slot availability and request states[span_18](end_span).
4.  **[span_19](start_span)Analytics:** Provides average duration, zone utilization rate, and peak usage zones[span_19](end_span).

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
