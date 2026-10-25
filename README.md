# CastleMiner Z VR updates

CastleMiner Z VR mod by ItssnotTristan.

## v0.58.1 installer repair

[Download v0.58.1](https://github.com/itssnotTristan/CastleMinerZVR-Updates/releases/tag/v0.58.1)
for the matching PC setup ZIP, Quest setup ZIP and signed, asset-free Quest update
APK. [PC/Quest hub and installation guides](https://github.com/itssnotTristan/CastleMinerZ-VR-Mod).
The exact reviewed ZIPs retain `SetupCandidate` in their names; they were approved
and published unchanged. The release page supersedes their enclosed review-status
notes.

The repair addresses PowerShell 5.1 ADB argument binding, GPU-generated HUD
validation and the v0.58 APK's CRLF checksum-list/native-parser mismatch. It keeps
strict supported-original input hashes and deterministic-output hashes. The
generated HUD's statistics and editable checksum receipt are structural and
transfer-corruption checks, not cryptographic proof of original pixels or
resistance to a regenerated receipt.

Quest uses package `org.codex.castleminerzvr`, version code **62**, version name
`0.58.1-installer-hud`, and the original signer. PC runtime remains v0.58/code
**61** with installer revision 0.58.1. Both retain shared-v0.58 gameplay, protocol
3 and content fingerprint 15070507204261208425. The full-package compatibility
matrix references the current setup ZIP; the PC in-game feed remains on its
unchanged v0.58 code-only ZIP. Do not send a setup ZIP to the PC code updater.

Public files contain no original game assets, keys or saves. Use your own
supported Steam game version 1.9.9.8. The file-identity check does not verify
Steam account entitlement. Fresh Quest installs need the complete setup ZIP;
the APK alone cannot supply original content. Close the game before setup.
Use an in-place update: **do not uninstall or clear app data**. Existing exact
imports require no receipt migration. If v0.58 cannot start, manually install
the new verified APK in place or run the complete setup before playing.

Passed: fresh import/package checks, PowerShell 5.1/7 installer and rollback
scenarios, all 12 affected native/Java suites, desktop GPU diagnostics, and
signature/content/alignment/hash verification. The APK was built on GitHub.
Physical Quest installation/upgrade and save preservation, PCVR/Quest wearer
acceptance, the reporter's or a second GPU, live headset performance and
different-home/WAN play remain untested. Simulated installer tests do not prove
physical save preservation. Full original-game feature parity is not established.
See the release notes for exact hashes and scope.

## Earlier update notes

CastleMiner Z VR mod by ItssnotTristan.

Original CastleMiner Z by DigitalDNA Games. The mod's source is maintained privately.

## Historical v0.39 update

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


## Matching PC and Quest v0.58

[Downloads and release notes](https://github.com/itssnotTristan/CastleMinerZ-PCVR/releases/tag/v0.58-public-beta) include the PC drag-and-drop package and standalone Quest Setup ZIP. Quest players: extract the complete setup ZIP, open START-HERE.html, then run Setup Quest.cmd on the Windows PC containing your Steam installation. [Read the Quest installation manual](https://github.com/itssnotTristan/CastleMinerZ-PCVR/blob/main/QUEST-INSTALL.md). The APK alone omits original game content; setup imports and verifies your own files. Both platforms use shared-v0.58, version code 61. Physical v0.58 headset and different-home testing remain pending.
