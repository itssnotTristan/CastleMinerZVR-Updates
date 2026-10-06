# CastleMiner Z VR updates

CastleMiner Z VR mod by ItssnotTristan.

Original CastleMiner Z by DigitalDNA Games. The mod's source is maintained privately.

## Current update

[v0.37: Item fit and menu update](https://github.com/itssnotTristan/CastleMinerZVR-Updates/releases/tag/v0.37) is available for existing installations.

- APK: `CastleMinerZVR-Quest2-v0.37-PublicUpdate.apk`
- Package: `org.codex.castleminerzvr`
- Version name: `0.37-item-fit-menu-candidate`
- Android version code: `38`
- Download size: `10797047` bytes
- SHA-256: `915b8d36d27f00f1223dc66e085dbbd18b99c6bf3f61aae402afb7905172ade3`

The release includes held-item fit controls and calibrated poses, SMG scale changes, RPG support-hand adjustments, PC-style menu/world pickers, credits and an original-asset filename parsing fix. See the release notes for details and validation limits.

## Installation requirements

This public APK omits original game assets. It is an update for an existing CastleMiner Z VR installation with the required game content already extracted, not a fresh-install package. Players need their own legally obtained original game content.

**Do not uninstall the existing game or clear its storage.** Back up important worlds, then install the APK as an in-place update. The public APK's signing certificate matches the checked v0.36 APK.

**Coming from v0.36? Manually sideload v0.37 once.** The v0.36 original-asset filename parser rejects semicolons in required filenames, blocking this first update through that version's in-game updater. The v0.37 build fixes the parser.

Only the named APK in the release assets is installable. GitHub-generated source archives contain this public repository's documentation and metadata.

## In-game updates and testing status

The app includes a public-feed check, APK download and verification, and an Android-confirmed installation flow. After the one-time manual v0.36-to-v0.37 update, future compatible releases can use this flow, with the player approving Android installation.

This exact APK and the end-to-end installation flow still require Quest testing. Host/static checks and APK signature, metadata and public-content checks were completed; Quest runtime behavior, visual alignment, existing-world preservation and on-headset installation remain unverified.

## Update feed

The live feed is [`cmz-update.json`](https://raw.githubusercontent.com/itssnotTristan/CastleMinerZVR-Updates/main/cmz-update.json) on `main`. Its seven fields are `schemaVersion`, `packageName`, `versionCode`, `versionName`, `tag`, `apkAsset`, and `apkSha256`.

Each entry must match a published, non-draft, non-prerelease release and a nonempty APK in this repository. The exact public download size and SHA-256 must be verified without GitHub authentication before publishing the feed. The file under `examples/` is a non-live format example, not an available update.

## What belongs here

- Public version and release metadata
- Player-facing update notes
- Reviewed, approved public update APKs that omit original game assets
- Reviewed, approved asset-free patch files

Original CastleMiner Z game assets, complete private APKs, signing keys, credentials, personal worlds and private validation logs must not be published here. An asset-free patch ZIP alone does not satisfy the APK update-feed contract.
