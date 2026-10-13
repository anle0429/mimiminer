# mimiminer 0.0.2

Windows x64 desktop release for Minecraft Java 1.21 with Fabric. Download and open **mimiminer.exe**, or extract the optional Windows ZIP containing the app, guide and notices. No Python installation is needed.

- English interface, automatic profile setup and local settings.
- **Run in background**: keep mining when you Alt+Tab, with no desktop cursor grab or mining keys sent to other apps. Enabled by default; you can turn it off.
- Minecraft's automatic lost-focus pause is suppressed only while the active bot renews its connection. Manually opened menus, loading overlays and disconnections still stop inputs.
- Tick-based steering continues when background rendering slows. Existing foreground sweep behavior is preserved.
- Select two opposite corners manually or with **Use my position**.
- Adaptive mining sweep, optional idle teleport recovery and configurable toggle key.
- Refresh observed mine blocks after rank changes; use `/mine go` on Akuma.
- **Auto-detect mine size**: update and save Pos and the mining route when nearby mine boundaries can be verified. Turn it off to keep a manual region fixed. Inconclusive detection keeps the existing bounds.
- **Flight mode** off requests ground movement, including disabling observed flight after a teleport. Ground scanning can look for side blocks from a protected floor.
- New transparent Mimi robot mascot, publisher contact and bundled license notices.

**TalonMC Prison has been tested; Akuma Prison now has successful short local mining trials. Other configurations remain experimental.** Testing is not server approval. Use automation only where applicable game policies and server rules allow it. No ban-free, fixed-speed or multi-hour uptime guarantee is provided.

Validation: 81 automated tests passed. The previous Akuma background trial recorded 3,328 direct client breaks in three minutes and an increasing server counter, with Minecraft unfocused; that trial used flight. Automatic geometry recognition was checked against the live mine and automated cases. Complete live ground-only mining through rank changes was not validated before publication, so ground mode and automatic mine sizing remain experimental.

Read the README and POLICY_REVIEW.md before use. Check the SHA256SUMS.txt included with this release. The application source and personal settings are not included. Baritone is optional and is not bundled.

**Upgrade:** close Minecraft, install the updated mod from this app's setup window, then relaunch your Fabric 1.21 profile. The old 0.0.1 mod does not support background mode. Existing settings are kept.

**NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**

Publisher: An Le (@anle0429). Contact: work.anle05@gmail.com.
