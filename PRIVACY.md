# Flux Monitor Privacy Policy

Last updated: October 6, 2026.

## Scope

Flux Monitor is developed by Matthew Hakes. This policy covers the Windows standalone Free application and Flux Monitor Beta intended for distribution through Microsoft Store. Features available in your edition determine which activities below apply.

Flux processes hardware information on your computer to display system readings. The application has no built-in advertising, usage analytics, or automatic upload of diagnostic logs to the developer. Optional remote monitoring sends readings directly to another computer; standalone update checks contact GitHub.

## Information used on your computer

Flux reads CPU and GPU models, utilization, temperatures, clock speeds, core counts, graphics memory use, available fan readings, system memory use and characteristics, drive information, and network-interface traffic counters. Drive information includes names or labels, mount paths, capacity, transfer rates, and available temperatures. Network information includes adapter names, transfer rates, and cumulative byte counters. Sensor availability varies by hardware and permissions.

Flux stores your preferences, custom labels, window positions, selected drives and adapters, appearance presets, and remote connection settings. Remote settings include device labels, addresses, ports, and pairing credentials. These names, addresses, and paths can contain identifying information.

The Utilities window picker reads visible window titles so you can select a snapping exclusion. Titles can include document or website names. Rules you save are stored in your settings. Window titles are not included in remote sensor snapshots.

Flux writes local diagnostic logs for startup, window behavior, and runtime troubleshooting. Additional diagnostics can include connection addresses, errors, and hardware details. These logs are not automatically uploaded by Flux. Review diagnostic files before sharing them with anyone.

## Optional remote monitoring

Broadcasting is off by default. Enabling it allows a reachable viewer with your handshake key to receive sensor snapshots over an encrypted TLS connection. The key is a credential: share it only with people and computers you trust.

A snapshot includes CPU, GPU, memory, every enumerated drive, every enumerated network interface, and a timestamp. It is not limited to visible tiles or the drive or adapter selected for display. It does not include file contents, network packet contents, or browsing history.

Remote monitoring is intended for a trusted local network. Flux's managed Windows firewall rules restrict access to the Private profile and local subnet, but other firewall rules, VPNs, routing, or port forwarding can change reachability. Flux does not send these snapshots through a developer-operated cloud relay.

You can turn off broadcasting to stop current sharing. Successfully regenerating the handshake key stops existing sessions and invalidates the previous credential for future connections. Removing a saved remote device removes that connection entry; it does not revoke a key the other party already possesses. Recipients may retain information they receive.

## Updates and other services

Standalone Free checks GitHub for releases and release notes by default, including in Manual mode. Auto and Manual modes check at startup and periodically while running. These HTTPS requests expose ordinary connection information, such as your IP address and the Flux-updater user agent, to GitHub and its delivery providers. They do not include sensor snapshots or pairing credentials. Setting update mode to Off disables automatic update and release-note requests; explicitly requesting an update check can still contact GitHub. Requested installer and checksum downloads also contact GitHub's delivery services.

The Microsoft Store edition does not use the standalone GitHub updater. Microsoft handles Store distribution and updates under its own privacy practices. External links opened from Flux use your browser and the destination website's privacy practices.

Windows temperature support uses a bundled third-party PawnIO installer. Windows signature verification may contact certificate services. Bundling the installer does not mean Flux downloads it during driver setup.

## Storage and security

Settings, pairing information, and main diagnostic logs are stored in your Windows user profile. Elevated sensor components can also write a current temperature snapshot under ProgramData. Setup errors can be recorded there in a protected diagnostic file associated with your Windows account identifier. Windows packaging, profile roaming, cloud backup, or other software can affect where copies are stored.

Remote traffic is encrypted in transit. Flux creates a persistent local pairing identity during normal startup even when broadcasting is off. Current pairing secrets and the local TLS private key are stored without additional application-level encryption and rely on operating-system file permissions and device security. Base64 encoding of these values is not encryption. Copying a handshake key places it on the system clipboard, where Windows clipboard history or synchronization settings may retain it.

## Retention and your choices

Preferences and pairing information remain until you remove or replace them. Turning off broadcasting does not delete saved keys. Standalone uninstall preserves settings unless you choose the remove-settings option. Backups, migrated settings, exported files, clipboard history, and copies held by another device may remain separately.

Flux appends diagnostic logs locally and replaces an oversized main diagnostic log at a subsequent launch. It does not apply a fixed age-based deletion period to all local files. Sensor snapshot files are overwritten as readings change, but stopping Flux does not guarantee that the last file is deleted.

You can inspect or remove local configuration files while Flux is closed, turn off broadcasting, regenerate pairing credentials, remove remote entries, and disable automatic standalone update checks. Removing configuration resets preferences; remove backups and clipboard copies separately when needed.

## Contact and changes

Privacy contact: [Matthew.Hakes@outlook.com](mailto:Matthew.Hakes@outlook.com).

Do not post handshake keys, private logs, or other sensitive information in public GitHub issues. This policy will be updated when Flux's data handling changes; its revision date appears above.
