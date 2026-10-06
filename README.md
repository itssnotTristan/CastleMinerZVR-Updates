# CastleMiner Z VR updates

CastleMiner Z VR mod by ItssnotTristan.

Original CastleMiner Z by DigitalDNA Games. The mod's source is maintained privately.

## Current update

[v0.39: Update loader and Exit repair](https://github.com/itssnotTristan/CastleMinerZVR-Updates/releases/tag/v0.39) is available for existing installations.

- APK: `CastleMinerZVR-Quest2-v0.39-PublicUpdate.apk`
- Package: `org.codex.castleminerzvr`
- Version name: `0.39-update-loader-exit-candidate`
- Android version code: `40`
- Download size: `10813439` bytes
- SHA-256: `d288893049581fafe9bb68ab6a3c72b5c38c052ca5dd93db8cab7676c3685ae2`

The release addresses the updater's Java/native validator-loading defect and the Exit lifecycle. Java explicitly loads the native validator before compatibility checks, mandatory checks remain enabled, and underlying loader errors are logged. Exit requests Android activity completion and processes lifecycle events before native teardown. See the release notes for validation limits.

## Installation requirements

This public APK omits original game assets. It is an update for an existing CastleMiner Z VR installation with the required game content already extracted, not a fresh-install package. Players need their own legally obtained original game content.

**Do not uninstall the existing game or clear its storage.** Back up important worlds, then install the APK as an in-place update. The public APK's signing certificate matches the audited earlier public APKs.

**Manual installation required from v0.37/v0.38:** these published builds can report “Update compatibility checker is unavailable” because their Java/native loader does not bind the checker correctly. They cannot apply the repair through their own in-game checker. Manually sideload the matching-signed v0.39 APK **over the existing installation** once. Do not uninstall, clear app data or delete original assets.

**v0.39 is now published for manual in-place installation.** This exact build and the repaired in-game update/Exit behavior still require Quest testing.

**Still on v0.36?** That build also has the earlier original-asset semicolon-parser issue. It likewise needs a matching-signed, manual in-place v0.39 installation. v0.37/v0.38 include the semicolon fix but still have the separate loader defect above. Do not uninstall first.

Only the named APK in the release assets is installable. GitHub-generated source archives contain this public repository's documentation and metadata.

## In-game updates and testing status

The app includes a public-feed check, APK download and verification, and an Android-confirmed installation flow. The confirmed loader defect blocks native compatibility verification in v0.37/v0.38. After v0.39 is manually installed, the repaired end-to-end in-game flow still needs confirmation on a Quest; Android permission and installation prompts remain explicit player actions.

The submitted v0.39 APK passed signature, identity, public-content and production preflight checks. APK inspection confirmed explicit Java native-library loading before validation and the native activity-finish/lifecycle-drain changes. Host tests cover Java/native binding and Android lifecycle handling.

The earlier compatibility-checker failure was reported on a Quest. This exact v0.39 APK has not been tested on a Quest. Repaired update checks, Android installation, Exit behavior, existing-world preservation and full runtime acceptance remain unverified.

Earlier [v0.38](https://github.com/itssnotTristan/CastleMinerZVR-Updates/releases/tag/v0.38) and [v0.37](https://github.com/itssnotTristan/CastleMinerZVR-Updates/releases/tag/v0.37) APKs remain available. Their release notices explain the manual repair path.

## Update feed

The live feed is [`cmz-update.json`](https://raw.githubusercontent.com/itssnotTristan/CastleMinerZVR-Updates/main/cmz-update.json) on `main`. Its seven fields are `schemaVersion`, `packageName`, `versionCode`, `versionName`, `tag`, `apkAsset`, and `apkSha256`.

Each entry must match a published, non-draft, non-prerelease release and a nonempty APK in this repository. The exact public download size and SHA-256 must be verified without GitHub authentication before publishing the feed. The file under `examples/` is a non-live format example, not an available update.

## What belongs here

- Public version and release metadata
- Player-facing update notes
- Reviewed, approved public update APKs that omit original game assets
- Reviewed, approved asset-free patch files

Original CastleMiner Z game assets, complete private APKs, signing keys, credentials, personal worlds and private validation logs must not be published here. An asset-free patch ZIP alone does not satisfy the APK update-feed contract.
