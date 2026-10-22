<p align="center">
  <img src="orbs.png" width="96" alt="Orbs">
</p>

<h1 align="center">Orbs</h1>

<p align="center">
  <b>Appear in-game on Discord without launching anything.</b><br>
  A Windows Rich Presence telemetry emulator: simulate supported games in Discord's
  detectable-games database, so your status shows it even on a slow or capped connection.
</p>

<p align="center">
  <a href="https://github.com/JPEG111/orbs-release/releases/latest">
    <img src="https://img.shields.io/badge/download-latest-e52e3d?style=flat-square" alt="Download">
  </a>
  <img src="https://img.shields.io/badge/platform-Windows%2010%2F11-2b2b33?style=flat-square" alt="Windows 10/11">
  <img src="https://img.shields.io/badge/version-1.13.1-2b2b33?style=flat-square" alt="v1.13.1">
</p>

<p align="center">
  <a href="#install">Install</a> &nbsp;·&nbsp;
  <a href="#usage">Usage</a> &nbsp;·&nbsp;
  <a href="#how-it-works">How it works</a> &nbsp;·&nbsp;
  <a href="#scope-and-honest-limits">Honest limits</a>
</p>

---

> [!IMPORTANT]
> ### "Why can't it do every game?" A line we drew, not a wall we hit
>
> When a game shows as **can't simulate**, that is Discord's own data, not a gap in Orbs: that title lists no Windows app, so there is nothing for Orbs to mirror at the OS level. It is not a bug or a missing feature.
>
> Orbs does not patch the Discord client or use your account's login token. Game presence is simulated locally. Scanning reads loaded quest cards; video tasks are skipped and ambiguous titles stay available for review.
>
> Quest acceptance is optional: when enabled in Settings, scans use the normal Discord controls to accept supported play quests and choose Desktop. This changes quest enrollment in your account. It does not simulate videos or claim rewards.

---

## Install

1. Download **`Orbs_Setup_1.13.1.exe`** from the [latest release](https://github.com/JPEG111/orbs-release/releases/latest).
2. Run it. Windows SmartScreen will warn you the publisher is unknown, because the installer is unsigned. This is expected. Choose **More info → Run anyway**.
3. Launch **Orbs** from the Start Menu or your desktop.

No Python installation required. Everything is bundled.

Already installed? Run the new installer once: it repairs or updates the existing
registered location and keeps your saved queue/settings. Launch the **Orbs** Start
Menu shortcut afterward. Downloaded installers, development builds and backups
are separate files; Windows Search may list them too.

To uninstall, use **Windows Settings > Apps > Installed apps**. Your saved queue
and preferences are retained for reinstalls. Orbs removes only startup commands
that point to the installation being removed.

---

## Usage

| Step | What to do |
| :-- | :-- |
| **1. Pick a game** | Open **Game Directory** and search. Results come live from Discord's own database of ~24,600 detectable games. |
| **2. Set a timer** | Drag the slider on the dashboard to auto-stop after a set number of minutes. Leave it at zero to run until you stop it manually. |
| **3. Start** | Hit **START EVASION**. Your Discord status switches to the selected game and the uptime clock begins. |
| **4. Stop** | Hit **STOP EVASION**, or let the timer expire. |

Closing the window minimises Orbs to the system tray and it keeps running. Right-click the tray icon to restore, toggle, or quit.

### New in 1.13.1

Fixes scanning stopping at Friends and waiting for zero cards. Orbs now clicks
the real Quests link inside the sidebar row, waits for navigation, verifies the
selected All Quests tab and only then reads cards. A no-op click or ambiguous
navigation control produces a specific error and leaves the queue unchanged.
Delayed rendering cannot bounce the client back to Home.

121 tests passed. A corrected real Friends-page scan read 21 cards/nine play tasks
and added five supported games to an isolated test queue. Native local fixtures
also passed Server, Friends, Claimed, already All, no-op and ambiguous cases. No
quests were accepted or sessions started in that validation. The original design
and acceptance settings are preserved; changed Discord controls can still need
manual handling.
A second live scan from outside Home retained all five queued games without
duplicates. The exact 1.13.0 → 1.13.1 Sandbox upgrade preserved saved data and reused
the existing installation.

### Changes in 1.13.0

Enable **Settings > Accept supported play quests and choose Desktop during scans**
to let manual and sign-in scans click **Accept Quest**, open the platform dropdown
when needed, choose **Quest on Desktop**, and verify progress before adding a game.
Already accepted quests skip the acceptance click. Console is never selected.

This option defaults off. Unsupported/ambiguous quests, videos and unexpected dialogs
stay for review. An uncertain action is not retried automatically; use **Details**
and check Discord. Cancelling leaves the queue unchanged but cannot undo quests
already accepted. Saved-queue-only startup does not accept quests. The original
interface is preserved, and Power mode remains removed.

115 tests passed, including acceptance state transitions and cancellation. Native
local control fixtures verified both in-card and external platform menus. Live
Discord acceptance/platform verification remains pending; no reward credit is promised.

### Changes in 1.12.0

**Scan Discord** opens the running client's **Quests > All Quests** view and reads
loaded quest-card accessibility text, including cards below the screen. Manual
scrolling and screenshot OCR are no longer the normal scan path. Navigation uses
the running client's controls and avoids opening another Discord channel through
Windows' global protocol handler.

The summary separates detected play tasks from supported games. Catalog gaps,
unsupported Windows entries and game selections remain visible for review.
Live app verification read 20 cards, detected nine play tasks, queued five supported
games and skipped ten videos. Original appearance and saved queues/timers retained;
103 tests passed. Loaded English desktop cards only; filters/client changes affect
coverage. Detection does not prove quest acceptance or reward credit.

### Changes in 1.11.1

Restores the original Game Directory artwork, glass panels, colours and compact
search rows. Queue timer/reorder/remove buttons are spaced below each title.
The scan progress, cancellation and reliability fixes from 1.11.0 remain;
Power mode stays removed. Saved queues and settings are preserved.

### Changes in 1.11.0

- **Card-aware scanning:** separates quest cards, enlarges their text and checks
  play instructions. Video tasks are skipped; unsupported and ambiguous matches
  remain visible with reasons and a manual search action.
- **Clear loading:** capture, catalog and per-card progress stay visible until all
  names and queue additions are ready. Cancel discards the scan's additions.
- **Readable library:** solid dark result cards, clear queued/review states and a
  scrollable queue with wrapped titles and separate timer/reorder/remove controls.
- **Power mode removed**, including its video runtime modules. Saved queues and
  settings remain intact. Review old queue items imported by earlier scanners.

Since 1.12.0 scanning covers loaded English desktop cards, including cards below
the screen. Filters, unloaded cards and changed accessibility controls can limit
coverage. Acceptance requires the optional 1.13.0 setting above; remaining duration,
eligibility and reward credit still need checking in Discord. Videos stay manual.

### Installation improvements from 1.10.1

- **Installation and updates** in Settings: current version/path, manual check,
  install/retry, logs, copy diagnostics and Quit.
- Repair/upgrade reuses the registered folder, including when an old updater
  supplies a different destination. New installers reject downgrades.
- Current copies reopen the registered app; second launches restore its window.
- Clean shutdown for install/uninstall; saved startup opt-ins work after reinstall.
- Windows file-version metadata, obsolete managed-file cleanup and bounded update
  cache retention. Historical builds and user files are preserved.

### New in 1.10.0

- **Scan Discord:** open the desktop Quests page and click Scan Discord in Game Directory. Readable supported titles enter the saved game queue; duplicate scans preserve existing timers. Scroll and rescan for more cards.
- **Settings:** opt-in Windows sign-in launch, scan and game-queue start, a startup delay and cancellation. New startup actions default off. Manual-launch resume has its own switch.
- Power mode was introduced in this release and removed in 1.11.0.

Scans interpret visible task wording but cannot establish account-side quest
acceptance, eligibility, remaining duration or completion. Automation can put an account at risk.

### Automatic updates

Version 1.12.0 checks at launch and every six hours, with a visible manual check in
Settings and a 15-minute retry after check errors. A newer stable installer is
downloaded and verified; active sessions, queues and scans defer installation.
**Later** postpones it until you choose Install update or reopen Orbs. Windows may
ask for administrator approval. Source pushes alone do not trigger updates.
1.9.1/1.10.0 check again when opened; very old builds may need a manual download.

Old EXEs/installers cannot gain protections retroactively. Use the installed
shortcut rather than historical build copies. Interactive UAC and every possible
antivirus/power-loss failure are not covered by the automated lifecycle tests.

---

## How it works

Orbs never touches the Discord client. Instead it reproduces the local footprint Discord's process scanner looks for when it decides whether a game is genuinely running.

| Layer | What it does |
| :-- | :-- |
| **Process name** | Copies the Python interpreter to a local directory under the exact filename of the target game's binary, so `EnumProcesses` reports the expected executable. |
| **Window handle** | Creates a real Win32 window with the game's window class and title, positioned off-screen, backed by a live message pump so it never registers as hung. |
| **Rich Presence** | Publishes activity over Discord's local IPC named pipe (`\\.\pipe\discord-ipc-N`) rather than forging REST calls. |
| **Process ancestry** | Spawns the worker with a spoofed parent process (`steam.exe` when Steam is running, otherwise `explorer.exe`) via `PROC_THREAD_ATTRIBUTE_PARENT_PROCESS`, so the process tree looks like a normally-launched game rather than a child of Orbs. |
| **Binary metadata** | Rewrites the disguised executable's PE version resource so it carries the game's `CompanyName`/`ProductName` instead of Python's, while preserving the packaged archive intact. |
| **Fingerprint diversity** | Randomises each install's build number so no two users share an identical binary hash. This removes the cross-user cluster signal (see limits below); it does **not** make the hash match the real game. |
| **Timing** | Draws update intervals from a log-normal distribution instead of a fixed loop, rotates sessions with realistic breaks, and adds a random tail to timed sessions so none end on a round minute. |
| **Resource curves** | Derives a per-game CPU/GPU/RAM envelope from a hash of its Discord application ID, then walks the values within that band. Reserves real memory for a believable working set. |
| **Pre-flight auditor** | Scores every outbound payload against 11 checks (flat timing, round-number timestamps, zero resources, dead window handle, clock monotonicity and others) and halts the session if a critical one fires. |
| **Crash resilience** | The worker can never surface a raw exception dialog; any failure is caught, logged, and the OS footprint is torn down cleanly. All activity is written to a log at `%LOCALAPPDATA%\Orbs\orbs.log` for diagnostics. |

---

## Scope and honest limits

**Not every game can be simulated.** Roughly 42% of the ~24,600 apps in Discord's database ship a Windows executable name Orbs can mirror (re-measured October 2026). The rest (mostly newer titles) list no executable at all, so there is nothing to mirror and Orbs marks them "can't simulate" rather than pretending. This is a fact about Discord's data, not a limitation we can code around. See the callout at the top for why Orbs won't reach them by other means.

**There is a ceiling this architecture cannot pass.** Discord's quest heartbeat carries a fingerprint computed from the *actual bytes* of the detected binary. A renamed interpreter fingerprints as the interpreter, not the game. Today Discord largely does not compare this server-side, but if it ever does, every rename-based tool breaks at once, and no amount of local spoofing can fix it, because matching the hash would require the real game's files. Orbs is honest about this rather than claiming to be "undetectable."

**The auditor grades Orbs against its own model, not against Discord's.** A clean score means the payload shows none of the anomalies Orbs knows how to look for. It is not evidence that Discord cannot detect the session, and nobody outside Discord knows what their detection actually measures. Treat a clean score as a sanity check, not a guarantee.

**Using this violates Discord's Terms of Service.** Spoofed activity can get an account suspended or terminated, and enforcement is known to be applied retroactively in batches, so "it worked and nothing happened" is not proof of safety. That risk is yours. Don't run it on an account you can't afford to lose.

Things that will expose a session no matter what Orbs does:

- **Running a real game at the same time.** Two heavy games at once is an impossible resource footprint.
- **Screen sharing the spoofed game.** The capture hook attaches to a window that renders nothing.
- **Marathon sessions.** Use the timer. A believable session ends.

---

## Troubleshooting

**Status stays "Disconnected":** Discord isn't running, or is running elevated while Orbs isn't. Start Discord first; match elevation.

**Game shows no cover art:** art is fetched from Steam by title match. Games not on Steam, or with a name that doesn't match cleanly, fall back to a plain tile. Cosmetic only.

**SmartScreen blocks the installer:** the build is unsigned. Code-signing certificates cost money; there is no way around the warning without one.

**Nothing happens after START:** check the activity log on the dashboard. If the worker exited, the disguised executable was most likely quarantined by antivirus (it's a renamed copy of `python.exe`, which is a common heuristic trigger).

---

## Disclaimer

Orbs is an independent, educational project for personal use. It is **not affiliated
with, endorsed by, or connected to Discord Inc.** "Discord" and related marks belong to
their respective owners and are used here only to describe what the software interoperates
with.

The software is provided **as is, without warranty of any kind**. Automating or simulating
activity on Discord's features may conflict with Discord's Terms of Service and can result
in action against your account. You alone are responsible for how you use it. If you are
not comfortable with that, do not run it. See [Scope and honest limits](#scope-and-honest-limits)
for the full picture.

---

## Source

This repository carries release builds only. Source lives in a separate private repository.

Built by [Skandar](https://github.com/JPEG111).
