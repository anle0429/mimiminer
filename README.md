<p align="center"><img src="assets/mimi.png" alt="Mimi, the mimiminer mascot" width="144"></p>

# mimiminer 0.0.3
I coded this with the help of Codex just because I'm bored during a hackathon and has too much quota.

I just realized they don't allow to automine in this server tho, use it as ur own risk.
A small Windows desktop app for mining inside a selected block volume in Minecraft Java Edition.

**NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**

Publisher: **An Le ([anle0429](https://github.com/anle0429))**. Product and rights inquiries: **[work.anle05@gmail.com](mailto:work.anle05@gmail.com)**. The publisher is responsible for this app. It is not affiliated with TalonMC or the projects credited below.

## What's new in v0.0.3

Released **October 14, 2026**, with client mod **0.4.6**:

- **Reset every 45 seconds:** enabled by default, with its own switch in desktop Settings and the in-game Hub. Sends `/mine reset`, then your saved mine return command, without waiting for low BPS. Requires Auto teleport recovery. Other recovery resets restart the 45-second timer. Menus, pickaxe upgrades and Pause & Alert defer a due reset until normal mining resumes.
- **No reset bursts:** all reset requests share the existing 12-second minimum cooldown. A late timer requests one reset, and starts a new 45-second interval; it does not replay missed intervals. An uncertain command still reserves the next interval.
- **Upgrade Best every 30 minutes:** replaces the old per-enchant/per-currency buyer. Right-click the held pickaxe, find the server's **Upgrade Best** button, click it once and return to mining. First check is after 30 minutes; the server decides the upgrades and currency. The old Tokens/Orbs/Gems switches have been removed.

The live Akuma timer trial completed two resets **45.13 seconds apart**, with background mining resuming after both return teleports. The current server Upgrade Best button was unavailable, so an actual purchase remains unverified. See **[release notes](RELEASE_NOTES.md)** for exact behavior, test conditions and update steps.

Features carried forward from v0.0.2:

- **In-game Hub:** a transparent panel with Minecraft's font, configurable shortcut/opacity, position capture, settings and Start/Stop/Save/Resume. Mining continues while this panel is open.
- **Pickaxe menu control:** opens the held pickaxe using the normal right-click action and returns to mining after an owned menu closes.
- **Low-BPS recovery:** request `/mine reset`, then `/mine go`, `/mine teleport` or your configured return command. At least 12 seconds between reset requests.
- **Player balances:** read visible money, Tokens, Orbs/Ores, Gems and Credits, including K/M/B/T/Q abbreviations.
- **Background fixes:** keep the bot running through mine inspection, return teleports and owned pickaxe-menu transitions after Alt+Tab.
- **Minimal desktop UI:** Minecraft-style Monocraft font, compact Mine view and persistent Start/Stop controls. Adaptive scan optimization and Pause & Alert are included.

Download the new EXE and reinstall the bundled mod, then restart Minecraft. Check the included **SHA256SUMS.txt**. Previous v0.0.2 downloads remain available in Releases.

## Compatibility — please read first

**This release works only with certain server configurations. TalonMC Prison has been tested, and short mining trials on Akuma Prison now work with the setup below. It is not a universal auto-miner.**

| Requirement / server | Status |
| --- | --- |
| Windows x64 | Required |
| Minecraft Java **1.21** with Fabric | Required; automatic setup is available |
| TalonMC Prison | Successful local testing; server updates, pickaxes and mine layouts may change results |
| Other servers | Unsupported / experimental; no compatibility promise |
| Akuma Prison | Short background trials with flight and ground movement passed; extended ground uptime and automatic mine sizing remain experimental. Use `/mine go`. |
| Other Minecraft versions, Bedrock, Forge or NeoForge | Not supported by 0.0.3 |

Successful testing on TalonMC **does not mean TalonMC permits or endorses this app**. We have not verified an official TalonMC rule allowing auto-mining. Check current server rules and obtain permission before using automation. Applicable Minecraft, Microsoft and Xbox policies also apply; server permission does not override them. Automation that creates an unfair advantage may violate those policies. There is no ban-free guarantee, fixed BPS promise or verified many-hour uptime guarantee.

## Download

Open **[Releases](https://github.com/anle0429/mimiminer/releases)** and download **mimiminer.exe** for **v0.0.3**. Open it to get started. The executable includes its license notices under **Settings → About & licenses**. A Windows ZIP is also available if you want the app, guide and notices together; extract it before opening the app. Keep notices with any package you share.

The app includes its own runtime, so you do not need to install Python. You still need a licensed Minecraft Java account, the Minecraft Launcher and internet access for first-time setup. This release is unsigned; check the release SHA-256 before running a downloaded copy. Do not disable security protection to run it.

## First-time setup

1. Install the official Minecraft Launcher and sign in with your Minecraft Java account. Run Java Edition once, then close the game and Launcher.
2. Open **mimiminer.exe**. Open **Settings**, then click **Minecraft setup**.
3. Click **AUTOMATIC SETUP • MINECRAFT 1.21 + MOD**, then wait for setup to finish. If you already use Fabric 1.21, select that profile's game folder and click **INSTALL MOD** instead.
4. Open the Launcher and select **mimiminer 1.21**, or the Fabric 1.21 profile you chose. Launch the game.
5. Enter a mine where you are allowed to use automation and select a suitable pickaxe in your hotbar.

Minecraft itself is downloaded through the Launcher. This package does not include Minecraft game files or Microsoft account credentials. Sign in only through the official Launcher; mimiminer does not ask for your password.

## Set your mine and start

The minimal **Mine** view keeps corners, current position, session state, direct-client BPS and Start/Stop visible. **Settings** contains your return command, toggle key, Minecraft setup, scan/movement options and Pause & Alert. Settings scrolls separately, while Start/Stop remain available.

The **in-game Hub** opens with **Right Shift** by default. Open the EXE once and leave it running. The transparent panel uses Minecraft's current font and lets you set positions, save options, start, stop and manually resume alerts without switching apps. Change the Hub key and opacity in its **Settings** tab, or change the key through Minecraft Controls. Existing custom keys are preserved. Choose a key that does not conflict with your game controls or Windows shortcuts. Mining continues with this Hub open; chat, inventory and other menus still pause mining. The desktop app uses the bundled [Monocraft](https://github.com/IdreesInc/Monocraft) font.

**Prison automation** is configurable in the desktop Settings and the in-game Hub:

- **Reset at low BPS:** measures direct client block breaks over an active window, then requests `/mine reset` and your configured return command when low progress persists. Idle recovery can also request a reset. The app waits at least **12 seconds** between reset requests and warms up after teleports or menu pauses. The server can reject a command; delivery to the client does not confirm a server reset. Raise or lower the BPS threshold for your pickaxe.
- **Reset every 45 seconds:** a separate timer, enabled by default. Turn it off in Settings if you only want low-BPS/idle recovery. It requires **Auto teleport recovery** to return safely to your mine. It waits through menus, upgrade cycles and latched alerts. Every reset request restarts the interval, including low-BPS or idle resets. Sleep/disconnection/menu delays do not cause accumulated reset requests.
- **Upgrade Best every 30 minutes:** opt in with this switch. After 30 minutes of an active worker, it opens the held pickaxe normally, identifies the exact **Upgrade Best** label (including small-cap/resource-font text), and clicks that button once. It closes the owned menu and resumes mining. A missing, ambiguous or unavailable button is skipped. An uncertain click is not retried; the next check is reserved for 30 minutes later. Pause & Alert interrupts the cycle.
- **Server-controlled upgrades:** the server's Upgrade Best function decides what to buy and which balances to spend. The app no longer selects individual enchants, calculates upgrade prices or offers Tokens/Orbs/Gems spending switches. Auto upgrade is off until enabled. Sidebar balances are still shown as estimates.

The balance reader supports K/M/B/T/Q suffixes and keeps the server's abbreviated balance text in the in-game panel. The local telemetry also records the visible sidebar lines to diagnose server formatting differences.

The new in-game timer switch requires bundled client mod **0.4.6** and a Minecraft restart. Download v0.0.3, close Minecraft, and use **Settings → Minecraft setup → INSTALL MOD** for your current Fabric 1.21 profile. Existing settings and custom keys are kept.

The previous v0.0.2 Akuma trial completed 90 seconds with background mining, the older upgrade mechanism and reset/return transitions. Those results do not establish compatibility for every server's Upgrade Best button or multi-hour uptime.

1. Choose **two opposite corners of the entire block volume**, including its depth. For example, Pos 1 `100, 70, 100` and Pos 2 `120, 40, 120` describe an inclusive rectangular volume.
2. Enter each corner's **X, Y, Z** values. Alternatively, stand at a corner and click **Use my position** beside that Pos. This captures the block coordinate where you are standing; adjust it manually if the mine's corner block is below you or farther down. F3 can help you check coordinates.
3. Open **Settings** and set **Return command** to the command your server accepts, such as `/mine teleport`. Test the command yourself first. Commands vary by server.
4. In **Settings**, enable **Fast adaptive sweep**. Enable **Auto teleport recovery** if you want to return when mining stops making progress. Leave **Flight mode** off for ground movement; turn it on only when flight is available and allowed on your server.
5. Click **START**, return to Minecraft, and close menus before the countdown finishes.
6. Press **F8** to turn mining on or off. Open **Settings** and click the **Toggle key** button to choose a different key. You can also click **STOP**.
7. Leave **Run in background** enabled to keep mining when you Alt+Tab to another application. It is enabled by default. Turn it off if you prefer mining to pause whenever Minecraft loses focus.
8. **Pause & Alert** is enabled by default. Open **Settings → Pause & Alert** to set a detection distance from **0.5 to 64 blocks** (default **8**), enable sound, and choose the optional **"what's up?"** greeting. A nearby player or incoming chat mentioning your account username stops mining and changes START to **RESUME**. The greeting can be sent at most once per START, only for proximity alerts.

Alerts remain paused even after the player leaves. Click **RESUME** yourself when ready, then close any Minecraft menu. This acknowledges players already nearby; a new arrival or a player returning later can trigger another pause. F8 stops the active worker; it is not the alert-resume button. Disabling Pause & Alert does not automatically clear an existing pause.

Stop before changing the corners. Opening chat, a game menu or a loading overlay still pauses mining inputs. With **Run in background** enabled, switching away from Minecraft continues the active bot; Minecraft's automatic lost-focus menu is suppressed only while the bot's connection remains alive. It does not lock your desktop cursor or send mining keys to other apps. Keep the app and Minecraft running; sleep, suspension, disconnection and an unloaded world cannot continue mining.

Upgrading from 0.0.1 requires installing the updated client mod and restarting Minecraft. The app will tell you if your loaded mod does not support background mode. Existing settings and mine corners are preserved. F8 is a global shortcut; select another toggle key if it conflicts with the application you use while mining.

The mine command can return you to a point outside the selected volume. The app remembers observed entry points for each server and mine configuration; it does not expand the selected mining volume to include that point. A new server or layout may still need fresh configuration.

On **Akuma**, enter **Prison** first, then use **`/mine go`** and select corners inside your current mine. Do not reuse TalonMC coordinates. Akuma can replace block types and enlarge the mine as your rank increases. Block recognition refreshes when mining progress disappears. With **Auto-detect mine size** enabled, the app periodically checks the nearby mine and updates both Pos fields and the saved route when it can verify its boundaries. If detection is inconclusive, it keeps the existing corners. Turn this option off to keep a manually selected subregion fixed. Automatic detection is experimental and does not support every mine layout; the selected volume remains limited to 300,000 blocks.

**Flight mode** off requests ground movement, including turning off actual flight if it is observed after a teleport. Ground scanning includes nearby side blocks when standing on a protected floor. Short ground-only background trials now pass, including mine inspection without opening Minecraft's lost-focus menu. Complete live ground operation across all rank changes and extended sessions remains unverified.

**Auto-optimize scan** is enabled by default with Fast adaptive sweep. The Hub displays the current strategy, measured direct-client BPS and its reason for changing. It compares short trials, retains a strategy when improvements repeat, and reassesses after teleports, mine block changes or verified size changes. Pause & Alert and normal mining boundaries remain in effect. Turn it off to use the fixed adaptive sweep. This requires client mod **0.4.4** and a Minecraft restart.

The displayed scan BPS measures local successful block interactions over completed active windows. It excludes paused time and does not count the server scoreboard bonus from Nuke effects. It is not a server-confirmed throughput guarantee. Brief trials can reduce output, and no strategy is guaranteed best in every situation. Learning stays in memory for the current Minecraft session; it is not uploaded.

## Options

| Option | Purpose |
| --- | --- |
| Fast adaptive sweep | Continuously scan for reachable blocks while mining |
| Auto-optimize scan | Compare short mining trials and select a scan strategy for the observed environment |
| Run in background | Continue the active bot when Minecraft loses focus; menus still pause it |
| Auto teleport recovery | Send your mine command when progress stalls, with a cooldown between retries |
| Reset at low BPS | Request `/mine reset`, then return; minimum 12 seconds between reset requests |
| Reset every 45 seconds | Separate periodic reset timer; enabled by default, requires Auto teleport recovery, waits through menus/alerts |
| Upgrade Best every 30 minutes | Open the held pickaxe and click the server's Upgrade Best once; replaces individual enchant purchases |
| In-game Hub | Transparent panel opened with Right Shift; configurable in-game key and opacity |
| Flight mode | On: use server-granted flight and maintain height. Off: request ground movement. |
| Auto-detect mine size | Verify nearby mine boundaries, update Pos and save the route; turn off for a fixed manual region |
| Pause & Alert | Stop for nearby players or username mentions and wait for manual RESUME |
| Alert settings | Detection radius, sound/test sound, and optional one-time "what's up?" greeting |
| Sprint | Sprint while moving |
| Baritone navigation | Optional navigation using a separately installed compatible Baritone; disabled by default |

**Baritone is not required or bundled.** Leave its option off for the standard mining mode. If you enable it without installing a compatible version, turn it off or restart Minecraft after installing Baritone separately.

Pause & Alert requires the updated client mod and a Minecraft restart. Detection covers player entities present in the loaded client world; it does not identify staff roles or guarantee avoiding a ban. Player-shaped NPCs may also trigger it. Chat matching uses your account username, so a server nickname alone may not match. This build waits for manual RESUME after alerts; automatic logout/rejoin needs a separate server-specific flow.

## Troubleshooting

- **Not connected:** launch the selected Fabric 1.21 profile, enter a world, and confirm that the app points to that profile's game folder. Restart Minecraft after installing the mod.
- **It does not mine:** close chat and menus, select a pickaxe, and check both corners. Enable **Run in background** for Alt+Tab, or keep Minecraft focused if it is off. On another server, stop: compatibility may be missing.
- **It repeatedly teleports:** test the command, check the volume and entry point, and confirm that the mine contains reachable blocks. Disable recovery while investigating. It cannot fix every server-specific mechanic.
- **It leaves the mine:** stop and recheck the coordinates and return command. On Akuma, configure the current mine after joining Prison. Enable **Auto-detect mine size** for verified size changes, or update both corners manually. Ground mode and other layouts remain experimental.
- **BPS is lower than expected:** pickaxe speed, enchants, reach, mine contents, network latency and server limits affect the result. A server's `Blocks` / `Blocks Mined` counter can also include plugin effects, so it may differ from direct client block breaks.
- **Hotkey unavailable:** select another key or use START / STOP.

For an issue report, include the app version, Minecraft version, server, relevant settings and what happened. Remove usernames, private server addresses and other personal information from logs before sharing them. Do not post account tokens or Launcher files.

## Data and removal

Settings are stored locally at `%LOCALAPPDATA%\mimiminer\profile.json`; learned entry points are stored in the adjacent `entry-memory` folder. The client mod writes local telemetry under the selected game folder's `mam_telemetry` directory, which can include server addresses, coordinates, held-item information, your username, nearby player names/IDs/distances and name-mention event counters. Full chat text is not written by this feature. The app does not upload this telemetry to the publisher. If you enable the greeting, it sends that message to your connected server. Automatic setup makes network requests to obtain profile dependencies.

To remove the app, stop mining, close Minecraft and delete the extracted app folder. To remove the mod from an existing profile, remove `mimiminer-fabric-1.21.jar` from that profile's `mods` folder. Do not remove shared Fabric dependencies if other mods need them. You may also remove the dedicated **mimiminer 1.21** Launcher profile and instance, and the local settings folder if you no longer need your settings. Back up worlds and settings before deleting a game instance.

## Credits and licenses

Shout-out to **[Fxdedglory / Minecraft-Auto-Miner](https://github.com/Fxdedglory/Minecraft-Auto-Miner)** for the original inspiration and early experimentation, and to **[cabaletta / Baritone](https://github.com/cabaletta/baritone)** and its contributors for their work on Minecraft automation and navigation. These acknowledgments do not imply endorsement or permission to reuse their code.

This publication contains release documentation and a prebuilt app; application source and private development history are not published. The original Minecraft-Auto-Miner implementation and Baritone binaries are not distributed in this package. Mimi is a new robot mascot generated for this release without reference images; the previously supplied third-party logo is not included.

See **[LICENSE.txt](LICENSE.txt)** for the app's freeware terms and **[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)** for bundled component licenses. You can also read notices in the app under **Settings → About & licenses**. Third-party license rights are unaffected by the app's freeware terms.

Read the **[policy review](POLICY_REVIEW.md)** for the limits of the pre-publication review. Hobby use and free distribution do not remove copyright or platform-policy requirements.
