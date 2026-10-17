# Flux Monitor Privacy Policy

Last updated: October 6, 2026.

## Scope

Flux Monitor is developed by Matthew Hakes. This policy covers the Windows standalone Free application and Flux Monitor Beta intended for distribution through Microsoft Store. Features available in your edition determine which activities below apply.

This revision describes the Windows beta candidate prepared on October 6, 2026. Earlier versions can retain the older storage behavior described below.

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

The Microsoft Store edition does not use the standalone GitHub updater. Microsoft handles Store distribution and updates under its own privacy practices.

The Store edition checks app and Pro ownership through Windows APIs at startup. It repeats that check approximately once per minute when no Store operation is pending. It also refreshes ownership after license changes, checkout, and a Restore purchases request. Opening Pro requests ownership and product information, including the current formatted price. Checkout starts only after you select the purchase button.

Flux reads product identifiers, purchase outcomes, license status, and expiration through Windows APIs. It keeps the resulting ownership state in process memory. Flux does not save Store account identifiers or license objects in its configuration. Flux does not request your payment-card details, Microsoft password, or a separate Flux account. Microsoft handles Store account, licensing, and payment processing under its own privacy practices. Windows Store services may make network requests or retain records independently of Flux.

External links opened from Flux use your browser and the destination website's privacy practices.

Windows temperature support uses a bundled third-party PawnIO installer. Windows signature verification may contact certificate services. Bundling the installer does not mean Flux downloads it during driver setup.

## Storage and security

Flux stores settings, pairing information, and main diagnostic logs in your Windows user profile. In the Store beta candidate, the temperature helper sends readings through an authenticated local connection to the widget. The widget keeps those readings in memory. The helper does not transmit readings over a network. If you enable broadcasting, the widget can include these readings in the remote snapshots described above.

The standalone edition can also write a current temperature snapshot under ProgramData. Setup errors can be recorded there in a protected diagnostic file associated with your Windows account identifier. Windows packaging, profile roaming, cloud backup, or other software can affect where copies are stored.

Remote traffic is encrypted in transit. Flux creates a persistent local pairing identity during normal startup even when broadcasting is off. The Windows beta candidate protects saved peer pairing keys and the local TLS identity with Windows Data Protection API (DPAPI). This protection is scoped to your Windows user. Other settings, including remote addresses and device labels, do not receive this additional encryption.

DPAPI does not protect against software running as your user or an administrator. Protected files are not portable pairing exports for another Windows account.

Earlier versions stored pairing secrets and the TLS private key without additional application-level encryption, relying on operating-system file permissions and device security. Base64 encoding of those values is not encryption. The candidate migrates active legacy credential files, but does not erase old folders, backups, or copies made by other software. Copying a handshake key places it on the system clipboard, where Windows clipboard history or synchronization settings may retain it.

## Retention and your choices

Preferences and pairing information remain until you remove or replace them. Turning off broadcasting does not delete saved keys. Standalone uninstall preserves settings unless you choose the remove-settings option. Backups, migrated settings, exported files, clipboard history, and copies held by another device may remain separately.

Flux appends diagnostic logs locally and replaces an oversized main diagnostic log at a subsequent launch. It does not apply a fixed age-based deletion period to all local files. Standalone sensor snapshot files are overwritten as readings change, but stopping Flux does not guarantee that the last file is deleted. Historical snapshots from older installations can also remain after an upgrade.

The Store beta helper exits when its widget process ends. Flux does not persist that helper's reading cache or Store ownership state between app sessions. Setup diagnostics have separate lifetimes. The shared PawnIO driver remains installed after Flux closes.

You can inspect or remove local configuration files while Flux is closed, turn off broadcasting, regenerate pairing credentials, remove remote entries, and disable automatic standalone update checks. Removing configuration resets preferences; remove backups and clipboard copies separately when needed.

## Contact and changes

Privacy contact: [Matthew.Hakes@outlook.com](mailto:Matthew.Hakes@outlook.com).

Do not post handshake keys, private logs, or other sensitive information in public GitHub issues. This policy will be updated when Flux's data handling changes; its revision date appears above.
