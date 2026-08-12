# DAWs — Digital Audio Workstations

## 1. Table of Contents
- [1. Table of Contents](#1-table-of-contents)
- [2. Checklist](#2-checklist)
- [3. Latency Compensation](#3-latency-compensation)
  - [3.1. With audio but without tranport](#31-with-audio-but-without-tranport)
  - [3.2. Full](#32-full)

---

## 2. Checklist

1. If your plugin introduces latency, in some DAWs the latency will be noticeable in subsequent plugins in the effect chain.

---

## 3. Latency Compensation

Each plugin should report its latency accurately so the DAW can calculate proper latency compensation. DAWs vary in how they handle this:

### 3.1. With audio but without tranport
- **Example:** Ableton<sup>[[1](https://www.reddit.com/r/ableton/comments/10bby0f/psa_3rd_party_plugin_latency_even_when_freezing/)][[2](https://help.ableton.com/hc/en-us/articles/209072409-Delay-Compensation-FAQ)]</sup>
- The DAW compensates for the cumulative latency of all plugins on a track relative to other tracks
- Latency compensation does **not** occur for the transport information, thus subsequent plugins will experience the latency from preceding plugins when relying on transport synchronization

### 3.2. Full
- **Example:** FL Studio
- The DAW performs latency compensation for both audio and transport at the plugin graph level

---

> We're always looking to expand and improve this resource. If you have any insights or additional information, your contributions are welcome!
