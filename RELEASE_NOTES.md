# mimiminer 0.0.2 — In-game Hub, upgrades & recovery

Updated October 13, 2026. Windows x64, Minecraft Java **1.21**, Fabric, bundled client mod **0.4.5**. This updated build replaces the earlier v0.0.2 download. No Python installation is needed.

## New features

- **Transparent in-game Hub:** open with Right Shift by default; customize the shortcut and opacity. Mine, Settings and Upgrades tabs include position capture and persistent Start/Stop/Save/Resume controls. Uses Minecraft's current font. Mining continues while this panel is open; keep the EXE running as its local backend.
- **Minimal desktop Hub:** compact Mine view, side-by-side corners, state, client BPS and persistent Start/Stop. Advanced settings scroll separately. Uses the unmodified Monocraft font with its SIL OFL 1.1 license.
- **Player balances:** read sidebar Money, Tokens, Orbs/Ores, Gems and Credits. Supports K/M/B/T/Q suffixes and preserves abbreviated balance text. Rounded balances remain estimates.
- **Auto upgrade pickaxe:** opt in and select Tokens, Orbs and/or Gems separately. Opens the held pickaxe normally, reads recognized English tooltips, skips locked/MAXED/unknown/unaffordable items, and buys single or explicitly advertised bulk upgrades. Observed level progress is required before another purchase. Cached tooltips get one refresh; uncertain purchases are skipped. Bounded cycles return to mining. Auto upgrade is off until enabled.
- **Low-BPS reset:** request `/mine reset` followed by your configured return command, including `/mine go` on Akuma or `/mine teleport` where supported. At least **12 seconds** between reset requests. Warm-up and persistence checks exclude menu pauses and brief interruptions. Idle recovery can also request a reset.
- **Adaptive scan optimization:** compare short active windows, retain repeatedly better strategies and reassess after mine/environment changes. Shows the measured strategy, direct-client BPS and reason. Can be disabled for fixed adaptive scanning.
- **Pause & Alert:** configurable 0.5–64 block radius, nearby-player/name-mention sound alerts and manual Resume. Interrupts upgrade automation too. Optional "what's up?" greeting is limited to once per Start.

## Fixes

- Background mining keeps its active connection through mine inspection, reset/return commands and opening/closing owned pickaxe menus. Mining waits briefly for fresh telemetry after a shop closes.
- Akuma's currency tabs can replace the menu title. Guarded Tokens/Orbs navigation now preserves ownership through that expected transition; unrelated menu changes release ownership.
- Ground movement can scan side blocks from a protected floor. Flight mode off disables observed flight after a teleport.
- Refresh observed block types after rank changes. Optional mine-size detection updates Pos and the route only when nearby boundaries can be verified; inconclusive scans preserve the existing region.
- In-game BPS is formatted to one decimal place. Saving unrelated overlay settings preserves automatically updated corners.

Other menus, loading overlays, disconnections and expired connections still stop mining inputs. Background mode does not grab the desktop cursor or send mining keys to other apps. Baritone is optional and is not bundled.

## Validation and limits

- **120 Python tests passed**, including alerts, manual resume, upgrade confirmations, currency navigation and reset cooldowns.
- Protected Java statistics, scan/optimizer/control tests and **18-class bytecode linkage checks passed**. Compiled EXE setup/UI checks and packaging audit passed.
- **90-second Akuma trial:** 949 direct client breaks, including 58 sampled seconds without window focus. Two upgrade-check cycles completed; the second opened/switched/closed the shop in the background and mining resumed. Five reset requests and return teleports completed without focus/menu pauses. The shortest reset-request interval was **12.03 seconds**.
- Completed active scan windows measured **19.5–19.8 client BPS**. That is not the average over the full trial and does not include scoreboard bonuses from Nuke effects. The threshold was temporarily raised to exercise recovery, then restored to 5 BPS.
- Earlier Tokens purchases were confirmed: Token Miner, XP Finder and Jackhammer 500→700; Key Finder 400→600, with MAXED checked after reopening the menu. Current Orb enchants were level-locked, so **Orb purchases remain unverified**. Tokens and Orbs were selected in the combined trial; Gems were off.

TalonMC Prison and short Akuma Prison trials have been tested. Other servers and upgrade menus are experimental. A live improvement over fixed scanning, extended ground operation through every rank change, and multi-hour uptime have not been established. Server commands may be rejected; client delivery does not confirm a server reset. No universal compatibility, fixed speed or ban-free guarantee is provided.

## How to update

1. Stop mining and close Minecraft and the old mimiminer app.
2. Download and open the updated **mimiminer.exe**, or extract the Windows ZIP first.
3. Open **Settings → Minecraft setup**, select your current Fabric 1.21 game folder and click **INSTALL MOD**. Existing settings and custom keys are kept.
4. Relaunch that profile, enter your mine and hold a pickaxe. Keep the EXE open, then open the in-game Hub with Right Shift or your saved custom key. **F8** remains the default mining toggle.
5. Check both mine corners and the return command. Enable your desired upgrades and low-BPS recovery options, then click Start.

Check the included SHA256SUMS.txt. Current EXE SHA-256:

`19b79e36aeb81c29204f68a77b6e4a270c8ef04f47f25834bd222059f795e271`

This package includes release documentation, the compiled app and component notices. Application source, private development history and personal settings are not published. Read README.md and POLICY_REVIEW.md; use automation only where applicable game policies and server rules allow it. Testing does not mean server approval.

**NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**

Publisher: An Le (@anle0429). Contact: work.anle05@gmail.com.
