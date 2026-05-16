# 🌆 HeteroLoop Urban Simulation System

<p align="center">

![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)
![Three.js](https://img.shields.io/badge/Three.js-r150-orange?style=flat-square)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?style=flat-square)
![HTML5](https://img.shields.io/badge/HTML5-Canvas-blue?style=flat-square)

<a href="https://miku-cy.github.io/HeteroLoop-Urban-Simulation-System/">
  <img src="https://img.shields.io/badge/Demo-Live%20Demo-ff6b6b?style=for-the-badge" alt="Live Demo"/>
</a>

</p>

> Real-time 3D urban traffic simulation powered by Three.js — Simulating vehicles, e-bikes, and pedestrians with AI-adaptive traffic signals

[中文版](./README_zh.md) | [Live Demo](https://miku-cy.github.io/HeteroLoop-Urban-Simulation-System/) | [Report Issues](https://github.com/Miku-cy/HeteroLoop-Urban-Simulation-System/issues)

---

## ✨ Features

- 🚗 **Vehicle Simulation** — Real-time vehicle spawning, routing, and collision detection with physics-based movement
- 🛵 **E-bike System** — Independent electric scooter traffic flow simulation with lane-changing behavior
- 🚶 **Pedestrian System** — Pedestrian movement with overpass/crosswalk support and pathfinding AI
- 🚦 **Adaptive Traffic Lights** — AI-controlled signal timing based on real-time traffic density analysis
- 🏢 **Building Analytics** — Real-time footfall statistics and heat mapping for each building
- 🌃 **Night City Rendering** — Immersive dark-theme 3D cityscape with dynamic lighting effects
- ⚡ **Performance Dashboard** — Live metrics: throughput, wait times, collision count, and entity tracking
- 🎮 **Interactive Controls** — Mouse/keyboard navigation with real-time parameter adjustment

---

## 🚀 Quick Start

### Option 1: Direct Browser (Recommended)

Just open `index.html` in your browser — no build step or dependencies required!

```bash
# On macOS
open index.html

# On Windows
start index.html

# On Linux
xdg-open index.html
```

### Option 2: Local Development Server

```bash
# Python 3
python3 -m http.server 8080
# Then open http://localhost:8080

# Node.js (if installed)
npx serve .
# Then open http://localhost:3000
```

### Option 3: Online Demo

[Click here to experience the live demo](https://miku-cy.github.io/HeteroLoop-Urban-Simulation-System/) — no installation needed!

---

## 🎮 Controls

| Action | Control | Description |
|--------|---------|-------------|
| Rotate view | Mouse drag | Orbit camera around the city |
| Zoom | Scroll wheel | Zoom in/out of the scene |
| Pan | Right-click drag | Move camera position |
| Toggle adaptive signals | Spacebar | Enable/disable AI traffic control |
| Pause simulation | P key | Freeze all entities |
| Reset view | R key | Return to default camera position |

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                   HETEROloop SIMULATION                  │
│                 异环都市仿真系统                           │
├─────────────────────────────────────────────────────────┤
│                                                          │
│  ┌─────────────────────────────────────────────────┐    │
│  │              THREE.JS 3D ENGINE                  │    │
│  │  ┌─────────────┐  ┌──────────────┐            │    │
│  │  │   SCENE      │  │   CAMERAS     │            │    │
│  │  │  - Buildings │  │  - Perspective│           │    │
│  │  │  - Roads     │  │  - Orthographic│          │    │
│  │  │  - Vehicles  │  │  - Controls   │            │    │
│  │  │  - Lighting  │  └──────────────┘            │    │
│  │  └─────────────┘                                │    │
│  └─────────────────────────────────────────────────┘    │
│                          │                              │
│  ┌───────────────────────┴───────────────────────────┐ │
│  │              ENTITY MANAGEMENT SYSTEM             │ │
│  │  ┌─────────┐  ┌─────────┐  ┌─────────────────┐  │ │
│  │  │VEHICLES │  │ E-BIKES │  │   PEDESTRIANS   │  │ │
│  │  │ - Cars  │  │ - Scooters│ │  - Walkers    │  │ │
│  │  │ - Trucks│  │ - Paths  │  │  - Crosswalks  │  │ │
│  │  │ - Routes│  │ - Behavior│ │  - Overpasses  │  │ │
│  │  └─────────┘  └─────────┘  └─────────────────┘  │ │
│  └───────────────────────────────────────────────────┘ │
│                          │                              │
│  ┌───────────────────────┴───────────────────────────┐ │
│  │              TRAFFIC CONTROL SYSTEM               │ │
│  │  ┌──────────────┐  ┌─────────────────────────┐   │ │
│  │  │TRAFFIC LIGHTS│  │   ADAPTIVE AI ENGINE   │   │ │
│  │  │ - Timers     │  │  - Density analysis    │   │ │
│  │  │ - Phases     │  │  - Timing optimization  │   │ │
│  │  │ - States     │  │  - Learning (future)    │   │ │
│  │  └──────────────┘  └─────────────────────────┘   │ │
│  └───────────────────────────────────────────────────┘ │
│                          │                              │
│  ┌───────────────────────┴───────────────────────────┐ │
│  │              ANALYTICS DASHBOARD                   │ │
│  │  ┌─────────────┐  ┌──────────────┐               │ │
│  │  │ REAL-TIME   │  │   HISTORICAL  │               │ │
│  │  │ - Counts    │  │   - Charts   │               │ │
│  │  │ - Speeds    │  │   - Trends   │               │ │
│  │  │ - Collisions│  │   - Export   │               │ │
│  │  └─────────────┘  └──────────────┘               │ │
│  └───────────────────────────────────────────────────┘ │
│                                                          │
└─────────────────────────────────────────────────────────┘
```

---

## 📊 Dashboard Metrics

| Metric | Chinese | Description | Update Frequency |
|--------|---------|-------------|------------------|
| 车辆通行量 | Vehicles Passed | Total vehicles that passed through | Every 100ms |
| 电瓶车通行 | E-bikes Passed | Total e-bikes in simulation | Every 100ms |
| 总客流量 | Pedestrian Flow | Total pedestrians count | Real-time |
| 车辆等待 | Vehicle Wait Time | Average wait time at signals | Rolling average |
| 碰撞事故 | Collision Count | Total collision incidents | On event |
| 路面车辆 | Road Vehicles | Active vehicles on road | Real-time |
| 路面电瓶车 | Road E-bikes | Active e-bikes count | Real-time |
| 路面行人 | Road Pedestrians | Active pedestrians count | Real-time |

---

## 🎨 Technical Highlights

### 1. Real-Time 3D Rendering
- 60 FPS performance with Three.js WebGL rendering
- Dynamic lighting with day/night cycle simulation
- Instanced mesh rendering for hundreds of entities

### 2. Intelligent Traffic System
- BFS pathfinding algorithm for optimal routing
- Collision detection using bounding box intersection
- Traffic density calculation using spatial partitioning

### 3. Adaptive AI
- Real-time traffic flow analysis
- Dynamic signal timing adjustment
- Learning-based optimization (future enhancement)

### 4. Performance Optimization
- Object pooling to reduce garbage collection
- Level-of-detail (LOD) for distant objects
- RequestAnimationFrame for smooth animations

---

## 📁 Project Structure

```
HeteroLoop-Urban-Simulation-System/
├── index.html              # Main application (single file)
├── README.md              # English documentation
├── README_zh.md           # 中文文档
├── .gitignore             # Git ignore rules
├── CONTRIBUTING.md         # Contribution guidelines
└── CHANGELOG.md           # Version history
```

---

## 🛠 Tech Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| **Three.js** | r150+ | 3D rendering engine |
| **JavaScript** | ES6+ | Core programming language |
| **HTML5 Canvas** | - | HUD overlay and charts |
| **WebGL** | 2.0 | GPU-accelerated graphics |

### No Build Step Required
This project uses **zero build tools** and **zero npm dependencies** (except Three.js CDN). Just open `index.html` and it works!

---

## 📸 Screenshots

### Main Interface
- 3D city view with buildings, roads, and vehicles
- Real-time performance dashboard overlay
- Adaptive traffic signal indicators

### Night Mode
- Dynamic city lighting simulation
- Vehicle headlights and street lamps
- Ambient occlusion effects

---

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines on:
- Development setup
- Code standards
- Pull request process
- Issue reporting

---

## 📜 License

MIT License - feel free to use this project for education, research, or commercial purposes.

---

<p align="center">
  <strong>Built with ⏳ for urban simulation research</strong><br/>
  <sub>Powered by Three.js WebGL</sub>
</p>