# ABYSS 🌊

> *Neural link established. Dive into the deep.*

A browser-based top-down shooter built with PyScript — Python running natively in the browser, no server required. Descend through 5 levels of a sinking shipwreck, fighting off bioluminescent deep-sea horrors, until you face the APEX.

---

## 🎮 Gameplay

You pilot a submersible through the decaying layers of a massive wrecked vessel. Each level is a sealed compartment — clear all enemies to open the airlock gate and descend deeper.

| Level | Location | Threat |
|-------|----------|--------|
| 01 | Superstructure | Scout swarm |
| 02 | Mid-Deck | Faster, denser swarm |
| 03 | Cargo Bay | High-density swarm |
| 04 | Engine Room | Elite swarm |
| 05 | The Abyss | **APEX BOSS** |

Survive all five layers and pilot into the anomaly at the bottom to **ascend**.

---

## 🕹️ Controls

| Key | Action |
|-----|--------|
| `W A S D` | Move submersible |
| `Space` | Fire forward |
| Fullscreen button | Toggle fullscreen |

---

## ⚙️ Tech Stack

- **PyScript** — Python in the browser (no backend, no build step)
- **HTML5 Canvas** — All rendering done via the 2D canvas API
- **Web Audio API** — Procedurally generated sound effects (shoot, hit, heal)
- **CSS animations** — HUD, cinematic bars, critical hull pulse

Zero dependencies beyond a CDN link to PyScript. Open the HTML file and play.

---

## ✨ Features

- **Cinematic boss intro** — Screen letterboxes, HUD hides, camera shakes
- **Procedural audio** — Every sound is synthesized in real-time with oscillators; no audio files
- **Dynamic airlock gate** — Mechanical door opens as you approach, with spinning gear and hazard stripes
- **Hull integrity HUD** — Drops below 30%? The entire frame pulses red
- **Heal drops** — Enemies have a 25% chance to drop a cross-shaped pickup on death
- **Particle system** — Enemy hits burst into color-matched particles
- **Camera shake** — Scales with damage severity
- **Bubble trail** — Your sub leaves a bubble wake as it moves
- **Level-specific backgrounds** — Each deck renders unique wreckage: railings, portholes, pipes, hull ribs

---

## 🚀 Running It

No install, no build tools.

```bash
# Option 1: Just open it
open index.html   # macOS
start index.html  # Windows

# Option 2: Serve locally (avoids any CORS quirks)
python -m http.server 8000
# Then visit http://localhost:8000
```

> **Note:** PyScript requires a network connection on first load to fetch its runtime from the CDN.

---

## 🏗️ Architecture

```
index.html
├── CSS            — HUD, overlays, cinematic bars, animations
├── JS (vanilla)   — Audio context, fullscreen toggle, game bootstrap
└── PyScript       — Entire game engine
    ├── Player     — Physics, input, bubble trail
    ├── Enemy      — AI, boss variant, projectile firing
    ├── Particle   — Hit burst system
    ├── HealDrop   — Floating pickup with sine-wave bob
    ├── loop()     — Main game loop (requestAnimationFrame)
    ├── spawn()    — Level loader + boss cinematic trigger
    └── draw_*     — Airlock gate, Vertex anomaly, background wreckage
```

---

## 🧠 Built With AI

This project was built at a hackathon using AI-assisted development. The game loop, rendering pipeline, enemy AI, and procedural audio were all developed collaboratively with Claude.

---

## 📄 License

MIT — do whatever you want with it.
