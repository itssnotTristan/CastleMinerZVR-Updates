# CastleMiner Z VR v0.58.3 - PC rendering and Quest 3 support

Version code **63**, app version **0.58.3-quest3-pc-eye**, retains shared-v0.58
gameplay, network protocol 3, existing imports, saves and the original Quest
signer. The exact tested packages are published unchanged. The retained Candidate filenames and enclosed review-status notes preserve the verified hashes; this release page records publication.

## PC first-frame rendering

The intro could draw before terrain rendering initialized the shadow sampler.
That sampler defaulted to texture unit 0, already used by the diffuse sampler of
a different type. Desktop OpenGL rejected the first intro draw with error 1282.
All three PC shader programs now initialize distinct sampler units before any
draw. Driver error messages and separate intro/scene/presentation checkpoints
identify the failing operation and framebuffer/preset dimensions if another GL
error occurs. The log banner now records the actual app version.

The defect reproduced on the owner's RTX 4060 / NVIDIA 610.88 / OpenGL 4.5.
After correction, 216 production GPU intro/presentation cases passed: three eye
resolutions including the reported 2640x2880, four presets, three bloom levels,
both eye paths and three intro times. The visible intro contained 1,159,210 lit
pixels. All 16 retained scene diagnostics, four preset coverage checks and 120
storage-render frames also passed in fresh private profiles.

These are real GPU tests with ordinary eye-like textures, not a physical OpenXR
swapchain/headset test. The reporter's NVIDIA 621.01 / VirtualDesktopXR setup is
not available here and is not claimed accepted. No driver/runtime switch is
required by this repair.

## Quest 2 and Quest 3

The APK now explicitly declares **Quest 2 and Quest 3**. Optional Touch Plus
bindings are enabled only when the OpenXR runtime advertises the capability;
required legacy Touch bindings remain available and optional-profile rejection
does not abort startup. Runtime hardware/tracking properties are logged. Eye
targets remain bounded by runtime and GPU capabilities. Minimum SDK 29, target
SDK 34, GLES 3.2 and ARM64 requirements are unchanged. Quest 3S is not declared
or physically accepted by this release.

The GitHub build verifies the compiled APK device declaration, original signer,
sealed source and asset-free packaging, plus controller fallback and existing
validation/update/lifecycle regressions. No original game assets are packaged.
The legacy `Quest2` asset filenames now serve both declared models; use the
complete matching setup ZIP for a fresh installation.

The v0.58.2 ADB stderr/exit-status repair and v0.58.1 original-input/generated-HUD
checks remain in place. Source hashes establish supported original input identity;
the editable generated HUD receipt provides structural/corruption checks, not
original-pixel authenticity against a regenerated receipt. The executable check
does not establish Steam account entitlement.

## Install and update

- PC VR: use the complete `CastleMinerZ-PCVR-v0.58.3-SetupCandidate.zip`. Existing
  installations can use the matching code-only in-game update, which replaces
  runtime files while retaining imports and saves.
- Quest: extract `CastleMinerZVR-Quest2-v0.58.3-SetupCandidate.zip` on Windows and
  run **Setup Quest.cmd** with your own supported Steam version 1.9.9.8. Existing
  compatible imports can be retained by an in-place same-signer APK update.
- Close the app before setup. **Do not uninstall or clear app data.** A failed
  setup can retry; `-ImportDirectory` can reuse verified conversions. Old exact
  v0.58 imports remain accepted without a receipt migration.

No Quest is connected. Physical Quest 2/3 installation, upgrade/save preservation,
controller fit, gameplay, headset performance, another/reporting runtime or GPU,
and WAN acceptance remain untested. Installer doubles and host rollback checks
do not establish physical save preservation. Keep prior compatible packages and
backups available.

CastleMiner Z VR mod by ItssnotTristan; original game by DigitalDNA Games.
Unofficial mod. Coding/testing assistance: Codex (OpenAI). Third-party licenses
are included. Do not distribute imported original game content or private source.


## Package verification and downloads

Windows PowerShell 5.1.26100.9711 and PowerShell 7.6.5 each passed all nine
installer scenario groups, 21 native ADB argument/stdout/stderr checks, four
original-input checks and nine malformed/generated-HUD checks. Both full source
and extracted Quest installers passed real cold/warm ADB discovery in both
shells on an isolated server: eight cases per set, expected no-Quest stop. An
offline emulator/default server was preserved. No headset data was changed.

The code-only PC update passed validation, staging, bad-hash rejection, injected
copy failure/rollback, retry with simulated save/import preservation, and unsafe
archive rejection under both shells. These are host filesystem fixtures. The
native updater policy, 13 invalid release variants and original-file gate tests
also passed. A stale version59 test fixture was corrected to the compiled version;
production rejection was retained. The GitHub APK passed all 13 affected host
suites, Android compilation, actual compiled device declaration, asset exclusion,
16KB alignment and original-signer checks.

Use the **full setup ZIP** for a fresh install; the **CodeUpdate ZIP** is for the
PC in-game updater and the **PublicUpdate APK** is for existing compatible Quest
installs. Quest 2 and Quest 3 share the APK; legacy Quest2 filenames are retained.
No local APK build or new signing identity was used.

| File | Bytes | SHA-256 |
| --- | ---: | --- |
| `CastleMinerZ-PCVR-v0.58.3-SetupCandidate.zip` | 3410676 | `85099d6789a97f86a16aedb6f170ed9c72d4ce93060ceadef2de24f0bf05d19d` |
| `CastleMinerZVR-Quest2-v0.58.3-SetupCandidate.zip` | 4668977 | `eb1b1ddbd605b70af475d28e941f2cf088ab8f735532ed9b154a9a0e340c3bc5` |
| `CastleMinerZ-PCVR-v0.58.3-CodeUpdate.zip` | 3245810 | `e4b01421dcb2e5d63bd9423e564330ce0176d9d004b81047ec2b423cdc4da99f` |
| `CastleMinerZVR-Quest2-v0.58.3-PublicUpdate.apk` | 11731918 | `dc689ce80f2abbbca314b74f707de8717d172058142a587fcc63c8edc7e9f7bb` |

Quest APK original signer SHA-256: `90feab64d6f679f199c4e39a9407e25f17d038de58ff3a047dcecae01ae1e737`.
Public installer source/test PR: https://github.com/itssnotTristan/CastleMinerZ-VR-Mod/pull/6
