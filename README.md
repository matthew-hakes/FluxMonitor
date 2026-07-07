<div align="center">

# Flux Monitor — Free Edition

**A beautiful, lightweight system monitor for Windows — and a zero-friction LAN agent.**

Real-time CPU, GPU, RAM, network, and disk stats in a small always-on-top widget. Free, forever.

[![Platform](https://img.shields.io/badge/platform-Windows%20Server%20%7C%2010%20%7C%2011-0078d4)](#requirements)
[![Install](https://img.shields.io/badge/install-winget-4c8bf5)](#install)
[![Built with Rust](https://img.shields.io/badge/built%20with-Rust%20%2B%20iced-dea584)](https://iced.rs)
[![Price](https://img.shields.io/badge/price-Free-2ea043)](#editions--free--pro)

</div>

---

## What is this?

**Flux Monitor Free** is the no-cost edition of [Flux Monitor](https://apps.microsoft.com/) — a clean, themeable hardware widget that shows exactly what you care about at a glance, with virtually zero overhead. One tiny executable, no .NET runtime, no browser engine.

It does two jobs:

1. **A full local monitor** — all six tiles (CPU / GPU / RAM / Network / Disk / Clock), the complete built-in skin and color library, custom colors and fonts, and CPU temperature.
2. **A LAN reporting agent** — turn on *Broadcast on LAN* (off by default) and a **Flux Monitor Pro** desktop anywhere on your network can discover this machine and watch its stats remotely. Perfect for headless **Windows Server** boxes, home-lab nodes, and gaming rigs.

The Free build is **compile-stripped**: the paid features aren't hidden behind a flag, their code simply isn't in the binary. That keeps it lean, and it's why it scans clean.

---

## Install

### winget (recommended — works on Server, 10, and 11)

```powershell
winget install MatthewHakes.FluxMonitor
```

That's it — winget verifies the download by hash and installs silently. To update later:

```powershell
winget upgrade MatthewHakes.FluxMonitor
```

For unattended / scripted server rollouts:

```powershell
winget install MatthewHakes.FluxMonitor --silent --accept-package-agreements --accept-source-agreements
```

### Direct download

Grab the latest installer from the [**Releases**](https://github.com/matthew-hakes/FluxMonitor/releases/latest) page and run it. The build is unsigned, so SmartScreen shows a one-time prompt — click **More info → Run anyway**. Every release is verified on VirusTotal and Microsoft Defender before it ships; a `.sha256` is published alongside each installer so you can confirm your download:

```powershell
Get-FileHash .\flux-monitor-setup.exe -Algorithm SHA256
```

### Requirements

- Windows Server 2019/2022, Windows 10, or Windows 11 (x64)
- A GPU with Direct3D 12, Vulkan, or DX11 support (virtually all modern PCs and servers)

---

## Remote monitoring, the easy way

No config files, no port juggling, no exposing anything to the internet.

1. Install **Flux Monitor Free** on the machine you want to watch (e.g. a server).
2. In **Tools → Remote**, flip on **Broadcast on LAN**. The agent announces itself over mDNS on your local network only.
3. On your main PC, open **Flux Monitor Pro** — it discovers the broadcasting machine and offers a **one-click add**. Confirm the prompt (it shows the device's name, host, local IP, OS, and hardware so you know it's yours), and the machine appears as a live tab.

The link is authenticated end-to-end (TLS + certificate pinning). Broadcasting is **opt-in** and stays on your LAN.

---

## Editions — Free & Pro

| | **Free** (this repo) | **Pro** (Microsoft Store) |
|---|:---:|:---:|
| All six tiles (CPU/GPU/RAM/Net/Disk/Clock) | ✅ | ✅ |
| Full skin + 100+ color library, custom colors/fonts | ✅ | ✅ |
| CPU temperature | ✅ | ✅ |
| Broadcast on LAN (be monitored by Pro) | ✅ | ✅ |
| **View** other machines remotely | — | ✅ |
| Pop-out device windows | — | ✅ |
| Temperature **Alerts & thresholds** | — | ✅ |
| **Game Mode** overlay | — | ✅ |
| **Theme Store** (downloadable packs) | — | ✅ |
| Price | **Free** | One-time purchase |

**Flux Monitor Pro** is a one-time purchase on the Microsoft Store. Free machines are the agents; a single Pro desktop is the dashboard that watches them all.

---

## Security & privacy

- **No telemetry, ever.** Zero analytics calls. The only outbound traffic is the optional update check and — only if you enable it — LAN-local broadcasting.
- **Local only.** All settings live in `%APPDATA%\Flux`. Nothing is sent anywhere. Remote monitoring never leaves your LAN.
- **Verified clean.** Every release is scanned on VirusTotal and checked against Microsoft Defender before publishing.
- **Hash-verified installs.** winget verifies the package by SHA-256; a `.sha256` is published with every direct download.

---

## Building from source

The Free edition is built from the Flux Monitor engine with its paid features compiled out:

```powershell
cargo build -p flux-widget --release --no-default-features
# -> target\release\flux.exe  (Pro features stripped at compile time)
```

---

## License

© 2026 Matt Hakes. Free to download, install, and use. Redistribution requires prior written permission — see [`LICENSE`](LICENSE).

---

<div align="center">
<sub>Flux Monitor — built with Rust, iced, and an unreasonable number of color palettes.</sub>
</div>
