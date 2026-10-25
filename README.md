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
  <img src="https://img.shields.io/badge/version-1.19.1-2b2b33?style=flat-square" alt="v1.19.1">
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

1. Download **`Orbs_Setup_1.19.1.exe`** from the [latest release](https://github.com/JPEG111/orbs-release/releases/latest).
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
| **1. Pick a game** | Open **Library > Discover** and search, or scan Discord Quests. Review support and add games to Queue. |
| **2. Set a timer** | Edit each Queue card’s play-time dial and arrange the order. Home also has an auto-stop slider for a single session. |
| **3. Start** | Click **Start queue** in Library, or **START EVASION** on Home for one selected game. |
| **4. Stop** | Hit **STOP EVASION**, or let the timer expire. |

Closing the window minimises Orbs to the system tray and it keeps running. Right-click the tray icon to restore, toggle, or quit.

### Artwork recovery — 1.19.1

Fixed black game images and quest art appearing only on the card. Discover now
uses the full campaign preview, and queue artwork identifiers survive saving and
rescanning. Blank public assets are skipped so useful game artwork can load.

### Playlist and inspector — 1.19.1

The Queue tab now has compact numbered rows, a selected-game artwork and time
inspector, and a glass footer for totals, Clear and Start. Both time editors stay
synchronized. Reorder, remove, scroll and start your list in English or Egyptian
Arabic; compact windows retain all controls.

### Scanner workspace — 1.19.1

Home and Library now share a split glass scan button with a controller tile, coral
accent/arrow and bold bilingual label. Hover, press and disabled states keep a
stable click area. Release inside to activate; release outside to cancel.


A five-segment progress ring, centered live status and clock, larger controller
and readable Discord guidance show where the scan is. The layout supports English
and Egyptian Arabic at compact and wide window sizes. Stages follow scan events;
elapsed time never invents completion progress.

### Discover showcase — 1.19.1

Discover features a large game panel, compact activity counters and a horizontal
cover browser. Status filters, keyboard navigation, search return and queue actions
remain available. Empty states are centered; Arabic errors and search details are
translated before fitting, keeping titles and descriptions apart.

### Scanner navigation

Fixes the Opening Quests stall: supports the Quests NEW label, allows non-modal
Discord child windows and bounds each navigation stage. Cancel interrupts the
scanner’s read process. If Discord still hides its controls, the scan ends with
a clear instruction to open All Quests manually and retry.

### Queue reliability

Discord activity rejections no longer pass silently. Timers start after an
acknowledged update, pause during an outage and resume after recovery. If
reconnection fails, the current game stays available for Retry. Lists still use
local timers; check Discord for actual quest progress and rewards.

### English / العربية — 1.19.1

Choose **English** or **العربية** on first launch. You can change it live in
**Settings → General → Language**; your queue and automation settings stay intact.
One app and one installer serve both languages.

### بالعربي المصري

- اختار **العربية** أول مرة تفتح التطبيق. تقدر تغيّرها من **الإعدادات ← عام ← اللغة**.
- حدّد ألعابك من المكتبة، ظبّط وقت كل لعبة، وبعدها اضغط **شغّل القايمة**.
- لو الجلسة اتقطعت، وقتك محفوظ. اختار **كمّل اللعبة** أو **الغي القايمة**.
- فحص المهام محتاج واجهة ديسكورد بالإنجليزي حاليًا. سيبه مفتوح على صفحة المهام لحد الفحص ما يخلص.
- أرقام الأوربس والوقت تقديرية. راجع ديسكورد عشان تتأكد من التقدّم والمكافآت الفعلية.

Game names and technical identifiers remain original. Original publisher descriptions
are available through the Arabic game-details link in their original language.

## Fixed in 1.16.7

- A worker exit advances the queue once. Duplicate or late events cannot skip or stop the next game.
- Unexpected exits and startup failures pause the unfinished game with **Retry game** and **Cancel queue**.
- Retry keeps the remaining time. Paused queues remain paused after reopening.
- Timer and exit decisions appear in the local log for diagnosis.

The timer records local runtime; check Discord for actual quest requirements and credit.

## Fixed in 1.16.6 — queue navigation and shared scan controls

- Start queue opens Home; an existing run is shown without restarting it.
- Long game titles and queue subtitles fit above the status rows.
- Close Library summaries with ×; results and queue data remain available.
- Home and Discover use the same controller scan entry, shared two-step preference, live progress view and explicit Cancel action.

[Download 1.16.6](https://github.com/JPEG111/orbs-release/releases/tag/v1.16.6).

### Fixed in 1.16.5 — more resilient scanning

- Handle delayed platform menus, scaled/reflowed layouts and menus above or below their selector using current accessible controls.
- Restore minimized windows when supported and reveal offscreen controls through native accessibility.
- Recover from changing accessibility trees by rereading; never replay an uncertain account action.
- Reject ambiguous targets and stop for visible dialogs, changed clients or leaving All Quests.
- Recheck prepared quests before publishing. Fresh sign-in runs require observed desktop readiness even with auto-accept off.

The same scanner powers Home and Discover. English controls and working accessibility remain required; custom skins and future Discord changes can still need manual handling.

[Download 1.16.5](https://github.com/JPEG111/orbs-release/releases/tag/v1.16.5).

### Fixed in 1.16.4 — quest-card pictures

- Load pictures for review cards, in-Discord activities and completed/claimed quests. These previously skipped the artwork loader entirely.
- Prefer the campaign banner linked to the stable quest ID, including VALORANT ACES, Resident Evil Sale, Clean Crew and Nekome. Keep game artwork as a fallback for identified catalog games.
- Use an optional public artwork index, fetching images only from validated Discord CDN paths. Artwork does not change game identification, quest acceptance, platform choice or queue eligibility.
- Share/cache index requests off the UI thread, bound downloads and keep campaign images separate in the presentation cache. Missing images/index failures leave the existing placeholder/fallback flow available.

[Download 1.16.4](https://github.com/JPEG111/orbs-release/releases/tag/v1.16.4).

### Fixed in 1.16.3 — return from Discover search

- Catalog search now opens a temporary view instead of losing your Discover list.
- Use **Back to Discover**, **Escape**, clear the search field, or click **Discover** to restore your original games, selected card and scroll position.
- Keep cached card artwork and metadata warm when returning. Repeated searches, no matches and lookup failures preserve the original list.
- Ignore search responses delivered after you go back. Refreshing an empty search updates the catalog without erasing scan results.
- Games added to your queue while searching remain queued. A newly completed scan replaces the previous Discover list normally.

[Download 1.16.3](https://github.com/JPEG111/orbs-release/releases/tag/v1.16.3).

### Fixed in 1.16.2 — quest types and title matching

- Recognize **Launch Quest** as an activity played inside Discord. Show **Play in Discord** and instructions instead of **Accepted / Review game** or a search for the base desktop title. These activities never enter desktop acceptance, platform selection or the queue. Finished activity rewards still appear as completed/claimed.
- Resolve a complete instruction name or alias first, then allow a unique catalog subtitle difference: **Nekome** now resolves to **Nekome: Nazi Hunter**. Multiple subtitle choices stay manual; an unlisted edition cannot silently match its base game.
- Use the same trademark, Unicode and apostrophe normalization in scanning and manual catalog search.
- Inspect supported **Play Now** cards whose offscreen progress is absent, even if Discord omits the Accepted label. Reading/revealing alone never changes enrollment. Unknown progress stays unverified.
- Give separately listed Roblox experiences a specific explanation. Clean Crew is not replaced with the Roblox desktop app; multi-game offers still need a manual selection.

[Download 1.16.2](https://github.com/JPEG111/orbs-release/releases/tag/v1.16.2).

### Fixed in 1.16.1 — accepted and finished quest recognition

- Fix accepted quests being reported as not ready when Discord has not exposed
  their offscreen progress rings. The scanner can reveal the exact verified card
  with native accessibility, then reread progress; revealing never clicks Accept,
  changes the platform or claims a reward.
- Distinguish **already accepted** from **accepted now**. An accepted card whose
  Desktop readiness remains unverifiable is labelled accepted and kept for review.
- Show **Completed — claim in Discord** and **Reward claimed** states separately.
  Finished rewards never enter the runnable queue or quest-acceptance candidates.
- Ignore View Quest shortcut controls instead of creating unresolved placeholder
  cards. Do not mistake promotional discount percentages for quest progress or
  round almost-complete progress up to 100%.
- Keep unsupported games visible when optional acceptance is enabled. Catalog
  gaps, game-choice tasks and interactive quests retain their review actions.
- Review/finished details show observed status rather than an endless game-info
  loading message. Snapshot stability includes progress and platform controls.

Existing queue/settings and the 30-rank / 500,000 progression are retained.
[Download 1.16.1](https://github.com/JPEG111/orbs-release/releases/tag/v1.16.1).

### Changes in 1.16.0 — Automatic mode and a 30-rank progression

**Automatic mode** is an explicit setup choice in Settings → General. It
explains the four sign-in steps, lets you choose a 15/30/60/120-second delay, and
applies them together only after **Enable automatic mode**. Opening or dismissing
setup saves nothing. It takes effect at the next Windows sign-in; Resume remains
separate and retains its saved preference. Cancel pending startup is available
during the wait or scan. Existing individual switches remain under Customize.

The status panel now has **30 animated cosmetic ranks**, ending at
**Singularity / 500,000 estimated Orbs**. Eight visual families keep related
shapes and gemstone colours together; simpler models lead into more articulated
versions. The first five stay restrained, while the final winged sequence gains
layers, crowns and orbiting details. The read-only ladder groups each family,
reveals your current rank and supports scrolling and keyboard navigation.

The total, next-rank caption and progress rail sit closer to the visible emblem,
with a larger wide-layout figure. Animations use cached frames and stop while
hidden/minimized. Ranks and time saved are local estimates, not a verified Discord
balance or rank. Spending is unavailable.

The final rank unlocks at **500,000**, with no saved-total reset or clamp.
Names/emblems have moved to follow their visual families, so an existing total
may show a different cosmetic rank. Existing startup action choices are retained;
this update does not silently enable Automatic mode.

See the [1.16.0 release and installer](https://github.com/JPEG111/orbs-release/releases/tag/v1.16.0).

### Changes in 1.15.0 — ranks, scan workspace and gaming typography

- A shared gaming type system across Home, Library, Settings, Audit and dialogs:
  **Oxanium** headings, **Chakra Petch** UI copy and **JetBrains Mono** technical
  readings. Fonts are bundled and load locally; no font installation is needed.
- **Scan Discord from Home**, with the same optional Accept Quest → Desktop
  setting as Library. A compact glass workspace shows the actual scanner action,
  elapsed time and an event-driven five-stage rail with a cached light sweep.
- Clear scan guidance: leave Discord open on Quests without navigating, scrolling,
  minimizing or closing it. You can use other apps. Cancel remains in Library;
  results and queue additions appear together after completion.
- **Ten distinct animated ranks**, Ember through Ascendant, with next-unlock
  progress and a read-only ladder. They are cosmetic app ranks based on locally
  estimated earned Orbs, not Discord ranks or a verified balance.
- A transparent native caption and refined status glass over the selected game
  scene. Library details have local glass for contrast; Home's hero, button and
  lower figures remain directly on the sharp artwork. Settings/Audit soften it.
- Fixed late/missing art updates, saved queue icon hashes and unrelated
  similar-title fallback art. Unresolved quests retain neutral media and review
  actions. Available source resolution still limits some games.

The existing stacked Discover selection, editable Queue dials, cached hover/press
feedback, startup opt-ins, tray, updater and duplicate-version protections remain.
Discover searches the public game catalog and presents scan results; it adds to
one saved queue. Video completion and reward claiming remain manual.

Orbs and time saved are **local estimates**. Spending is unavailable; game/runtime
tracking began in 1.14.4, and old history is not reconstructed. Verify quest
eligibility, progress and rewards in Discord. The app adds no browser runtime.

See the [versioned release and installer](https://github.com/JPEG111/orbs-release/releases/tag/v1.15.0).

### Changes in 1.13.3

Opening another Orbs copy or version while one is running now shows **Orbs is
already running** in a dismissible toast, then exits. It cannot start another
dashboard or queue. Quit the active copy from its tray icon before opening a
different one. The notice closes after about 4.5 seconds without taking keyboard
focus or adding a taskbar window. Sign-in duplicates exit quietly.

The lock is shared across versions and paths in the current Windows login session.
GUI and CLI participate; legitimate game workers remain allowed. Duplicate checks
run before installed-copy forwarding, and a rejected launcher cannot keep the lock
alive after the original app quits.132 regressions and a real native toast render
passed. Old binaries without equivalent protection cannot be retroactively changed.

### Changes in 1.13.2

Scan from your current normal Discord tab; opening Friends or Quests first is
unnecessary. Orbs uses a shared route: establish Home unless already on verified
Quests, open the sidebar Quests link, verify All Quests, then read cards. Starting
tabs are not whitelisted. Links named Quests in chat/page content are ignored.

123 regressions and nine native scenarios passed, including unrelated/duplicate
link labels and delayed Home selection. Actual sidebar structure was checked in
Discord. These tests do not mean every possible client view/layout was individually
live-tested. Blocking dialogs/login or changed controls can still need attention.
Original appearance, saved queues and optional acceptance settings are preserved.

### Changes in 1.13.1

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
- Current copies use the registered app when none is running; since 1.13.3,
  duplicate launches show a toast and exit.
- Clean shutdown for install/uninstall; saved startup opt-ins work after reinstall.
- Windows file-version metadata, obsolete managed-file cleanup and bounded update
  cache retention. Historical builds and user files are preserved.

### New in 1.10.0

- **Scan Discord:** click Scan Discord in Library. Orbs navigates to desktop Quests and reads loaded accessible cards, including below the screen. Review the matches and timers before Start; unsupported/unresolved quests stay available for attention.
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

**Not every game can be simulated.** Roughly 42% of the ~24,800 apps in Discord's database ship a Windows executable name Orbs can mirror (public catalog checked 23 October 2026). The rest (mostly newer titles) list no executable at all, so there is nothing to mirror and Orbs marks them "can't simulate" rather than pretending. This is a fact about Discord's data, not a limitation we can code around. See the callout at the top for why Orbs won't reach them by other means.

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

**Game shows no cover art:** artwork uses exact Steam matches and identity-checked public Discord covers. Missing publisher assets or network failures use a neutral cover/default scene. Some source images are small; requesting a larger size cannot recover missing detail.

**SmartScreen blocks the installer:** the build is unsigned. Code-signing certificates cost money; there is no way around the warning without one.

**Nothing happens after START:** check the Audit page. If the worker exited, the disguised executable was most likely quarantined by antivirus (it's a renamed copy of `python.exe`, which is a common heuristic trigger).

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
