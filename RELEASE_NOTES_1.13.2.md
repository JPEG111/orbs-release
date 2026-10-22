# Orbs 1.13.2

**Scan Discord uses one shared route from the current normal Discord tab.** You
do not need to open Friends or Quests first. Unless the Quests page is already
verified, Orbs establishes Home, opens the sidebar Quests link, verifies All Quests
and reads the loaded cards. There is no starting-tab whitelist.

Home selection must now be observed before opening Quests. The target is scoped
to the actual sidebar row, so a link named Quests in chat or other page content
cannot substitute for navigation. Delayed rendering, no-op actions and ambiguous
navigation remain bounded and produce an explicit error. Original appearance,
saved queues and optional acceptance settings are retained.

123 regression tests and nine native control scenarios passed. New cases cover
unrelated content links outside Home, a duplicate Quests link beside the genuine
sidebar link, and delayed Home selection. The real Discord sidebar structure was
checked; this is not a claim that every Discord screen was individually live-tested.
Blocking dialogs/login and changed/inaccessible client controls can require attention.

A fresh live source-app scan from already open All Quests read 21 cards and added
five supported games to an isolated queue, without accepting quests or running
sessions. The exact offline Sandbox 1.13.1 → 1.13.2 upgrade reused the registered
directory, relaunched one process and preserved queue/settings hashes. Interactive
administrator approval was not tested.
