# NV-UV
**GPU Undervolt Companion Tool for NVIDIA RTX 40 (Ada Lovelace) and RTX 50 (Blackwell)**

NV-UV simplifies GPU undervolting by working alongside MSI Afterburner. One-click presets, automatic game detection, crash recovery, and a built-in DX12+DXR stress test scanner.

NV-UV is a **companion tool**, not a replacement for Afterburner. For overclocking, OSD, fan control and advanced curve editing, Afterburner remains the tool of choice.

**Platform:** Windows 10/11 (64-bit) only. NV-UV does not run on Linux or macOS.

> **Not to be confused with** [doums/nvuv](https://github.com/doums/nvuv), a separate CLI tool for NVIDIA undervolting on Linux written in Zig. Different platform, different scope, different project.

---

## Download

The latest build is available as a password-protected ZIP under [Releases](https://github.com/christianp403-spec/NV-UV/releases).

---

## Requirements

- **OS:** Windows 10 or 11 (64-bit)
- **GPU:** NVIDIA RTX 5090 / 5080 / 5070 Ti / 5070 / 5060 Ti / 5060 (Blackwell)  
  or NVIDIA RTX 4090 / 4080 / 4070 Ti Super / 4070 Ti / 4070 Super / 4070 / 4060 Ti / 4060 (Ada Lovelace)
- **Dependencies:** MSI Afterburner 4.6.6+ with RivaTuner Statistics Server (RTSS)
- **Driver:** Latest NVIDIA driver recommended

---

## Features

- **Voltage Lock** — one click, GPU runs at an exact voltage/frequency point
- **4 Presets** — Eco, Balanced, Performance, Max (community-validated per GPU)
- **OCS → UV Import** — import AB OC Scanner results, build a chip-specific UV curve
- **Voltage Step Scanner** — DX12+DXR stress engine with FMA math-error detection
- **Game Replay** — automatic frequency step-down on crash, with per-game learning loop
- **UV-Pilot** — detects 632 games, automatically switches to the optimal UV preset
- **Smart Hz** — desktop 60 Hz, gaming native Hz (experimental)
- **Mini View**, **DE/EN localization**, **System Tray**, **4 Skins**

---

## How It Works

NV-UV reads and writes MSI Afterburner profile files to apply voltage/frequency curves. Live telemetry comes via MAHM Shared Memory and NVML. The stress test runs as a separate process so a GPU crash won't take down the UI.

---

## Community & Support

- **PCGH Forum:** [extreme.pcgameshardware.de/forums/nv-uv.3601](https://extreme.pcgameshardware.de/forums/nv-uv.3601/)
- **Documentation:** [christianp403-spec.github.io/nv-uv-docs](https://christianp403-spec.github.io/nv-uv-docs/)

---

## Support the Project

NV-UV is free. If you find it useful, you can support development via [PayPal](https://www.paypal.com/paypalme/christianpapaioannou).

---

## License

NV-UV is closed-source software. See [LICENSE](LICENSE.txt) for terms.

Third-party components and attributions are documented in [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt).

---

**Build 22 · Cantor · Open Alpha**
