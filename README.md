# CastleMiner Z VR updates

CastleMiner Z VR mod by ItssnotTristan.

Public update information for players. The mod's source is maintained privately.

## Current status

No installable update has been published here yet. Creating this repository or updating its metadata does not mean an APK is available or that a build has passed headset testing.

## What belongs here

- Public version and release metadata
- Player-facing update notes
- Explicitly reviewed, approved asset-free patch files

Original CastleMiner Z game assets, complete private APKs, signing keys, credentials, personal worlds, and private validation logs must not be published here. Players need their own legally obtained game content where required by the installation instructions.

An update entry must point to an actual approved release, with accurate compatibility and installation instructions. Until then, the feed must not advertise a downloadable version.

## Update feed

The application expects `cmz-update.json` on the `main` branch, with these seven fields: `schemaVersion`, `packageName`, `versionCode`, `versionName`, `tag`, `apkAsset`, and `apkSha256`.

The file under `examples/` is a non-live format example with a placeholder version and zero digest. It is not an available update. No root `cmz-update.json` is published until there is an approved real release.

The current app flow checks metadata and opens a matching GitHub release page in the headset browser after the player chooses it. It does not download or install APKs automatically. A live entry requires an uploaded, nonempty APK with a matching SHA-256 digest in a published, non-draft, non-prerelease release in this repository. An asset-free patch ZIP alone does not meet that checker contract. Any APK publication requires separate verification that it contains no original game assets or private material and falls within the owner's approved distribution scope.
