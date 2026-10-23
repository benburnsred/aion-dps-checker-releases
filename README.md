# Aion DPS Checker — downloads

A DPS meter for **Aion 2** that runs on your PC: party damage, healing and damage taken, per-skill breakdowns, a DPS graph and skill timeline, boss HP and kill timer, ping, field boss respawn timers, and a click-through on-screen overlay.

This repository only hosts the **releases**. Download the newest one from the **[Releases](../../releases/latest)** page.

## Install

1. Download `aion-dps-checker-<version>.zip` from the latest release and unzip it anywhere.
2. Double-click **`start.bat`**.
   - The first time, a pop-up offers to install **Npcap**, the free network-capture driver the meter needs. Click **Yes** and click through its installer with the default options.
   - The meter runs in the **system tray** (the bar-chart icon by the clock), and your browser opens it. Right-click the icon for the overlay, reports, updates and **Quit**.
3. For the overlay to show over the game, set Aion 2 to **borderless windowed**.

To try it without the game, double-click `demo.bat`.

The meter checks this page for new versions and can update itself with one click. Each update is checked against the release's `SHA256SUMS.txt` before anything is replaced.

## Requirements

- Windows 10 or 11
- [Npcap](https://npcap.com). The installer offers to set it up for you.
- Chrome or Edge, for the browser pop-out

Python and everything else the meter needs is included in the zip.

## How it works

The meter **passively reads the game's own network traffic**, the same way ACT does for FFXIV. It never touches the game process, its memory or its files, and it never sends anything to the game. Its web page only listens on your own PC (`127.0.0.1`).

## ⚠ Account risk

NCSOFT has not approved any third-party meter, and its operation policy prohibits "unauthorized programs". **Using any meter is at your own risk.** Keep it to yourself: don't post meter screenshots or use the numbers to call out other players.

## Verifying a download

Each release lists `SHA256SUMS.txt`. In PowerShell:

```powershell
Get-FileHash .\aion-dps-checker-<version>.zip -Algorithm SHA256
```

The hash should match the one in `SHA256SUMS.txt`.

## License

GPL-3.0. Each release zip contains the meter's complete source code (`server/`, `web/`, `scripts/`) and the `LICENSE` file. It builds on GPL-3.0 work by Kuroukihime (AIon2-Dps-Meter), taengu's A2Tools lineage and ZDYoung0519 (NOIA2), credited in the README inside the zip.
