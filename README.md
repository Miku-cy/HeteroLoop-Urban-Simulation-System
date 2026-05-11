# 🌆 HeteroLoop Urban Simulation System | 异环都市仿真系统

A real-time 3D urban traffic simulation system built with Three.js, featuring vehicle, e-bike, and pedestrian simulation with adaptive traffic signals.

基于 Three.js 的实时 3D 城市交通仿真系统，支持车辆、电瓶车、行人模拟与自适应信号灯控制。

## ✨ Features | 功能特性

- 🚗 **Vehicle Simulation** — Real-time vehicle spawning, routing, and collision detection
- 🛵 **E-bike System** — Independent electric scooter traffic flow simulation
- 🚶 **Pedestrian System** — Pedestrian movement with overpass/crosswalk support
- 🚦 **Adaptive Traffic Lights** — AI-controlled signal timing based on traffic density
- 🏢 **Building Analytics** — Real-time footfall statistics for each building
- 🌃 **Night City Rendering** — Immersive dark-theme 3D cityscape
- ⚡ **Performance Dashboard** — Live metrics: throughput, wait times, collision count

## 🚀 Quick Start | 快速开始

Just open `index.html` in your browser — no build step required!

直接在浏览器中打开 `index.html` 即可运行，无需任何构建步骤。

```bash
# Or serve locally | 或者本地启动服务
python3 -m http.server 8080
# Then open http://localhost:8080
```

## 🎮 Controls | 操作说明

| Action | Control |
|--------|---------|
| Rotate view | Mouse drag / 拖拽旋转 |
| Zoom | Scroll wheel / 滚轮缩放 |
| Toggle adaptive signals | Spacebar / 空格键 |

## 🛠 Tech Stack | 技术栈

- **Three.js** — 3D rendering engine
- **Vanilla JavaScript** — Zero dependencies (except Three.js CDN)
- **HTML5 Canvas** — Real-time HUD overlay

## 📊 Dashboard Metrics | 面板指标

| Metric | Description |
|--------|-------------|
| 车辆通行量 | Total vehicles passed |
| 电瓶车通行 | Total e-bikes passed |
| 总客流量 | Total pedestrian flow |
| 车辆等待 | Average vehicle wait time |
| 碰撞事故 | Collision incidents |
| 路面车辆/电瓶车/行人 | Active entities on road |

## 📜 License | 许可证

MIT License
