# Orbs 1.13.0

Scans can now prepare supported play quests for Desktop before adding them to the queue.
Enable **Settings > Accept supported play quests and choose Desktop during scans**.
It clicks **Accept Quest** when needed, opens the platform dropdown, selects
**Quest on Desktop**, and checks the resulting progress state. Already accepted
quests skip acceptance; Console is never selected.

The option defaults off and applies to manual and Windows sign-in scans. Videos,
unsupported games, game-choice tasks and unexpected dialogs remain for review.
Uncertain actions are not retried automatically; use **Details** to see what needs
attention. Cancel leaves the queue unchanged but cannot undo accepted quests in
Discord. Saved-queue-only startup does not perform acceptance. Original appearance
and queue controls are preserved; Power mode remains removed.

Validation: 115 tests passed. Native local Windows control fixtures verified
Accept → Desktop → progress with both in-card and external dropdown menus, identity
checks and video exclusion. The exact 1.12.0 → 1.13.0 installer upgrade reused the
registered directory, relaunched one process and preserved saved-data hashes in
an offline disposable Windows Sandbox. Live Discord acceptance/platform end-to-end
verification and interactive UAC remain pending; eligibility/reward credit is not
established by these tests.

Installing over an existing registered copy upgrades that installation. Installed
clients discover published stable releases through the existing updater; pushing
source commits alone does not update users. Windows may request administrator approval.
