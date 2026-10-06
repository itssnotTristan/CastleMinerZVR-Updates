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

**Already on the corrected v0.37?** Use the in-game update flow to download and verify v0.38, then approve Android's installation prompt.

**Still on v0.36? Manually sideload v0.38 once as an in-place update.** The v0.36 original-asset filename parser rejects semicolons in required filenames, blocking that version's in-game updater. The corrected parser is included in v0.37 and later. Do not uninstall first.

Only the named APK in the release assets is installable. GitHub-generated source archives contain this public repository's documentation and metadata.

## In-game updates and testing status

The app includes a public-feed check, APK download and verification, and an Android-confirmed installation flow. The corrected v0.37 can use this flow to update to v0.38, with the player approving Android installation.

The submitted v0.38 APK passed signature and public-content checks, and the actual v0.37 production feed/APK preflight and native checklist checks accepted it. Native inspection confirmed the new editor/support-hand behavior.

This exact APK still requires Quest testing. Visual alignment, menu interaction, settings persistence, existing-world preservation and end-to-end Android installation remain unverified on a Quest.

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
