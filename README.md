# ⚡ RLX Disk Pulse v1.0
**Ultra-Lightweight Real-Time Disk I/O Telemetry & Kernel Throttler for Windows**

[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011%20%2F%20LTSC-0078D6?style=flat-square&logo=windows)](https://github.com)
[![Language](https://img.shields.io/badge/Language-Native%20Win32%20C%2B%2B-00599C?style=flat-square&logo=c%2B%2B)](https://github.com)
[![Footprint](https://img.shields.io/badge/RAM%20Usage-%3C%204%20MB-2ECC71?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-MIT-E74C3C?style=flat-square)](LICENSE)

Developed under **Riswan-Limaga Experience (RLX)**, **RLX Disk Pulse** is a zero-bloat, single-file native Win32 C++ desktop HUD engineered specifically to eliminate mechanical hard drive (5400RPM / 7200RPM HDD) freezes and I/O bottlenecks on low-end and legacy PCs.

Unlike bloated system monitors packed with installers, Electron frameworks, or nagging ads, RLX Disk Pulse launches in milliseconds, consumes under **4 MB of RAM**, and uses near **0% CPU**.

---

## 🚀 Key Features

* **Instant Cold Start (< 50ms):** Pure Win32 GDI + PDH kernel APIs with static linking—zero external DLLs or .NET dependencies.
* **True Bottleneck Detection:** Monitors **Disk Queue Length** and **Average Response Latency (ms)** alongside real-time **RAM Load (%)** to expose actual drive thrashing.
* **One-Click Kernel I/O Throttling:**
  * **Left-Click** any top disk-consuming process to drop its Windows kernel I/O priority to **Very Low (`IO_PRIORITY_VERY_LOW`)** via `NtSetInformationProcess`—instantly unfreezing your PC without killing the application.
  * **Right-Click** to restore normal I/O priority at any time.
* **Automated Guard Mode (`Guard: ON`):** Automatically detects latency spikes (> 65 ms) and throttles the top runaway I/O hog in real time.
* **System Tray Integration:** Minimize (`_`) to the Windows System Tray with live latency tooltips while Auto-Guard protects your system silently in the background.
* **Zero-Friction Startup Toggle (`Boot: ON/OFF`):** Enable or disable automatic launch at Windows startup with a single click.

---

## 🛠️ Build From Source (MinGW-w64)

1. Compile the Windows version metadata resource:
   ```cmd
   windres rlx.rc -O coff -o rlx.res