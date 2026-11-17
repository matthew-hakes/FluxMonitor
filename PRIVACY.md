# Flux Monitor Privacy Policy

Last updated: November 17, 2026.

## Summary

- Flux Monitor ("Flux") is a desktop system monitor made by Matthew Hakes, an individual developer in Tennessee, United States ("we", "us").
- Flux reads hardware and system information on your computer to show it to you. That processing happens on your computer.
- Flux has no user accounts, no built-in advertising, no usage analytics, no crash reporting service, and no automatic upload of logs to us. We do not receive the readings Flux displays, and we do not sell or share personal information.
- Information leaves your computer only in these cases: standalone update checks and downloads from GitHub; Microsoft Store licensing and purchases in the Store edition; remote sharing that you turn on, which sends readings directly to computers you pair; and websites you choose to open.

## Scope

This policy covers the Windows editions of Flux: the standalone Free edition distributed through GitHub releases and WinGet, and Flux Monitor Beta and later editions distributed through Microsoft Store. Features available in your edition and version determine which parts below apply. This revision describes the current Windows beta candidate. Earlier versions may behave as described in the policy supplied with them.

This revision was checked against the Windows code only. It does not describe macOS-specific storage locations or behavior in detail. If you use Flux on macOS and have a question, contact us.

## Information Flux uses on your computer

**Hardware readings.** Flux reads CPU and GPU models, utilization, per-core usage, temperatures, clock speeds, core and thread counts, graphics memory use, available fan readings, system memory use and characteristics, drive information, and network-interface traffic counters. Drive information includes names or labels, mount paths, capacity, transfer rates, and available temperatures. Network information includes adapter names, transfer rates, and cumulative byte counters. Sensor availability varies by hardware and permissions.

**Settings.** Flux stores your preferences, custom labels, window positions, selected drives and adapters, appearance presets, any storage-tool options left by earlier builds, the time of the last update check, and remote connection settings. Remote settings include device labels, addresses, ports, and pairing credentials. Names, addresses, and paths can contain identifying information.

**Snap Exclusions.** To build its list, the Snap Exclusions picker asks Windows for the titles of visible windows. It lists and saves only Flux's own windows; titles of other programs are discarded and not stored. Rules you save are stored in your settings. Window titles are not included in remote sensor snapshots.

**Storage Explorer and storage tools.** Storage Explorer reads local folder names, file names, paths, sizes, and file-system metadata to build an in-memory usage map. It does not read file contents. Scan results are not included in remote sensor snapshots and are not uploaded by Flux. Closing the utility cancels an active scan; a completed map can remain in application memory until it is replaced or Flux closes.

When you choose Show in Explorer, Flux passes the selected local path to Windows Explorer so it can show that item. Flux does not send that path to remote viewers or any online service.

The current release does not offer storage cleanup. It does not delete files, empty the Recycle Bin, run Windows component cleanup, or run scheduled cleanup, and it does not start a cleanup schedule saved by an earlier build.

Earlier development builds offered cleanup tools. If you used one, its cleanup preferences, schedule times, pending-operation records and result history (time, operation name, result, and error details) can remain in Flux's configuration folder. These records can contain paths and Windows error text, but not file contents. Flux does not upload them or apply additional encryption to them. Windows servicing tools can keep their own logs.

**Diagnostic logs.** Flux writes a local diagnostic log about startup, window behavior, and runtime problems. It can include timestamps, connection addresses (including the address of a computer that pairs for remote viewing), error messages, and hardware details. Flux does not upload logs. Review diagnostic files before sharing them with anyone, including us.

**Clipboard.** When you choose to copy a key or code, Flux places it on the Windows clipboard. Windows clipboard history or synchronization settings may keep it.

## Optional remote sharing

Remote sharing is off by default. Sharing this computer's readings is available in Free and Pro; viewing other computers requires Pro and is not included in the standalone Free edition.

When you turn sharing on, Flux listens for connections on your network (port 5199 unless you change it). A viewer can connect only if you pair it with a one-time code shown on this computer, or if it has this computer's shared handshake key. A one-time code expires after five minutes, can be used once, stops working after repeated wrong attempts, and is kept only in memory. Pairing gives that viewer its own key. Connections are encrypted with TLS, and viewers check this computer's certificate.

A snapshot sent to a viewer includes CPU, GPU, memory, every enumerated drive (including its mount path and label), every enumerated network interface (including its adapter name), and a timestamp. It is not limited to visible tiles or to the drive or adapter selected for display. It does not include your computer name, Windows user name, window titles, file names, file contents, network packet contents, or browsing history.

Remote sharing is designed for a trusted local network. Flux does not send snapshots through any server we operate. Flux does not announce itself on the network; a viewer must be given this computer's address. In the standalone edition, the installer adds a Windows Firewall rule by default (you can untick it) that allows Flux's sharing port on the Private network profile from the local subnet; it is added before sharing is turned on, but nothing listens until you turn sharing on. Turning sharing off does not remove the rule; uninstalling does. The Microsoft Store edition does not create firewall rules; Windows and your other firewall settings decide whether viewers can reach it. Other firewall rules, VPNs, routing, or port forwarding can change who can reach your computer.

You control access:

- Turn off sharing to stop current sharing.
- Remove a paired viewer to end its access.
- Turn off "Also accept the handshake key" so that only paired viewers can connect. The shared handshake key is the same for everyone who has it, so it cannot be withdrawn from one person.
- Regenerate the key to create a new certificate and handshake key, disconnect every viewer, and remove all paired viewers.

Viewers may keep information they have already received. We cannot see, reset, or recover pairing codes, keys, or viewer lists.

## Updates, Microsoft Store and other services

**Standalone update checks (GitHub).** The standalone edition checks GitHub for new releases and release notes. Its update mode is Manual by default; Manual and Auto check at startup and about every six hours while Flux runs, and Off stops automatic checks. A check you request yourself still contacts GitHub. These HTTPS requests send a fixed user agent ("Flux-updater") and no device identifier, app version, or other information about you, but GitHub and its delivery providers receive ordinary connection information such as your IP address. Downloading an update also contacts GitHub's delivery services. GitHub's own privacy practices apply to those requests. Flux installs an update only after you choose to, and only if the download matches a checksum published with the release.

**Microsoft Store.** The Store edition does not use the GitHub updater. Microsoft handles Store distribution and updates. Flux asks Windows Store services whether you own the app and Pro: at startup, about once a minute while Flux runs, after license changes, and when you open Pro, buy Pro, or choose Restore purchases. Opening Pro also requests product information, including the current price. Checkout starts only after you select the purchase button. Flux reads product identifiers, purchase outcomes, license status, and expiration through Windows, and keeps the result in memory only. It does not save Store account identifiers or license data in its configuration. Flux never asks for your payment-card details, Microsoft password, or a separate Flux account. Microsoft handles your Store account, licensing, and payments under its own privacy statement, and Windows Store services may make network requests or keep records independently of Flux.

**PawnIO driver.** Windows CPU temperature support is optional and uses the official PawnIO installer, which is included with Flux and run only when you choose it; Flux does not download it. Windows signature checks may contact certificate services. PawnIO is third-party software with its own terms.

**Websites.** Links opened from Flux use your browser and the destination website's privacy practices.

## Where information is stored, and security

Flux stores settings, pairing information, storage-tool records, and the main diagnostic log in your Windows user profile (for the standalone edition, under `%APPDATA%\Flux`). Windows packaging, profile roaming, cloud backup, or other software can affect where copies are kept.

In the standalone edition, if you choose the optional CPU temperature setup (in the installer, or later from the CPU tile), the sensor service it installs (with Windows administrator approval) writes the current CPU and drive temperature readings to `%ProgramData%\FluxSensorData`, and setup errors can be recorded in `%ProgramData%\FluxSetupDiagnostics` in a file named with your Windows account identifier. In the Store edition, a temperature helper that you approve sends readings to Flux over an authenticated local connection; it does not send readings over a network and does not save them.

Flux creates a persistent local pairing identity at startup even when sharing is off. On Windows, Flux protects saved pairing keys, its list of paired viewers, and its TLS identity with the Windows Data Protection API (DPAPI), scoped to your Windows user. Other settings, including remote addresses and device labels you save on a viewer, are not separately encrypted. DPAPI does not protect against software running as your user or as an administrator. Protected files cannot be moved to another Windows account.

Earlier versions stored pairing secrets and the TLS private key without this additional encryption. Current versions migrate active credential files but do not erase old folders, backups, or copies made by other software.

We take reasonable steps in how Flux is built, but no software or network is completely secure, and we cannot guarantee the security of your computer, your network, or information you share with others. The pairing component uses an open-source cryptography library that is a pre-release version and has not had an independent security audit.

## Retention and deletion

- Settings, pairing information, and storage-tool records remain until you remove or replace them. Turning off sharing does not delete saved keys.
- The main diagnostic log grows over time and is replaced at a later launch once it exceeds a size limit. There is no fixed age-based deletion period for local files.
- The standalone sensor snapshot is overwritten as readings change. Stopping or uninstalling Flux does not delete the last snapshot or setup diagnostics under ProgramData.
- The Store edition's temperature helper exits when Flux exits and does not keep its readings. Store ownership information is not saved between sessions.
- Uninstalling the standalone edition removes Flux's program files, shortcuts, startup entry, sensor service (when it is safe to do so), and firewall rule. It keeps your settings unless you choose the option to remove them. The shared PawnIO driver remains installed; manage it separately in Windows.
- Backups, migrated settings, exported files, clipboard history, and copies held by viewers or other software may remain separately.

You can inspect or delete Flux's local files while Flux is closed, turn off sharing, remove viewers, regenerate keys, and turn off automatic update checks. Deleting the configuration resets your preferences.

## Children

Flux is a general-purpose system utility. It is not directed to children under 13, and we do not knowingly collect personal information from children. Flux does not collect personal information from any user through the app.

## Your rights and choices

Because Flux processes your information on your own computer, you can view, change, or delete it yourself as described above. We do not receive the readings, settings, logs, or keys stored by Flux, so we cannot access, correct, export, or delete them for you.

If you contact us by email, we receive your email address and whatever you send, and use it to respond to you. Depending on where you live (for example under the EU or UK GDPR or California privacy law), you may have rights to ask what personal information we hold about you, and to have it corrected or deleted. Contact us to make a request. We do not sell or share personal information for advertising. You can also complain to your local data protection authority.

GitHub, Microsoft, and other services you use with Flux handle your information under their own policies. Contact them for requests about information they hold.

## Changes to this policy

We will update this policy when Flux's handling of information changes. The date at the top shows the latest revision. A copy is included with Windows packages as PRIVACY.txt, which describes the version it ships with.

## Contact

Privacy contact: [Matthew.Hakes@outlook.com](mailto:Matthew.Hakes@outlook.com).

Do not post handshake keys, pairing codes, private logs, or other sensitive information in public GitHub issues.
