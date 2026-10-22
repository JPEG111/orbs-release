# Orbs 1.13.1

Fixes **Scan Discord** stopping at Friends and waiting for zero quest cards.
Discord's outer Quests row exposed an Invoke action that did nothing; the scanner
now targets the actual link inside it and verifies each page transition.

- Wait for Home navigation when starting outside the home area.
- Open the real Quests link, verify the Quests page and selected All Quests tab,
  then wait for stable quest cards.
- Keep waiting through delayed rendering without navigating back to Home.
- Report the failed navigation stage for no-op, unavailable or ambiguous controls.
- Stop for unexpected dialogs or a changed client process. Queue stays unchanged
  on failure. Original appearance and existing acceptance options are preserved.

121 regression tests passed. The old installed scan reproduced the failure, and
the corrected source-app scan from real Discord Friends read 21 cards/nine play
tasks and added five supported games to an isolated test queue. Native local
fixtures passed Server, Friends, Claimed, already All, no-op and ambiguous cases.
No real quests were accepted and no sessions ran. Live coverage of every Discord
screen is not established; English loaded accessibility controls are still required.
A second live scan from outside Home read the same 21 cards and preserved five
queued games without duplicates. The exact offline Windows Sandbox upgrade from
1.13.0 reused the registered installation, relaunched one process and preserved
queue/settings hashes. Interactive administrator approval was not tested.
