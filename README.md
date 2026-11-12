<p align="center">
  <img src="orbs.png" width="96" alt="Orbs app icon — Discord Quests utility for Windows">
</p>

<h1 align="center">Orbs — Discord Quests Scanner & Game Activity Simulator for Windows</h1>

<p align="center">
  Orbs is an independent Windows desktop utility for reviewing Discord Quests, simulating supported game activity, and managing timed game queues.
</p>

<p align="center">
  <a href="https://github.com/JPEG111/orbs-release/releases/latest">
    <img src="https://img.shields.io/badge/Download-Latest%20Windows%20Installer-e52e3d?style=for-the-badge" alt="Download the latest Orbs Windows installer">
  </a>
  <img src="https://img.shields.io/badge/Windows-10%20%2F%2011-2b2b33?style=for-the-badge" alt="Windows 10 and 11">
  <img src="https://img.shields.io/badge/Interface-English%20%2B%20Arabic-2b2b33?style=for-the-badge" alt="English and Arabic interface">
</p>

> [!WARNING]
> **Discord account risk — read before using.** Discord's [Platform Manipulation Policy](https://discord.com/safety/platform-manipulation-policy-explainer) prohibits scripts, spoofed apps, and other tools that simulate Quest completion or engagement without performing the required activity. Using Orbs to simulate activity may result in Quest restrictions or other account enforcement. Orbs is **not endorsed by Discord**, is **not undetectable**, and cannot guarantee Quest progress, rewards, or account safety.
>
> **Do not run it continuously or repeatedly.** The project recommends leaving **at least three days between optional usage sessions** as a conservative restraint, **not a validated safe interval or a method of avoiding detection**. Any use can still be detected and penalized. Automatic mode may repeat at every Windows sign-in, so leave it off if you do not want repeated sessions. **Complete Quests that require actual gameplay, specific game actions, video watching, streaming, or in-Discord activities by doing those activities normally.** The only way to avoid the account risk from activity simulation is not to use simulation.

## What is Orbs?

**Orbs for Discord** is a Windows 10/11 app that brings a Discord Quest scanner, supported game-activity simulation, and a sequential queue manager into one desktop interface. It can inspect the Quests visible in your selected Discord desktop client and help you organize supported **Play on Desktop** tasks.

Orbs reproduces local game presence and communicates through Discord's local Rich Presence connection. It does **not** patch the Discord client, ask for your Discord account token, or directly submit Quest-completion requests. Discord—not Orbs—determines whether any Quest progress or reward is awarded.

This is a **public download and documentation repository**. The application's source code is maintained privately; Orbs is **not advertised as open source**.

## Main features

- **Discord Quest scanner:** inspect loaded Quests through the Discord desktop interface, identify supported desktop play tasks, and flag unsupported or ambiguous items for review.
- **Optional Quest preparation:** for supported tasks, use the visible Discord interface to accept a Quest, select **Quest on Desktop**, and confirm that it appears ready before queueing.
- **Scan & start:** prepare positively ready, supported desktop tasks and create a queue based on the remaining required play time. Turn one-click behavior off for scan-only control.
- **Game activity simulation:** present supported game activity to the selected local Discord client without launching the actual game. Local activity acknowledgement is **not** proof of Quest credit.
- **Editable game queue:** reorder entries, change durations, and run one supported game entry at a time. A paused or interrupted queue keeps the remaining local time for manual retry.
- **Discord Stable, PTB & Canary:** choose from installed or running desktop clients; sessions stay bound to the selected client.
- **English and Egyptian Arabic interface:** choose your language at setup or change it later. Discord's own interface currently needs to be **in English for scanning**.
- **Artwork, diagnostics & statistics:** game covers, scan feedback, estimated local Orbs/time-saved statistics, and a cosmetic 30-rank progression.
- **Installer and updates:** Windows installer, optional startup settings, update checks, and preservation of saved preferences and queues across normal upgrades.

## Download and install Orbs

1. Open **[Latest Orbs release for Windows](https://github.com/JPEG111/orbs-release/releases/latest)**.
2. Download the Windows setup executable from the release assets and install it. **Python is not required.**
3. Open the installed **Orbs** app, select your language and the Discord desktop client you use.
4. Keep Discord open, signed in, and set to **English** before starting a Quest scan.
5. Review detected tasks and their requirements in Discord. Use **Library → Discover** and **Queue** for manual control, or **Scan & start** for the supported one-click flow.

**Latest published version checked for this documentation:** [Orbs 1.21.16](https://github.com/JPEG111/orbs-release/releases/tag/v1.21.16) (November 2, 2026). Use the latest-release link above for future versions.

> **Windows download notice:** The installer is not code-signed, so Microsoft Defender SmartScreen may warn about it. Download only from this repository's Releases page, verify that you trust the publisher and file, and do not disregard an unexpected security warning.

## Supported versus manual Quest types

| Discord Quest requirement | Orbs behavior |
| --- | --- |
| Supported **Play on Desktop** game with a recognized local runtime | May be prepared and added to a timed simulation queue; actual progress is not guaranteed |
| Multiple eligible desktop games | Attempts a verified supported choice; uncertain choices remain for review |
| Video or trailer Quest | Complete the viewing requirement manually in Discord |
| **Launch Quest** or in-Discord activity | Open and complete the activity in Discord |
| Stream a game to a friend | Perform the streaming requirement genuinely |
| In-game action, linked-account achievement, or game-specific objective | Play the game and complete the actual objective |
| Completed, claimed, ambiguous, or unsupported task | Not automatically added to the desktop simulation queue |

See [Discord's official Quests FAQ](https://support.discord.com/hc/en-us/articles/22225719947543-Discord-Quests-FAQ) for current Quest types and completion requirements.

## Settings, updates, and saved data

Orbs can optionally start at Windows sign-in, scan Discord, prepare ready desktop tasks, and run a fresh queue. **These are opt-in settings**, and automatic mode can trigger on every sign-in; see the account-risk warning above. You can disable **One-click scan & start** for scan-only behavior and keep a manually edited queue instead.

Orbs checks for app updates on launch and periodically while installed. Find **Check for updates**, install controls, and **Open logs** under Settings. Active operations defer installation. Normal updates and reinstalls preserve the saved queue and preferences. Closing the main window may leave Orbs in the system tray; use the tray menu to quit fully.

## FAQ — Orbs, Discord Quests and Discord Orbs

### Does Orbs automatically earn Discord Orbs?

**No guarantee.** Orbs can simulate supported desktop game presence and show local estimates, but Discord decides whether a Quest advances and whether rewards are issued. Check actual progress and your spendable Orbs balance in Discord. Orbs does not claim rewards automatically.

### Is Orbs safe or undetected if used only once every three days?

**No.** Three days is a conservative usage recommendation, not a tested safety threshold. Discord explicitly prohibits simulated Quest completion without the required activity. The account may be restricted regardless of frequency.

### Does Orbs work with every Discord Quest or game?

**No.** Support depends on the Quest type, its desktop task requirements, recognizable game metadata, and the current Discord desktop interface. Unsupported titles and tasks needing genuine in-game actions require manual completion. Orbs does not automate videos or in-Discord activities.

### Does Orbs need my Discord token or modify Discord?

**No.** It uses the running Discord desktop client, local presence communication, and interface accessibility. It does not request account tokens or patch Discord. This does **not** mean that simulation is authorized by Discord.

### Can Orbs scan Discord PTB or Canary?

**Yes**, when the selected Discord channel is installed or running and supported by the current build. You choose the client in setup or Settings.

### Is Orbs free or open source?

The **installer is available on the Releases page**. This repository does not publish source code or make an open-source licensing claim. Refer to each release for its download details.

### Do I need Python to use Orbs?

**No.** The downloadable Windows installer includes the packaged app. Python is only relevant to the private development workflow.

## Troubleshooting and help

If scanning fails, confirm that the chosen Discord desktop client is running and that Discord's interface language is English. Leave the Discord window open and avoid navigating, scrolling, minimizing, or closing it during the scan. Some changed or unfamiliar Discord layouts may need manual navigation. Review **Settings → Open logs** for diagnostics. An unsupported Quest or a local timer ending does not mean a reward was granted.

For version history, downloads, and fixes, see **[All Orbs releases](https://github.com/JPEG111/orbs-release/releases)**.

---

**Independent community software.** Orbs is not affiliated with, approved by, or endorsed by Discord. Discord and its marks belong to their respective owners. Use is at your own risk and subject to Discord's rules. Built by [Skandar](https://github.com/JPEG111).
