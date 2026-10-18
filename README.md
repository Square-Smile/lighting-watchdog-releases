# Lighting Watchdog — downloads

A free desktop app that checks a lighting network at load-in and watches Art-Net and sACN during the show — every dropout with its time, length, universes, the fixtures it hit and the likely cause. By [Squaresmile](https://squaresmile.de/lighting-watchdog).

**Free beta.** Download it from [squaresmile.de/lighting-watchdog](https://squaresmile.de/lighting-watchdog) with a free squaresmile.de account, or take the newest files from [Releases](https://github.com/Square-Smile/lighting-watchdog-releases/releases/latest).

## Install

- **macOS** — open the `.dmg` and drag Lighting Watchdog into Applications. Signed and notarised by Apple. The first Watch asks once for your admin password to allow packet capture.
- **Windows** — install [Npcap](https://npcap.com) first (keep "Support loopback traffic" ticked), then run `…_x64-setup.exe` (or the `.msi`). The installer is not code-signed yet: SmartScreen may say "Windows protected your PC" → **More info → Run anyway**.

Check a download against `SHA256SUMS.txt`.

## Requirements

- macOS 12 or newer (Apple silicon and Intel), or Windows 10 / 11 (x64) with Npcap
- A wired network adapter on the lighting network

## Help

The guide: [squaresmile.de/help/lighting-watchdog](https://squaresmile.de/help/lighting-watchdog). Questions and reports: support@squaresmile.de.

## What's in this repository

Only the installers. The source code is not public.

Art-Net™ Designed by and Copyright Artistic Licence.
