# mimiminer 0.0.3 — 45-second reset & 30-minute Upgrade Best

October 14, 2026. Windows x64, Minecraft Java **1.21**, Fabric. Bundled client mod **0.4.6**. No Python installation is needed.

## New function

**Reset every 45 seconds** is enabled by default and has its own switch in desktop Settings and the transparent in-game Hub.

- Requests `/mine reset`, followed by your saved mine return command (`/mine go` on Akuma, `/mine teleport` where supported), then resumes the normal mining route.
- Runs independently of the low-BPS threshold. Turn the periodic switch off to keep only existing low-BPS/idle recovery.
- Requires **Auto teleport recovery**. The first timer starts when the miner is ready in the configured area, and waits 45 seconds.
- Every reset request restarts the interval, including low-BPS and idle resets. All reset modes share the existing minimum **12-second** cooldown.
- Defers while a normal menu is open, an owned pickaxe-upgrade cycle is active, a return teleport is pending, or Pause & Alert is latched. A due reset is considered when normal mining resumes. Alerts still require manual Resume.
- A late timer sends at most one reset; missed intervals are not replayed. The next interval is reserved before command delivery, so a timeout does not repeatedly send the same reset.
- Turning the periodic option off and back on starts a fresh interval.

These are requested server commands. The server may reject them; client delivery does not confirm a mine reset. Existing low-BPS/idle recovery can still reset earlier than 45 seconds.

## New upgrade mechanism

**Upgrade Best every 30 minutes** replaces the old individual enchant buyer and currency switches.

- Opt in through desktop Settings or the in-game Upgrades tab. The first check is after 30 minutes of ready mining; later checks are at least 30 minutes apart.
- Right-click the held pickaxe, inspect its owned menu, match the exact **Upgrade Best** label, click it once, close the menu and continue mining.
- The server chooses which upgrades and balances to use. The app no longer calculates prices, walks Tokens/Orbs/Gems tabs, or repeats purchases until MAXED.
- Missing, ambiguous and unavailable buttons are skipped. Menu opening is bounded; a stale item or unconfirmed click ends that cycle. No uncertain click is repeated.
- Menu pauses and Pause & Alert retain priority. Missed intervals do not trigger a burst of upgrade actions.

## Included features

Carries forward the transparent in-game Hub, configurable shortcut/opacity, native Minecraft font, minimal desktop UI with Monocraft, position capture, sidebar balances, adaptive scan optimization, background mining, mine-size detection and Pause & Alert.

Baritone is optional and is not bundled. Application source and personal settings are not published.

## Validation status

- **127 Python tests passed**, including clock-based checks for the 45-second reset and 30-minute Upgrade Best delay, one-click behavior, unavailable buttons, menu/alert deferral and unconfirmed-command limits.
- Protected Java checks and **18-class linkage verification passed**. The compiled EXE's setup/UI checks and package audit passed.
- **110-second live Akuma trial:** two periodic reset requests were **45.13 seconds apart**. Both return teleports were confirmed and mining resumed. There were no focus/menu pauses, with 87 sampled seconds in the background and 1,274 direct client breaks.
- The timer trial used a temporary region covering the mine's full depth. Low-BPS resets were disabled and idle recovery delayed to isolate the periodic timer. The user's original region and recovery options were restored afterward. This does not measure normal throughput or extended uptime.
- **Live Upgrade Best availability probe:** the exact button was recognized, but the server reported "No affordable enchant upgrade" for the current pickaxe progression. The bot closed the owned menu without a purchase and reserved the next 30-minute check. An actual server purchase and a real 30-minute waiting cycle remain unverified; their click/scheduling behavior is covered by automated clock tests.

The earlier [v0.0.2 release](https://github.com/anle0429/mimiminer/releases/tag/v0.0.2) had short local TalonMC/Akuma trials, including background mining, Tokens purchases and reset/return transitions. Those trials did not include this timer. Orb purchases, extended sessions and other server configurations remain unverified.

## How to update and try it

1. Stop mining and close Minecraft and the old mimiminer app.
2. Download **mimiminer.exe** for v0.0.3, or extract the Windows ZIP first.
3. Open **Settings → Minecraft setup**, choose your existing Fabric 1.21 game folder and click **INSTALL MOD**. Existing mine settings and custom keys are preserved.
4. Relaunch that profile, enter your mine and hold a pickaxe. Keep mimiminer running.
5. In desktop Settings, keep **Auto teleport recovery** enabled. Open the in-game Hub with Right Shift or your saved key; in its Settings, enable **Reset every 45 seconds** and confirm the correct return command. Click Start.

Check the included **SHA256SUMS.txt**. Only Minecraft Java 1.21 with Fabric on Windows x64 is supported by this build. TalonMC Prison and Akuma Prison have prior short tests; other layouts and upgrade menus are experimental. No universal compatibility, fixed BPS, multi-hour uptime or ban-free guarantee is provided.

Read README.md and POLICY_REVIEW.md. Use automation only where applicable game policies and server rules allow it. Testing does not mean server approval. Component notices, including Monocraft's SIL OFL 1.1 license, are included.

**NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**

Publisher: An Le (@anle0429). Contact: work.anle05@gmail.com.
