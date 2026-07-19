<p align="center">
  <img src="orbs.png" width="96" alt="Orbs">
</p>

<h1 align="center">Orbs</h1>

<p align="center">
  <b>Discord Rich Presence telemetry emulator for Windows</b><br>
  Simulate playing any game in Discord's detectable-games database — without launching it.
</p>

<p align="center">
  <a href="https://github.com/JPEG111/orbs-release/releases/latest">
    <img src="https://img.shields.io/badge/download-latest-e52e3d?style=flat-square" alt="Download">
  </a>
  <img src="https://img.shields.io/badge/platform-Windows%2010%2F11-2b2b33?style=flat-square" alt="Windows 10/11">
  <img src="https://img.shields.io/badge/version-1.2.0-2b2b33?style=flat-square" alt="v1.2.0">
</p>

---

## Install

1. Download **`Orbs_Setup_1.2.0.exe`** from the [latest release](https://github.com/JPEG111/orbs-release/releases/latest).
2. Run it. Windows SmartScreen will warn you the publisher is unknown — the installer is unsigned, so this is expected. Choose **More info → Run anyway**.
3. Launch **Orbs** from the Start Menu or your desktop.

No Python installation required. Everything is bundled.

---

## Usage

| Step | What to do |
| :-- | :-- |
| **1. Pick a game** | Open **Game Directory** and search. Results come live from Discord's own database of ~23,000 detectable games. |
| **2. Set a timer** | Drag the slider on the dashboard to auto-stop after a set number of minutes. Leave it at zero to run until you stop it manually. |
| **3. Start** | Hit **START EVASION**. Your Discord status switches to the selected game and the uptime clock begins. |
| **4. Stop** | Hit **STOP EVASION**, or let the timer expire. |

Closing the window minimises Orbs to the system tray and it keeps running. Right-click the tray icon to restore, toggle, or quit.

---

## How it works

Orbs never touches the Discord client. Instead it reproduces the local footprint Discord's process scanner looks for when it decides whether a game is genuinely running.

| Layer | What it does |
| :-- | :-- |
| **Process name** | Copies the Python interpreter to a local directory under the exact filename of the target game's binary, so `EnumProcesses` reports the expected executable. |
| **Window handle** | Creates a real Win32 window with the game's window class and title, positioned off-screen, backed by a live message pump so it never registers as hung. |
| **Rich Presence** | Publishes activity over Discord's local IPC named pipe (`\\.\pipe\discord-ipc-N`) rather than forging REST calls. |
| **Timing** | Draws update intervals from a log-normal distribution instead of a fixed loop, and rotates sessions with realistic breaks rather than running unbroken for hours. |
| **Resource curves** | Derives a per-game CPU/GPU/RAM envelope from a hash of its Discord application ID, then walks the values within that band. |
| **Pre-flight auditor** | Scores every outbound payload against 11 checks — flat timing, round-number timestamps, zero resources, dead window handle, clock monotonicity and others — and halts the session if a critical one fires. |

---

## Scope and honest limits

**The auditor grades Orbs against its own model, not against Discord's.** A clean score means the payload shows none of the anomalies Orbs knows how to look for. It is not evidence that Discord cannot detect the session, and nobody outside Discord knows what their detection actually measures. Treat a clean score as a sanity check, not a guarantee.

**Using this violates Discord's Terms of Service.** Spoofed activity can get an account suspended or terminated. That risk is yours, and it is real regardless of how careful the implementation is. Don't run it on an account you can't afford to lose.

Things that will expose a session no matter what Orbs does:

- **Running a real game at the same time.** Two heavy games at once is an impossible resource footprint.
- **Screen sharing the spoofed game.** The capture hook attaches to a window that renders nothing.
- **Marathon sessions.** Use the timer. A believable session ends.

---

## Troubleshooting

**Status stays "Disconnected"** — Discord isn't running, or is running elevated while Orbs isn't. Start Discord first; match elevation.

**Game shows no cover art** — art is fetched from Steam by title match. Games not on Steam, or with a name that doesn't match cleanly, fall back to a plain tile. Cosmetic only.

**SmartScreen blocks the installer** — the build is unsigned. Code-signing certificates cost money; there is no way around the warning without one.

**Nothing happens after START** — check the activity log on the dashboard. If the worker exited, the disguised executable was most likely quarantined by antivirus (it's a renamed copy of `python.exe`, which is a common heuristic trigger).

---

## Source

This repository carries release builds only. Source lives in a separate private repository.

Built by [Skandar](https://github.com/JPEG111).
