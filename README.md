# 🌆 HeteroLoop Urban Simulation System

> Real-time 3D urban traffic simulation built with Three.js

[中文版](./README_zh.md)

## ✨ Features

- 🚗 **Vehicle Simulation** — Real-time vehicle spawning, routing, and collision detection
- 🛵 **E-bike System** — Independent electric scooter traffic flow simulation
- 🚶 **Pedestrian System** — Pedestrian movement with overpass/crosswalk support
- 🚦 **Adaptive Traffic Lights** — AI-controlled signal timing based on traffic density
- 🏢 **Building Analytics** — Real-time footfall statistics for each building
- 🌃 **Night City Rendering** — Immersive dark-theme 3D cityscape
- ⚡ **Performance Dashboard** — Live metrics: throughput, wait times, collision count

## 🚀 Quick Start

Just open `index.html` in your browser — no build step required!

```bash
# Or serve locally
python3 -m http.server 8080
# Then open http://localhost:8080
```

## 🎮 Controls

| Action | Control |
|--------|---------|
| Rotate view | Mouse drag |
| Zoom | Scroll wheel |
| Toggle adaptive signals | Spacebar |

## 🛠 Tech Stack

- **Three.js** — 3D rendering engine
- **Vanilla JavaScript** — Zero dependencies (except Three.js CDN)
- **HTML5 Canvas** — Real-time HUD overlay

## 📊 Dashboard Metrics

| Metric | Description |
|--------|-------------|
| 车辆通行量 | Total vehicles passed |
| 电瓶车通行 | Total e-bikes passed |
| 总客流量 | Total pedestrian flow |
| 车辆等待 | Average vehicle wait time |
| 碰撞事故 | Collision incidents |
| 路面车辆/电瓶车/行人 | Active entities on road |

## 📸 Preview

> Open the [live demo](https://miku-cy.github.io/HeteroLoop-Urban-Simulation-System/) to see it in action.

## 📜 License

MIT License
