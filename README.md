<div align="center">

# Flux Monitor — Free Edition

**A beautiful, lightweight system monitor for Windows and macOS — and a zero-friction LAN agent.**

Real-time CPU, GPU, RAM, network, disk, and clock stats in a small desktop widget. Free, forever.

[![Release](https://img.shields.io/badge/release-v1.3.0-5898a0)](../../releases)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS-0078d4)](#requirements)
[![Built with Rust](https://img.shields.io/badge/built%20with-Rust%20%2B%20iced-dea584)](https://iced.rs)
[![Price](https://img.shields.io/badge/price-Free-2ea043)](#free-and-pro)

</div>

---

## What is Flux Monitor Free?

Flux Monitor Free is the complete no-cost local monitor: all six tiles, the full built-in skin and color library, custom colors and fonts, native hardware monitoring, and optional LAN broadcasting. It is one small native app with no .NET runtime and no browser engine.

- **CPU, GPU, RAM, Network, Disk, and Clock** tiles, each individually configurable and drag-to-reorder
- **21 built-in skins**, 100+ color presets, custom palettes, font controls, and saved favorites
- **Vertical or horizontal layouts**, always-on-top, snapping, click-through mode, opacity, and adjustable refresh rate
- **12-hour or 24-hour clock**, with AM/PM automatically removed in 24-hour mode
- **Built-in Help** covering every setting and tool
- **Flux Drop on macOS**, an unobtrusive menu-bar mode for show/hide, Settings, reset position, and Quit
- **Native Apple Silicon sensors** for CPU and integrated-GPU temperature, load, clocks, and unified memory
- **Unified-memory-aware GPU reporting** for integrated GPUs on macOS and Windows
- **Optional LAN broadcast**, so a Flux Monitor Pro computer can monitor this machine

The Free build is compile-stripped: Pro features are not merely hidden behind a switch; their code is excluded from the binary.

---

## Install

### Windows

Download **`flux-setup-free-vX.Y.Z.exe`** from [Releases](../../releases), verify its matching `.sha256`, and run it.

```powershell
Get-FileHash .\flux-setup-free-v1.3.0.exe -Algorithm SHA256
```

The installer is currently unsigned, so Windows may show SmartScreen the first time. Confirm the published hash, then choose **More info → Run anyway**.

The winget package can also be installed with:

```powershell
winget install MatthewHakes.FluxMonitor
```

### macOS

1. Download **`Flux-Monitor-Free-vX.Y.Z-macOS-arm64.dmg`** and its `.sha256` from [Releases](../../releases).
2. Verify the disk image:

   ```bash
   shasum -a 256 ~/Downloads/Flux-Monitor-Free-v1.3.0-macOS-arm64.dmg
   ```

3. Open the disk image and drag **Flux** to **Applications**.
4. If Gatekeeper blocks the first launch, open **System Settings → Privacy & Security**, confirm the published hash, and choose **Open Anyway**.

The Mac app is ad-hoc signed but not Apple-notarized yet. Apple Silicon temperature monitoring is native and requires no driver, helper, administrator access, or extra setup.

### Requirements

- Windows 10 or 11, x64
- macOS 12 or later, Apple Silicon (arm64)
- Windows: a GPU with Direct3D 12, Vulkan, or DX11 support
- macOS: Metal support, included on every Apple Silicon Mac

---

## Menus and settings

Settings use the same organization on Windows and macOS:

- **Appearance** — Colors, Font, and Tiles. Each tile opens its options directly underneath its own row.
- **Behavior** — layout, always-on-top, startup, tray or menu-bar behavior, snapping, click-through, lock/reset position, opacity, and refresh rate.
- **Tools** — Utilities, Remote, Updates, plus clearly marked Pro entries for Alerts and Game Mode.
- **? Help** — a categorized guide to the widget, behavior, tools, updates, platform-specific temperature setup, and keyboard controls.

The **Theme Store**, **Alerts**, **Game Mode**, viewing remote machines, and pop-out remote windows are Pro features. The built-in skins, color library, custom themes, all local tiles, Utilities, Help, updates, and LAN broadcasting remain available in Free.

---

## Remote monitoring

Free can securely report its live stats to a Pro desktop on the same LAN:

1. Open **Settings → Tools → Remote**.
2. Turn on **Broadcast on LAN**.
3. On the Pro computer, discover and add the machine.

Broadcasting is opt-in and stays on the local network. The connection uses TLS, certificate pinning, and handshake-key authentication.

---

## Free and Pro

| Feature | Free | Pro |
|---|:---:|:---:|
| CPU/GPU/RAM/Network/Disk/Clock | ✅ | ✅ |
| Native Mac sensors and Windows GPU monitoring | ✅ | ✅ |
| Built-in skins, colors, custom palettes/fonts | ✅ | ✅ |
| 12/24-hour clock | ✅ | ✅ |
| Flux Drop menu-bar mode | ✅ | ✅ |
| Utilities and built-in Help | ✅ | ✅ |
| Broadcast on LAN | ✅ | ✅ |
| View other machines remotely | — | ✅ |
| Pop-out remote device windows | — | ✅ |
| Alerts and temperature thresholds | — | ✅ |
| Game Mode overlay | — | ✅ |
| Downloadable Theme Store packs | — | ✅ |

---

## Security and privacy

- **No telemetry.** Flux makes no analytics calls.
- **Local settings.** Configuration stays in `%APPDATA%\Flux` on Windows or `~/Library/Application Support/com.Flux.Flux` on macOS.
- **Verified downloads.** A SHA-256 sidecar is published for every installer and disk image.
- **No bundled PawnIO.** On Windows, the optional PawnIO driver for CPU-temperature readout is downloaded only when you request it, from its official source.
- **No Mac helper.** Apple Silicon temperature monitoring runs natively inside Flux.
- **No silent updates.** Choose Off, Manual, or Auto checking; installation always remains your choice.

---

## Uninstall

### Windows

Open **Settings → Apps → Flux → Uninstall**. The uninstaller can also remove settings and the optional CPU-temperature components.

### macOS

Quit Flux from the Flux Drop, then move `Flux.app` from Applications to the Trash. To remove preferences too, delete `~/Library/Application Support/com.Flux.Flux`; remove `~/Library/LaunchAgents/com.matthewhakes.flux.plist` if startup was enabled.

---

## License

© 2026 Matt Hakes. Free to download, install, and use for personal, non-commercial use. Redistribution requires prior written permission. See [`LICENSE`](LICENSE).

---

<div align="center">
<sub>Flux Monitor — built with Rust, iced, and an unreasonable number of color palettes.</sub>
</div>
