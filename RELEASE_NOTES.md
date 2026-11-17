# mimiminer 0.0.4 — Rotating routes & mine depth fix

November 17, 2026. Windows x64, Minecraft Java **1.21**, Fabric. Bundled client mod **0.4.7**. No Python installation is needed.

## Fix for walking without mining

A shallow saved region could leave reachable blocks outside the selected volume. The client correctly refused to break those blocks, while movement continued.

- With **Auto-detect mine size** enabled, detection can recover the full vertical mine depth from a shallow selection. It requires matching enclosed layers and consistent protected-floor evidence before updating Pos.
- Inconclusive or unloaded geometry keeps the existing corners. Turn auto-detection off when you want a fixed manual subregion.
- The maximum selected volume increases from 300,000 to **500,000 blocks**.
- The client still checks the selected boundaries and normal reach before mining. Manual Pos must include the depth you intend to excavate.

## Different routes after mine returns

- Confirmed returns advance through **eight starting sectors**: front-left, front-centre, front-right, right-middle, back-right, back-centre, back-left and left-middle.
- The route starts near the selected sector and alternates lane order. The route counter is saved locally.
- The client clears its previous sweep target when the route changes and aligns movement with the next route direction.
- An ordinary Nuke drop within the mine preserves the current route. Returning to the known entry can advance it.

This spreads starting paths across the mine. It does not guarantee perfectly even excavation or maximum BPS in every layout.

## Recovery improvements

- Idle recovery uses **direct client block breaks** when available. Passive scoreboard gains such as Minion no longer hide a stalled miner; the scoreboard remains a fallback when the client counter is unavailable.
- Reset-and-return handling avoids treating an intermediate reset landing as the permanent mine entry. Existing commands such as `/mine go` and `/mine teleport` remain configurable.
- Verified bounds can be adopted before the miner's full-area inspection, allowing recovery from an undersized saved region.

## Features retained

- **Reset every 45 seconds**, enabled by default, followed by the saved mine return command. All reset modes share a minimum 12-second cooldown. Low-BPS or idle recovery may reset earlier and restart the interval. Menus, upgrades and alerts defer a due reset. Auto teleport recovery is required.
- **Upgrade Best every 30 minutes**, opt-in. Opens the held pickaxe, identifies the exact server button, clicks it once if available, closes the owned menu and resumes mining. The first check is after 30 minutes; the server chooses upgrades and currency. Unavailable buttons and uncertain clicks are not repeatedly retried.
- Transparent in-game Hub, configurable shortcut/opacity, Minecraft font, position capture, sidebar balances, adaptive scan optimization, background mining and Pause & Alert.

Baritone is optional and is not bundled. Application source and personal settings are not published.

## Validation

Publication checks rerun on November 17, 2026:

- **136 Python tests passed**, including coverage rotation, shallow-region detection, idle-counter selection, teleport settling, timers and menu/alert behavior.
- Protected Java checks and **18-class linkage verification passed**.
- The compiled EXE's setup/UI self-test and package audit passed. The app's own Python and Java source files and personal profile data are excluded from the release.

Live observations recorded on October 14, 2026, before this publication:

- A short Akuma ground-mining trial recorded **2,171 direct client breaks**, five confirmed return teleports and six successive starting sectors including the initial route. Mining resumed after every observed return, with no recorded worker pause or connection wait.
- A separate Alt+Tab trial recorded **743 direct client breaks in 54.94 seconds**, approximately **13.52 client blocks per second** across that sample. All 214 samples were in background mode; 213 showed active mining input. This includes time spent moving and recovering, rather than only active scan windows.
- A final background check recorded another 139 client breaks in about eight seconds and active input in all 32 samples. The worker was left running at the end of that earlier session.

These live trials were not rerun during the November 17 publication. They do not establish current server compatibility, extended uptime or a fixed throughput. The previous v0.0.3 trial recognized the server's Upgrade Best button but found no affordable upgrade; an actual server purchase and real 30-minute waiting cycle remain unverified. Clock-based scheduling and menu behavior are covered by automated tests.

## Update

1. Stop mining and close Minecraft and the old mimiminer app.
2. Download **mimiminer.exe** for **v0.0.4**, or extract the Windows ZIP first. Verify the included SHA-256 checksums.
3. Open **Settings → Minecraft setup**, select your existing Fabric 1.21 game folder and click **INSTALL MOD**. The bundled client mod must be updated to **0.4.7**.
4. Restart that Minecraft profile, enter the mine and hold a suitable pickaxe. Keep mimiminer running.
5. On Akuma, use `/mine go`. Check the full depth in Pos 1/Pos 2, or enable **Auto-detect mine size** for verified correction. Existing custom shortcuts and other settings are preserved.
6. Enable **Run in background** for Alt+Tab. Start mining. The in-game Hub uses **Right Shift** by default or your saved key; the mining toggle defaults to **F8**.

Only Minecraft Java 1.21 with Fabric on Windows x64 is supported by this build. TalonMC Prison has prior local testing and Akuma Prison has short local trials. Other configurations remain experimental. Server updates may change behavior.

Read README.md and POLICY_REVIEW.md. Use automation only where applicable game policies and server rules allow it. Testing does not mean server approval. Component notices, including Monocraft's SIL OFL 1.1 license, are included.

**NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**

Publisher: An Le (@anle0429). Contact: work.anle05@gmail.com.
