# CastleMiner Z VR updates

CastleMiner Z VR mod by ItssnotTristan.

Original CastleMiner Z by DigitalDNA Games. The mod's source is maintained privately.

## Current update

[v0.38: Item editor and RPG support-hand update](https://github.com/itssnotTristan/CastleMinerZVR-Updates/releases/tag/v0.38) is available for existing installations.

- APK: `CastleMinerZVR-Quest2-v0.38-PublicUpdate.apk`
- Package: `org.codex.castleminerzvr`
- Version name: `0.38-item-editor-support-candidate`
- Android version code: `39`
- Download size: `10813439` bytes
- SHA-256: `24db256b2f015af470938bdf286d741257b30a9bde7c026a459ac3893a407abd`

The release adds separate Size, Position and Rotation pages for the held-item editor; RPG left-support-hand position and rotation editing with saved settings and export; a clickable Username button at bottom left; and Options in the Username button's former menu position. See the release notes for details and validation limits.

## Installation requirements

This public APK omits original game assets. It is an update for an existing CastleMiner Z VR installation with the required game content already extracted, not a fresh-install package. Players need their own legally obtained original game content.

**Do not uninstall the existing game or clear its storage.** Back up important worlds, then install the APK as an in-place update. The public APK's signing certificate matches the audited v0.37 APK.

**In-game update blocker in v0.37/v0.38:** these published builds can report “Update compatibility checker is unavailable” because their Java/native loader does not bind the checker correctly. They cannot apply that loader repair through their own in-game checker. Once a corrected APK is built and verified, install it manually **in place with the same signing key**. Do not uninstall, clear app data or delete original assets.

**v0.39 is currently a source candidate only. No v0.39 public APK or feed has been published.** v0.38 remains the latest published release while the corrected build and device checks are pending.

**Still on v0.36?** That build also has the earlier original-asset semicolon-parser issue. It likewise needs a same-key, manual in-place corrected installation. v0.37/v0.38 include the semicolon fix but still have the separate loader defect above. Do not uninstall first.

Only the named APK in the release assets is installable. GitHub-generated source archives contain this public repository's documentation and metadata.

## In-game updates and testing status

The app includes a public-feed check, APK download and verification, and an Android-confirmed installation flow. The confirmed loader defect blocks native compatibility verification in the currently published v0.37/v0.38 builds. After a corrected APK is manually installed, the repaired end-to-end in-game flow still needs confirmation on a Quest; Android permission and installation prompts remain explicit player actions.

The submitted v0.38 APK passed signature and public-content checks, and host production feed/APK preflight and direct native checklist checks accepted it. Those checks did not exercise the failing Java-to-native runtime lookup. Native inspection confirmed the new editor/support-hand behavior.

The compatibility-checker failure was reported on a Quest. Full acceptance of visual alignment, menu interaction, settings persistence, existing-world preservation and end-to-end Android installation is still outstanding.

The [v0.37 release](https://github.com/itssnotTristan/CastleMinerZVR-Updates/releases/tag/v0.37) remains available unchanged.

## Update feed

The live feed is [`cmz-update.json`](https://raw.githubusercontent.com/itssnotTristan/CastleMinerZVR-Updates/main/cmz-update.json) on `main`. Its seven fields are `schemaVersion`, `packageName`, `versionCode`, `versionName`, `tag`, `apkAsset`, and `apkSha256`.

Each entry must match a published, non-draft, non-prerelease release and a nonempty APK in this repository. The exact public download size and SHA-256 must be verified without GitHub authentication before publishing the feed. The file under `examples/` is a non-live format example, not an available update.

## What belongs here

- Public version and release metadata
- Player-facing update notes
- Reviewed, approved public update APKs that omit original game assets
- Reviewed, approved asset-free patch files

Original CastleMiner Z game assets, complete private APKs, signing keys, credentials, personal worlds and private validation logs must not be published here. An asset-free patch ZIP alone does not satisfy the APK update-feed contract.
