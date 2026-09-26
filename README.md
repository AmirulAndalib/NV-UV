# NV-UV
**GPU Undervolt Companion Tool for NVIDIA RTX 30 (Ampere), RTX 40 (Ada Lovelace) and RTX 50 (Blackwell)**

NV-UV simplifies GPU undervolting by working alongside MSI Afterburner. It combines one-click presets, automatic game detection, crash recovery, a built-in DX12+DXR stress-test scanner and optional clock-efficiency control for games.

NV-UV is a **companion tool**, not a replacement for Afterburner. For overclocking, OSD, fan control and advanced curve editing, Afterburner remains the tool of choice.

**Platform:** Windows 10/11 (64-bit) only. NV-UV does not run on Linux or macOS.

> **New in v0.99.5:** Dynamic Clock Clapping (DCC), NVIDIA Auto-UV, NVIDIA Power Efficiency Mode, verified manual updates with rollback, optional private diagnostic reports and numerous setup, telemetry and recovery fixes.

## NV-UV v0.99.6.0

This update reworks Hotspot and VRAM monitoring with independent PawnIO readings, guided migration and optional Afterburner/RTSS Hotspot support.

- Sensor migration preserves UV profiles and respects disabled displays. Missing optional sensor readings do not block UV features.
- PawnIO is downloaded and installed when you apply enabled sensor options if it is missing. Internet access and Windows administrator approval are required.
- The VRAM Hotspot display shows the highest individual temperature, with the sensor list available on click.
- Improved Voltage Step Scanner monitoring and reporting of interrupted readings, single-instance handling and restoration from the system tray.
- Improved DCC game detection for restricted game processes, including The Division 2, and cleanup after failed in-place file replacements.
- The bundled Game Database **2.28** contains **699 entries**, including **CODE VEIN II** and **Valheim**.

Thanks for your feedback, bug reports and diagnostic data!

[Release notes and download](https://github.com/christianp403-spec/NV-UV/releases/tag/v0.99.6.0)

> **Not to be confused with** [doums/nvuv](https://github.com/doums/nvuv), a separate CLI tool for NVIDIA undervolting on Linux written in Zig. Different platform, different scope, different project.

---

## Download
The latest build is available as a ZIP under [Releases](https://github.com/christianp403-spec/NV-UV/releases).

---

## Requirements
- **OS:** Windows 10 22H2 (fully updated) or Windows 11, 64-bit
- **GPU:** NVIDIA RTX 5090 / 5080 / 5070 Ti / 5070 / 5060 Ti / 5060 (Blackwell)  
  or NVIDIA RTX 4090 / 4080 / 4070 Ti Super / 4070 Ti / 4070 Super / 4070 / 4060 Ti / 4060 (Ada Lovelace)  
  or NVIDIA RTX 3090 Ti / 3090 / 3080 Ti / 3080 / 3070 Ti / 3070 / 3060 Ti / 3060 (Ampere, new in v0.97, verified on RTX 3090 only, other models experimental)
- **Mobile / Laptop GPUs:** Not directly supported and not tested by me. The scanner may run, but there is no guarantee it works on mobile chips. You are welcome to try it at your own risk, but expect issues. Notebook support is on the ToDo.
- **Dependencies:** MSI Afterburner 4.6.6+ with RivaTuner Statistics Server (RTSS)
- **Driver:** Latest NVIDIA driver recommended

---

## Features
- **Voltage Lock**: one click, GPU runs at an exact voltage/frequency point
- **4 Presets**: Eco, Balanced, Performance, Max (community-validated per GPU)
- **OCS → UV Import**: import AB OC Scanner results, build a chip-specific UV curve
- **Voltage Step Scanner**: DX12+DXR stress engine with FMA math-error detection
- **Game Replay**: automatic frequency step-down on crash, with per-game learning loop
- **DCC: Dynamic Clock Clapping**: learns efficient clock caps for recognized games and remembers them per game and GPU
- **NVIDIA Power Efficiency Mode**: optional experimental global NVIDIA efficiency mode
- **NVIDIA Auto-UV**: previews an individual starting point and applies it only after confirmation
- **UV-Pilot**: recognizes 699 games, automatically switches to the selected UV preset
- **Smart Hz**: desktop 60 Hz, gaming native Hz (experimental)
- **Verified Updates**: manual installation, signed packages and rollback if installation fails
- **Local Diagnostics**: creates a local ZIP first; optional private sending only after review and consent
- **Mini View**, **DE/EN/RU/ES localization**, **System Tray**, **5 Skins**

---

## How It Works
NV-UV reads and writes MSI Afterburner profile files to apply voltage/frequency curves. Its central GPU-control path coordinates UV profiles and DCC so they do not write competing settings. Live telemetry is collected centrally from the available providers. The stress test runs as a separate process so a GPU crash will not take down the UI.

---

## Sensor monitoring

GPU Hotspot and individual VRAM temperatures are read through [PawnIO](https://github.com/namazso/PawnIO), independently of Afterburner's Hotspot source. Readings depend on your GPU and available sensors. Afterburner remains required for NV-UV's profile control and other monitoring functions.

The sensor dialog guides you through migration. Existing UV profiles are preserved. If PawnIO is missing, NV-UV downloads its official installer when you apply enabled sensor options; confirm the Windows administrator prompt. The PawnIO system driver is installed separately and is not bundled in the portable ZIP. Missing optional readings do not lock UV features. You can also keep or set up the optional Afterburner/RTSS Hotspot source and choose its OSD display in Afterburner.

## Troubleshooting
**NV-UV closes immediately on launch, no window, no log.** This is almost always an outdated Windows build that is missing required OS components (WinRT / COM API-set contracts). In the Windows Event Viewer it shows up as an APPCRASH with exception code 0xc0000602 in KERNELBASE.dll. Install all pending Windows updates (Windows 10 needs 22H2 fully patched) and NV-UV will start normally. The crash happens in the Windows loader before any of NV-UV's own code runs, which is why no log is written.

---

## Credits

Thank you to the projects and developers whose work supports NV-UV and NV-UV Play:

- **[Green Curve](https://github.com/aufkrawall/green-curve) by [aufkrawall](https://github.com/aufkrawall)** (MIT License), for the NVAPI V/F-curve access approach used by NV-UV's native bridge.
- **[PawnIO](https://github.com/namazso/PawnIO) by namazso and the PawnIO.Modules contributors**, for the hardware access used by NV-UV's Hotspot and VRAM readings.
- **[LibreHardwareMonitor](https://github.com/LibreHardwareMonitor/LibreHardwareMonitor) and its contributors**, for CPU temperature monitoring in the standalone NV-UV Play application.

Special thanks to Unwinder for his longstanding work on MSI Afterburner and GPU tuning tools. Required third-party notices are included with the portable release.

---

## Community & Support
- **PCGH Forum:** [extreme.pcgameshardware.de/forums/nv-uv.3601](https://extreme.pcgameshardware.de/forums/nv-uv.3601/)
- **GitHub:** report bugs or ask questions via [Issues](https://github.com/christianp403-spec/NV-UV/issues)
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
