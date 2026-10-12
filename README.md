<p align="center"><img src="assets/mimi.png" alt="Mimi, the mimiminer mascot" width="144"></p>

# mimiminer 0.0.1
I coded this with the help of Codex just because I'm bored during a hackathon and has too much quota.

I just realized they don't allow to automine in this server tho, use it as ur own risk.
A small Windows desktop app for mining inside a selected block volume in Minecraft Java Edition.

**NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**

Publisher: **An Le ([anle0429](https://github.com/anle0429))**. Product and rights inquiries: **[work.anle05@gmail.com](mailto:work.anle05@gmail.com)**. The publisher is responsible for this app. It is not affiliated with TalonMC or the projects credited below.

## Compatibility — please read first

**This release works only with certain server configurations. TalonMC Prison is the only configuration we have successfully tested so far. It is not a universal auto-miner.**

| Requirement / server | Status |
| --- | --- |
| Windows x64 | Required |
| Minecraft Java **1.21** with Fabric | Required; automatic setup is available |
| TalonMC Prison | Successful local testing; server updates, pickaxes and mine layouts may change results |
| Other servers | Unsupported / experimental; no compatibility promise |
| Akuma | Known unresolved behavior: the bot can leave the mine, become idle and teleport back |
| Other Minecraft versions, Bedrock, Forge or NeoForge | Not supported by 0.0.1 |

Successful testing on TalonMC **does not mean TalonMC permits or endorses this app**. We have not verified an official TalonMC rule allowing auto-mining. Check current server rules and obtain permission before using automation. Applicable Minecraft, Microsoft and Xbox policies also apply; server permission does not override them. Automation that creates an unfair advantage may violate those policies. There is no ban-free guarantee, fixed BPS promise or verified many-hour uptime guarantee.

## Download

Open **[Releases](https://github.com/anle0429/mimiminer/releases)** and download **mimiminer.exe** for **v0.0.1**. Open it to get started. The executable includes its license notices under **About & licenses**. A Windows ZIP is also available if you want the app, guide and notices together; extract it before opening the app. Keep notices with any package you share.

The app includes its own runtime, so you do not need to install Python. You still need a licensed Minecraft Java account, the Minecraft Launcher and internet access for first-time setup. This release is unsigned; check the release SHA-256 before running a downloaded copy. Do not disable security protection to run it.

## First-time setup

1. Install the official Minecraft Launcher and sign in with your Minecraft Java account. Run Java Edition once, then close the game and Launcher.
2. Open **mimiminer.exe**. Click **Minecraft • Choose profile / Install mod**.
3. Click **AUTOMATIC SETUP • MINECRAFT 1.21 + MOD**, then wait for setup to finish. If you already use Fabric 1.21, select that profile's game folder and click **INSTALL MOD** instead.
4. Open the Launcher and select **mimiminer 1.21**, or the Fabric 1.21 profile you chose. Launch the game.
5. Enter a mine where you are allowed to use automation and select a suitable pickaxe in your hotbar.

Minecraft itself is downloaded through the Launcher. This package does not include Minecraft game files or Microsoft account credentials. Sign in only through the official Launcher; mimiminer does not ask for your password.

## Set your mine and start

1. Choose **two opposite corners of the entire block volume**, including its depth. For example, Pos 1 `100, 70, 100` and Pos 2 `120, 40, 120` describe an inclusive rectangular volume.
2. Enter each corner's **X, Y, Z** values. Alternatively, stand at a corner and click **Use my position** beside that Pos. This captures the block coordinate where you are standing; adjust it manually if the mine's corner block is below you or farther down. F3 can help you check coordinates.
3. Set **Mine command** to the return command your server accepts, such as `/mine teleport`. Test the command yourself first. Commands vary by server.
4. Enable **Fast adaptive sweep**. Enable **Auto teleport recovery** if you want to return when mining stops making progress. Enable **Maintain flight height** only if flight is available and allowed on your server.
5. Click **START**, return to Minecraft, and close menus before the countdown finishes.
6. Press **F8** to turn mining on or off. Click the **Toggle key** button to choose a different key. You can also click **STOP**.

Stop before changing the corners. Opening a menu or switching away from Minecraft pauses mining inputs. Keep Minecraft focused while the bot runs.

The mine command can return you to a point outside the selected volume. The app remembers observed entry points for each server and mine configuration; it does not expand the selected mining volume to include that point. A new server or layout may still need fresh configuration.

## Options

| Option | Purpose |
| --- | --- |
| Fast adaptive sweep | Continuously scan for reachable blocks while mining |
| Auto teleport recovery | Send your mine command when progress stalls, with a cooldown between retries |
| Maintain flight height | Use available flight; does not grant flight permission |
| Sprint | Sprint while moving |
| Baritone navigation | Optional navigation using a separately installed compatible Baritone; disabled by default |

**Baritone is not required or bundled.** Leave its option off for the standard mining mode. If you enable it without installing a compatible version, turn it off or restart Minecraft after installing Baritone separately.

## Troubleshooting

- **Not connected:** launch the selected Fabric 1.21 profile, enter a world, and confirm that the app points to that profile's game folder. Restart Minecraft after installing the mod.
- **It does not mine:** close chat and menus, focus Minecraft, select a pickaxe, and check both corners. On another server, stop: compatibility may be missing.
- **It repeatedly teleports:** test the command, check the volume and entry point, and confirm that the mine contains reachable blocks. Disable recovery while investigating. It cannot fix every server-specific mechanic.
- **It leaves the mine:** stop immediately and recheck the coordinates. Other-server navigation is not verified; the known Akuma behavior is unresolved in this release.
- **BPS is lower than expected:** pickaxe speed, enchants, reach, mine contents, network latency and server limits affect the result. A server's `Blocks` / `Blocks Mined` counter can also include plugin effects, so it may differ from direct client block breaks.
- **Hotkey unavailable:** select another key or use START / STOP.

For an issue report, include the app version, Minecraft version, server, relevant settings and what happened. Remove usernames, private server addresses and other personal information from logs before sharing them. Do not post account tokens or Launcher files.

## Data and removal

Settings are stored locally at `%LOCALAPPDATA%\mimiminer\profile.json`; learned entry points are stored in the adjacent `entry-memory` folder. The client mod writes local telemetry under the selected game folder's `mam_telemetry` directory, which can include server addresses, coordinates and held-item information. The app does not upload this telemetry to the publisher. Automatic setup makes network requests to obtain profile dependencies.

To remove the app, stop mining, close Minecraft and delete the extracted app folder. To remove the mod from an existing profile, remove `mimiminer-fabric-1.21.jar` from that profile's `mods` folder. Do not remove shared Fabric dependencies if other mods need them. You may also remove the dedicated **mimiminer 1.21** Launcher profile and instance, and the local settings folder if you no longer need your settings. Back up worlds and settings before deleting a game instance.

## Credits and licenses

Shout-out to **[Fxdedglory / Minecraft-Auto-Miner](https://github.com/Fxdedglory/Minecraft-Auto-Miner)** for the original inspiration and early experimentation, and to **[cabaletta / Baritone](https://github.com/cabaletta/baritone)** and its contributors for their work on Minecraft automation and navigation. These acknowledgments do not imply endorsement or permission to reuse their code.

This publication contains release documentation and a prebuilt app; application source and private development history are not published. The original Minecraft-Auto-Miner implementation and Baritone binaries are not distributed in this package. Mimi is a new robot mascot generated for this release without reference images; the previously supplied third-party logo is not included.

See **[LICENSE.txt](LICENSE.txt)** for the app's freeware terms and **[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)** for bundled component licenses. You can also read notices in the app under **About & licenses**. Third-party license rights are unaffected by the app's freeware terms.

Read the **[policy review](POLICY_REVIEW.md)** for the limits of the pre-publication review. Hobby use and free distribution do not remove copyright or platform-policy requirements.
