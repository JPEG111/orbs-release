# Orbs 1.13.3

Launching another Orbs copy or version now shows **Orbs is already running** in a
dismissible toast and exits. It does not start another dashboard/queue or forward
into a different EXE. Quit the active copy from its system-tray icon before opening
another. The notice closes after about 4.5 seconds and does not take keyboard focus
or add a taskbar window. Background sign-in duplicates exit quietly.

GUI and CLI share the same version/path-independent lock in the current Windows
login session. Legitimate game worker processes remain allowed. Guard checks run
before installed-copy redirection, and rejected launchers release their observer
handles so the toast cannot keep Orbs locked after the original app quits.

132 regressions passed, including real cross-process mutex lifetime tests and
entry-point checks for duplicates, legacy dashboards, sign-in launches, CLI/workers,
access-denied locks and installed handoff ordering. A native toast render verified
its window styles, unchanged foreground and timed dismissal; the preview was
visually inspected. Historical binaries without equivalent protection cannot be
retroactively changed by publishing a new version.

The exact offline Windows Sandbox installer check passed newer-versus-older and
same-version duplicate launches, including a renamed candidate EXE, an older
backup forwarding to the new registered app, and quiet sign-in duplicates. Each
launcher exited with the primary app preserved. The 1.13.2 → 1.13.3 upgrade reused
the registered directory, relaunched one primary process and preserved saved-data
hashes. SYSTEM testing does not establish an interactive user's UAC experience.
