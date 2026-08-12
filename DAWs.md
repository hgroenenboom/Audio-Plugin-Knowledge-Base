# DAWs — Digital Audio Workstations

## 1. Table of Contents
- [1. Table of Contents](#1-table-of-contents)
- [2. Checklist](#2-checklist)
- [3. Latency Compensation](#3-latency-compensation)
  - [3.1. Track-Level Compensation](#31-track-level-compensation)
  - [3.2. Plugin Graph Compensation](#32-plugin-graph-compensation)

---

## 2. Checklist

1. If your plugin introduces latency, in some DAWs the latency will be noticeable in subsequent plugins in the effect chain.

---

## 3. Latency Compensation

Each plugin should report its latency accurately so the DAW can calculate proper latency compensation. DAWs vary in how they handle this:

### 3.1. Track-Level Compensation
- **Example:** Ableton
- The DAW compensates for the cumulative latency of all plugins on a track relative to other tracks
- Latency compensation does **not** occur between individual plugins within the same chain, subsequent plugins will experience the latency from preceding plugins

### 3.2. Plugin Graph Compensation
- **Example:** FL Studio
- The DAW performs latency compensation at the plugin graph level

---

> We're always looking to expand and improve this resource. If you have any insights or additional information, your contributions are welcome!
