# Pre-publication policy and license review

Reviewed on **2026-10-11** for a free Windows release published from the **United States**. This is a limited technical and policy review, not a legal opinion, permission from a rights holder, or a guarantee against claims. State-specific questions and disputed rights require qualified legal advice.

## Copyright and provenance

The upstream [Minecraft-Auto-Miner repository](https://github.com/Fxdedglory/Minecraft-Auto-Miner) had no LICENSE file at commit `5d4674c` when reviewed. A public GitHub repository does not by itself authorize redistribution of a modified program. [GitHub's licensing guidance](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository) explains the default reservation of rights when no license is provided.

The release staging list contains newly added app modules and the new Fabric client mod, rather than the upstream app, archived controllers or Forge mod. Imports and staged assets were inspected, and source text was compared with the checked-out upstream commit; the identified shared sequences were ordinary syntax and library calls. This supports the narrow conclusion that no substantial copied implementation was identified in the inspected release. It is not proof of independent authorship or a complete infringement analysis. Modified legacy source and the clone's history are kept outside this publication.

The [U.S. Copyright Office's Circular 31](https://www.copyright.gov/circs/circ31.pdf) distinguishes ideas, methods and systems from their expression. Its [computer-program guidance](https://www.copyright.gov/circs/circ61.pdf) likewise distinguishes functional aspects from copyrightable expression. Its [FAQ](https://www.copyright.gov/help/faq/faq-fairuse.html) explains that changing somebody else's work or distributing it without profit does not automatically authorize a derivative work; fair use depends on the facts. Credit alone is not a license.

The previous third-party mascot was replaced by a new robot image generated specifically for this release without reference images. This removes the known unlicensed image from the release; it does not establish exclusive trademark or copyright rights in an AI-generated mascot. No trademark or patent clearance was performed.

## Minecraft and Microsoft

The [Minecraft EULA](https://www.minecraft.net/en-us/eula) allows original mods and tools within its conditions, while restricting redistribution of Minecraft itself or a modified game distribution. This package contains an original client mod and its dependencies; Minecraft game JARs, game assets and a Java runtime are not bundled. A licensed account and the official Launcher remain required.

The [Minecraft Usage Guidelines](https://www.minecraft.net/en-us/usage-guidelines) apply to free community sharing as well as paid activity. The release uses mimiminer as its primary name, includes the unofficial-product disclaimer, identifies the publisher and provides a contact email. It does not use Minecraft assets as its logo, charge for the mod or provide cash-out / NFT features.

Minecraft's EULA also references the [Microsoft Services Agreement](https://www.microsoft.com/en-us/servicesagreement) and [Xbox Community Standards](https://www.xbox.com/en-US/legal/community-standards). These address unauthorized use, cheating and software that gives an unfair advantage. The permission to create mods does not authorize every multiplayer use of this miner. Even if a server permits a particular automation mode, applicable platform policies still matter. Do not use it for cheating, bypassing access restrictions, ban evasion, or interference with other players.

## TalonMC and other servers

TalonMC Prison is the only configuration successfully tested locally so far. That is a compatibility observation, not approval by TalonMC. The official [website](https://www.talonmc.net/) and [store](https://store.talonmc.net/) were reviewed. Their linked purchase terms do not establish permission to auto-mine, and no accessible official rule expressly allowing this automation was verified. Current rules or explicit server permission must be checked before use. The release does not claim universal compatibility, a ban-free result or proven multi-hour reliability.

## GitHub

The [GitHub Acceptable Use Policies](https://docs.github.com/en/site-policy/acceptable-use-policies/github-acceptable-use-policies) require respect for intellectual property and prohibit unlawful activity, abuse, privacy violations and unauthorized access. The reviewed tool is presented for permitted personal automation; publication is not presented as permission to cheat or abuse another service. GitHub retains discretion to enforce its policies. No promise that GitHub will accept or retain the project is made.

## Dependencies

Notices for the runtime and bundled Fabric components are preserved in the release and this repository. Nuitka's runtime exception permits proprietary compiled output under its stated conditions; the compiler's license does not by itself require publishing this app's source. The obfuscation tool is not distributed. Baritone is not bundled and is installed separately if a user chooses its optional integration. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

## Practical conclusion

No general legal clearance is asserted. The release avoids the identified upstream-code and logo redistribution concerns, includes dependency notices, and documents platform and server restrictions. A free hobby release is still subject to those restrictions. A new monetization plan, copied component, game version or server policy requires a fresh review.
