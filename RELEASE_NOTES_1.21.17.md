# Orbs 1.21.17

Scanned desktop quests now run 30 seconds past their calculated remaining time. A 15-minute quest observed at 30% keeps its 10:30 remaining-time reading and gets an 11:00 queue target. Finished quests remain excluded, and manually chosen durations remain yours to edit. Discord can still update progress later than the local timer; check the quest in Discord.

This release also restores artwork for exact quest IDs using Discord's public quest configuration, adds a banner fallback, and keeps claimed, completed, and in-Discord activities out of Library's Needs review filter. Queue countdowns now retain the last second when adding game durations.

The scanner handles more slow provider transitions and a narrowly verified focused context menu. It observes menu dismissal after one Escape even if Discord replaces the menu tree during the bridge read. It continues to stop for unknown dialogs, unsaved settings, uncertain actions, or an unverified window. No reward claiming or video-quest automation was added.

The exact installer passed 722 source and 722 packaged tests, 51 native and
51 packaged Chromium cases, plus 288 simulated routes and 12 interruption
boundaries. On Discord Stable, 14 quest cards were scanned. Two already accepted
desktop quests showed 99% with nine seconds remaining; the new queue target was
39 seconds each, preserved through a repeat scan and queue serialization.
All 14 required live starting states, clean channel-settings recovery, guarded
preparation and repeat scans passed the exact-candidate release gate. An
offline installer upgrade/repair/reinstall check was also run separately.
The extra 30 seconds has not been observed to guarantee server-side 100%
credit on every quest.
