# NodeRed-HMI-Simumatik-Bottle-Conveyor

## 📖 Project Overview
This project demonstrates **integration of Node-RED HMI with a Simumatik PLC bottle conveyor simulation** using **OPC UA**. A simple dashboard allows users to **start, stop, and reset** the conveyor simulation. The process stops automatically after **28 cans have been counted**.

Since Simumatik is local simulation only, the repository includes a **YouTube video demo**, the **CODESYS PLC program**, and the **Node-RED JSON flow**.

**YouTube Demo:** [Watch here](https://youtu.be/yAT6tvawFW4)

---

## 🛠️ Project Components

1. **CODESYS PLC Program**
   - Implements bottle counting logic.
   - Stops conveyor automatically at 28 bottles.
   - Provides input/output variables accessible via OPC UA.

2. **Node-RED Dashboard (JSON Flow)**
   - Start, Stop, and Reset buttons.
   - Real-time counter display.
   - Connects to CODESYS PLC via **OPC UA Client** node.
   - Uses function nodes to simulate button presses (sets bits in the PLC GVL).

3. **Simulation Environment**
   - **Simumatik** (local simulation only).
   - Integrates the Node-RED HMI for control.
   - Demonstrates automation control for the bottle conveyor.

---

## 📁 Repository Structure

```
NodeRed-HMI-Simumatik-Bottle-Conveyor/
│
├── CODESYS/
│   └── BottleConveyorProject.project   # Your CODESYS PLC project file
│
├── NodeRED/
│   └── NodeREDFlow.json                # Exported Node-RED flow
│
├── Videos/
│   └── Simumatik_Demo.mp4             # Optional local video copy
│
└── README.md                           # This file
```

---

## ⚙️ Node-RED Dashboard Features

| Feature         | Description |
|-----------------|-------------|
| **Start Button** | Sends bit 0 to PLC to start conveyor. |
| **Stop Button**  | Sends bit 1 to PLC to stop conveyor. |
| **Reset Button** | Sends bit 5 to PLC to reset counter. |
| **Counter Display** | Shows current bottle count from PLC CTU counter. |

---

## 🔗 How to Run

1. **Open CODESYS PLC project** in your CODESYS Control Win runtime.
2. **Run the Simumatik simulation** for the bottle conveyor.
3. **Import the Node-RED JSON flow**:
   - Open Node-RED → Menu → Import → Clipboard → Paste JSON → Deploy.
4. **Configure OPC UA Endpoint** in Node-RED to match your CODESYS runtime:
   - `opc.tcp://localhost:4840` (or change to your setup).
5. **Use the dashboard** to Start, Stop, and Reset the conveyor while monitoring the counter.

---

## 📌 Notes

- This setup **only works locally** due to Simumatik simulation constraints.
- Node-RED dashboard was created using:
  - `node-red-dashboard v3.6.6`
  - `node-red-contrib-opcua v0.2.340`
- Counter stops the process at 28 bottles automatically.

---

## 🎬 YouTube Demo
Watch the full simulation and dashboard in action:  
[![Simumatik Bottle Conveyor Demo](https://img.youtube.com/vi/yAT6tvawFW4/0.jpg)](https://youtu.be/yAT6tvawFW4)

