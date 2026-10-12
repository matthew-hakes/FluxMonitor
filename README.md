# Flux Monitor

Desktop system-monitor widgets for CPU, GPU, RAM, network, disk, and clock information.
This repository provides downloads and documentation. Application source is private.

[![Release](https://img.shields.io/badge/release-v1.3.0-5898a0)](https://github.com/matthew-hakes/FluxMonitor/releases)

## Release status

The latest published download is **v1.3.0**. Refer to its
[release notes](https://github.com/matthew-hakes/FluxMonitor/releases/tag/v1.3.0)
for that version's features and installation information.

A new Windows candidate is under audit. The planned edition model below applies
to that candidate, not to the existing v1.3.0 downloads. **The Microsoft Store
beta and its Pro upgrade are not available yet.**

The published macOS release remains available. The Windows audit does not qualify
new macOS changes or change that release's feature set.

<a id="free-and-pro"></a>

## Editions

### Planned Windows editions — not released yet

The next Windows release has two feature tiers: Free and Pro. Standalone Free
and Store Free share the same Free monitoring features. Installation, update
delivery, and Store purchase options differ.

| Feature | Standalone Free | Store Free | Store Pro |
| --- | --- | --- | --- |
| Local CPU, GPU, RAM, Network, Disk, and Clock tiles | Included | Included | Included |
| Light and Dark colors | Included | Included | Included |
| Fonts, skins, layout, and opacity controls | Included | Included | Included |
| Utilities, Help, and optional LAN broadcasting | Included | Included | Included |
| Custom colors and bundled theme palettes | — | — | Included |
| Saved appearances and appearance import/export | — | — | Included |
| Remote viewing and remote pop-out windows | — | — | Included |
| Alerts and Game Mode | — | — | Included |

Pro supports this PC plus up to four remote devices: **five devices total**.
Each remote device can use its own pop-out window.

The planned Pro upgrade is a one-time, non-expiring Microsoft Store add-on inside
the Store app. It is not a subscription or a separate Pro installer. Purchase
and restore use the Microsoft Store account that owns the app. Standalone Free
does not accept Store licenses or activation codes.

Beta licenses apply to the beta product; do not assume they transfer to a future
production app. Pricing and availability will accompany the approved release.

Pro theme palettes are bundled for offline use. Dark and Light are always
available. Other palettes stay hidden from the theme picker until enabled.
Hover over Preview to try a palette. Move away to restore the current colors.
Color controls preserve the selected skin and fonts.

Standalone updates will use this GitHub release channel. Store installations
will receive updates through Microsoft Store; their settings will show a
changelog instead of a separate updater.

### Planned Windows remote monitoring

LAN broadcasting is optional and available in Free. Remote viewing requires Pro.
The viewer uses an explicitly added device address and handshake key; do not
expect automatic discovery. Connections use TLS, certificate pinning, and
handshake-key authentication. Enable sharing only on a trusted local network.

## Install the published release

### Windows

Download `flux-setup-free-v1.3.0.exe` and its matching `.sha256` from
[Releases](https://github.com/matthew-hakes/FluxMonitor/releases).
Compare the downloaded file's SHA-256 value with the published checksum:

```powershell
Get-FileHash .\flux-setup-free-v1.3.0.exe -Algorithm SHA256
```

The standalone installer is unsigned. A matching checksum checks file integrity;
it does not identify a trusted Windows publisher or guarantee safety. Download
only from this repository's release page. Do not install a certificate to trust
a Flux development build.

WinGet distribution is planned, but catalog availability is not confirmed.
Use the published GitHub download for now. Command-line installation instructions
will follow catalog verification and installation testing.

### macOS v1.3.0

1. Download `Flux-Monitor-Free-v1.3.0-macOS-arm64.dmg` and its `.sha256` from
   [Releases](https://github.com/matthew-hakes/FluxMonitor/releases).
2. Verify the disk image:

   ```bash
   shasum -a 256 ~/Downloads/Flux-Monitor-Free-v1.3.0-macOS-arm64.dmg
   ```

3. Open the disk image and drag **Flux** to **Applications**.

The published Mac app is ad-hoc signed, not Apple-notarized. Refer to the release
notes for platform-specific installation and sensor information.

### Requirements

- Windows 10 or 11, x64, with a compatible graphics driver.
- macOS 12 or later, Apple Silicon (arm64), for the published Mac release.

Hardware readings depend on the device, firmware, drivers, and permissions.
Windows Server compatibility must be checked for the specific release and system.

## Windows temperature support

For the published v1.3.0 download, refer to that release's setup information.

The pending Windows candidate bundles the official, unmodified PawnIO installer
for optional CPU-temperature setup. The candidate verifies the installer before
it runs. Setup requires your consent and Windows administrator approval. CPU
usage and available clock readings remain usable without temperature setup.

The Store candidate keeps the widget, LAN monitoring, and purchases at normal
user privileges. A separate temperature helper requires administrator consent
for the session. Flux does not add a persistent sensor task or service in this
Store design. PawnIO installs its own driver. Removing Flux does not automatically
remove that shared driver.

Bundling, third-party notices, and Store delivery still require final review and
qualification. No Microsoft approval or universal sensor support is claimed.

## Privacy and support

Refer to the [privacy policy](PRIVACY.md) for data handling and contact information.
Report problems through [Issues](https://github.com/matthew-hakes/FluxMonitor/issues).
Do not post handshake keys, credentials, or other private information in a report.

## Uninstall

### Windows

Open **Settings → Apps → Flux → Uninstall**. Review the options shown by your
installed version before removing settings or optional components.

### macOS v1.3.0

Quit Flux from the Flux Drop, then move `Flux.app` from Applications to the Trash.
To remove preferences too, delete `~/Library/Application Support/com.Flux.Flux`;
remove `~/Library/LaunchAgents/com.matthewhakes.flux.plist` if startup was enabled.

## License

© 2026 Matt Hakes. Free to download, install, and use for personal, non-commercial
use. Redistribution requires prior written permission. See [`LICENSE`](LICENSE).
