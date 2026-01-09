# 🚗 Smart Parking Allocation & Zone Management System

> **A High-Performance DSA Project for Urban Infrastructure Management**

---

## 🏗️ System Architecture
The system follows a hierarchical spatial distribution to manage parking efficiently.

* **Logic:** C++ (Classes & DSA)
* **Storage:** In-memory (Stacks, Queues, Linked Lists)
* **Flow:** `Zone` ⮕ `Area` ⮕ `Slot` ⮕ `Vehicle`

---

## 👥 Team Roles

| 👤 Person A (Logic & DSA) | 👤 Person B (UI & Docs) |
| :--- | :--- |
| Core Backend Development | Frontend / Console Interface |
| Allocation & Rollback Logic | Data Validation & Integration |
| State Machine Management | Daily Reports & Final Manual |

---

## 📅 1-Week Execution Roadmap

* **Day 1:** 🛠️ Project Setup & Design Architecture
* **Day 2:** 🏗️ Base Classes (Zone, Area, Slot)
* **Day 3:** 🔄 Request Lifecycle & State Transitions
* **Day 4:** ⚙️ Allocation Engine (Same-zone vs Cross-zone)
* **Day 5:** ↩️ Rollback Manager (Stack Implementation)
* **Day 6:** 📊 Analytics Dashboard & UI Hookup
* **Day 7:** 🧪 Stress Testing & Final Submission

---

## 📂 Project Structure
```bash
📂 **Smart-Parking-System**
├── 📂 **src**
│   ├── 📂 **core**
│   │   ├── 📄 `Zone.h/cpp` — Zone definitions
│   │   ├── 📄 `ParkingArea.h/cpp` — Local area logic
│   │   ├── 📄 `ParkingSlot.h/cpp` — Slot status & IDs
│   │   ├── 📄 `Vehicle.h/cpp` — Vehicle properties
│   │   └── 📄 `ParkingRequest.h/cpp` — State transitions
│   ├── 📂 **engine**
│   │   ├── 📄 `AllocationEngine.h/cpp` — Search algorithms
│   │   └── 📄 `RollbackManager.h/cpp` — Undo/Redo (Stack)
│   ├── 📂 **system**
│   │   └── 📄 `ParkingSystem.h/cpp` — Main API Wrapper
│   └── 📄 `main.cpp` — Entry point
├── 📂 **ui**
│   ├── 📄 `index.html`
│   ├── 📄 `style.css`
│   └── 📄 `app.js`
├── 📂 **tests**
│   ├── 📄 `test_allocation.cpp`
│   └── 📄 `test_rollback.cpp`
├── 📂 **reports**
│   └── 📄 `report-day1..7.md`
├── 📂 **docs**
│   ├── 📄 `design.md`
│   └── 📄 `algorithms.md`
├── 📄 `README.md`
└── 📄 `.gitignore`

```
---

## 💻 Setup Terminal Command

Copy and paste the command below to generate the entire structure and all empty files at once:

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
Smart-Parking-System/tests/{test_allocation.cpp,test_rollback.cpp,test_states.cpp} \
Smart-Parking-System/reports/report-day{1..7}.md \
Smart-Parking-System/docs/{design.md,algorithms.md} \
Smart-Parking-System/{README.md,.gitignore}
```
