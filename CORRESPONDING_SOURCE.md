# Watower corresponding source

This repository hosts release downloads. The app's source is available in the separately uploaded archives below. GitHub's automatic source downloads contain this hosting repository, not the app.

## Watower 1.4

Download [Watower-1.4-source.tar.gz](https://github.com/iacompa/watower-releases/releases/download/v1.4/Watower-1.4-source.tar.gz) and [SHA256SUMS.txt](https://github.com/iacompa/watower-releases/releases/download/v1.4/SHA256SUMS.txt) from the [1.4 release](https://github.com/iacompa/watower-releases/releases/tag/v1.4).

The archive contains the matching application, CLI, widget, locked dependency sources, complete licenses, notices, and executed build/signing controls.
The application source is commit `4b09f1a95852eeb62c9ac98238322fbf6a2d8020`, tree `d0ca2082ac820ae77dbdb7259710576c9565d9fe`.
The source archive is 196,405,159 bytes with SHA-256 `61eb147b876c8a5c8e401eb9bf8face8533622c1ec6806290011f76ac605424c`.
Read `SOURCE-REBUILD.md` and `release/v1.4/production12/CORRESPONDING_SOURCE.md` inside the archive.
`SOURCE-MANIFEST.json` records the exact production source revision, tree, and every included file hash.
Apple signing credentials are unnecessary to modify or compile the program.

### Companion instructions for metadata-only packaging recovery

This document is the separate `CORRESPONDING_SOURCE.md` release asset, supplied beside the source archive. The additional recovery instructions below are not claimed to be inside the frozen archive identified above. Its revision, tree, bytes, and SHA-256 remain unchanged. All used project programs, including the unchanged compiler-free signer, remain in that archive. PlistBuddy is a general-purpose macOS system utility.

The received production artifact compiled the source identified above, but its producer refused final acceptance because the app declared `LSMinimumSystemVersion` as `10.13` instead of `14.0`. The raw app already had the production identifier, URL scheme, and build142. Its short version was `1.4.0`; the widget already declared public1.4/build142 and minimum14.0. This is a separate metadata-only recovery, not a passing producer run or a test-app relabeling.

Preserve the received archives, failed outcome, raw app/widget, compiler evidence, and original operation receipts. The producer's missing final stage/source snapshots, final vendor/compiler rechecks, final generated-widget state, final resource/time sample, and late API inventory remain unavailable historical evidence. Local recovery must not mark those checks as passed or invent a producer `stage.json`.

For the distributor recovery, Root first records a separately named, reviewed recovery-stage receipt. It binds the actual failed run/source/archive/outcome, compiler/profile evidence, complete current app/widget inventories, and every unavailable late check. It states `origin_producer_accepted: false`. Recovered-artifact acceptance is a separate decision from acceptance of that historical producer run.

The actual unchanged R2 copy action refused because standard ditto changed file birthtimes. Preserve that failed result and its complete comparison evidence. It is not a successful R2 copy checkpoint. Do not alter its receipt, strip security attributes, or reuse its failed output as an implicitly accepted copy.

**Manual-copy recovery procedure:** create a separate absent fresh output outside every retained input and failed output. Use standard metadata-preserving ditto for the app and embedded widget. The following paths are placeholders that Root must bind to the reviewed ordinary input and fresh output:

```sh
/usr/bin/ditto --rsrc --extattr --acl --qtn --preserveHFSCompression '/ABSOLUTE/RAW/Watower.app' '/ABSOLUTE/FRESH-COPY/Watower.app'
/usr/bin/ditto --rsrc --extattr --acl --qtn --preserveHFSCompression '/ABSOLUTE/RAW/WatowerWidgetExtension.appex' '/ABSOLUTE/FRESH-COPY/Watower.app/Contents/PlugIns/WatowerWidgetExtension.appex'
```

Compare the app copy before embedding and the widget copy before normalization. Record every new device/inode/ctime identity and every concrete file/directory birthtime difference as exact source/copy tuples. Require all content hashes, types, link counts, modes, ownership, modification times, flags, ACLs, and xattrs to match. Only the specifically inventoried creation-time tuples may be considered for Root's separate reviewed acknowledgment. Do not ignore all birthtimes or relax any content/security comparison.

Before the second ditto command, create only the absent `Contents/PlugIns` directory in the fresh app. Apply only the exact recorded owner-write changes needed for embedding, Info.plist editing, and later codesign. Use explicit existing paths from the reviewed inventory; do not use recursive chmod. Record the admitted widget additions and resulting parent-directory identity/time/link-count changes separately. All source inputs remain unchanged. This manual procedure uses general-purpose system tools and Root data checkpoints; it introduces no new project program.

After copying, manualcopy3 used these PlistBuddy commands on the reviewed fresh app and embedded widget:

```sh
/usr/libexec/PlistBuddy -c 'Set :CFBundleShortVersionString 1.4' '/ABSOLUTE/FRESH-COPY/Watower.app/Contents/Info.plist'
/usr/libexec/PlistBuddy -c 'Set :LSMinimumSystemVersion 14.0' '/ABSOLUTE/FRESH-COPY/Watower.app/Contents/Info.plist'
/usr/libexec/PlistBuddy -c 'Set :CFBundleShortVersionString 1.4' '/ABSOLUTE/FRESH-COPY/Watower.app/Contents/PlugIns/WatowerWidgetExtension.appex/Contents/Info.plist'
```

Replace the placeholder with the exact reviewed fresh-copy path. Do not run these commands on a raw input or an already signed app. Parse before/after plists. The app's only value changes are `CFBundleShortVersionString: 1.4.0 -> 1.4` and `LSMinimumSystemVersion: 10.13 -> 14.0`. Build142 remains unchanged. The widget short-version command writes `1.4` back as `1.4`: its parsed values and file hash remain unchanged, and the checkpoint records its exact modification-time writeback. The widget retains public1.4/build142/minimum14.0. Retain all concrete plist-file identity/time comparisons; do not introduce a general metadata exception or describe a semantic no-op as having no metadata effect.

Before signing, check the app and embedded widget: `LSMinimumSystemVersion` equals `14.0`, `CFBundleShortVersionString` equals `1.4`, and `CFBundleVersion` equals `142`. Require identifiers `com.iacompa.watower` and `com.iacompa.watower.widget`, the expected executable names, and the host's `watower` URL scheme. Root must explicitly check minimum14.0 because the unchanged signer does not enforce that field. Raising this plist floor restricts declared availability; it changes no Mach-O load command and proves no runtime behavior on macOS14.0.

Hash all three binaries before and after normalization. For this retained distributor artifact, the pre-sign values must remain:

| Binary in the fresh app | Unchanged SHA-256 |
| --- | --- |
| `Contents/MacOS/watower` | `3c1815c8d2437cf0dec222dee385002f0c1361565d57521599ff028ffb899ec5` |
| `Contents/MacOS/watower-cli` | `e45681a34ebb3fd42dad5a37b159da8299c042b799f384369d53178a5b03434d` |
| `Contents/PlugIns/WatowerWidgetExtension.appex/Contents/MacOS/WatowerWidgetExtension` | `e55b0704f03bf1103d43e3c4885a89853319478140c43079cf7e9d589e4eb835` |

Require every unrelated file/content/security property unchanged and capture a refreshed complete native app inventory. These are pre-sign comparisons; signing subsequently changes signed binary bytes. Modified source rebuilds use their own recorded pre/post packaging hashes. The table does not restrict modification rights or require byte-identical rebuilt binaries.

The normalization makes any earlier manual-copy `app_inventory` stale. Preserve that inventory and every failed adapter receipt. Create a separate Root-derived manual-copy checkpoint with:

1. Explicit Root-authored manual-copy provenance and the unchanged failed R2 copy receipt's path and SHA-256.
2. Actual manual ditto/embedding/mode-operation receipts, production source identity, exact fresh app path, and every specifically reviewed file/directory birthtime tuple.
3. `origin_producer_accepted: false`, the recovery-stage receipt binding, and the unavailable historical checks.
4. The exact normalization argv/tool identity, operation evidence, parsed before/after plist values, allowed key delta, and concrete file identity/time delta.
5. All three unchanged pre-sign binary hashes, unrelated-property comparison results, strict final metadata checks, and the refreshed full `app_inventory`.

Only after the distinct manual operation and its comparisons are accepted may its Root-derived record state `completed: true` and `scope: "copy"`, with the actual `production_sha`, `app`, and refreshed `app_inventory`. It must explicitly identify itself as a manual Root checkpoint, not the adapter's output or an accepted producer receipt. Populate the unchanged signer's `directory_birthtime_differences`/acknowledgment join with the specifically reviewed concrete tuple data, retaining file and directory kinds explicitly. The field name is not permission to omit file birthtime evidence. Root's sign gate binds this new checkpoint's path/hash and exact current inventory. It must not bind the failed R2 result as though it succeeded. This data recipe does not modify the signer or any frozen source program.

Keep all strict identity, code, license, entitlement, signature, deadline, source-preservation, Apple, and final-distribution checks. Do not sign until the distinct recovered-artifact decision and current checkpoint are accepted. This companion guide records the required procedure; it does not assert that recovery, signing, notarization, or distribution acceptance has occurred. Distributor Root gates are provenance controls, not prerequisites for exercising source modification or compilation rights.

## Historical Watower 1.3

Download [Watower-1.3.0-source.tar.gz](https://github.com/iacompa/watower-releases/releases/download/v1.3.0/Watower-1.3.0-source.tar.gz) and [SHA256SUMS.txt](https://github.com/iacompa/watower-releases/releases/download/v1.3.0/SHA256SUMS.txt) from the [1.3 release](https://github.com/iacompa/watower-releases/releases/tag/v1.3.0).

The archive supplies matching complete source for the shipped macOS arm64 application and CLI. It includes:

- The frozen application tree, including frontend, Rust, CLI, widgets, configuration, and build scripts.
- All 634 locked Rust registry packages and an offline Cargo source configuration.
- Exact frontend runtime package archives and preferred upstream JavaScript or TypeScript sources.
- Sources for the emitted Vite helper and Tailwind stylesheets.
- Preserved third-party notices, GPL text, and the first-party grant.
- `SOURCE-MANIFEST.json` and `DEPENDENCY-MANIFEST.json`, identifying the source revision, file hashes, and dependency provenance.

Verify the downloaded source archive against its line in `SHA256SUMS.txt`:

```sh
shasum -a 256 Watower-1.3.0-source.tar.gz
tar -xzf Watower-1.3.0-source.tar.gz
```

Inside the extracted archive, read `CORRESPONDING_SOURCE.md` and the detailed guide at `release/v1.3.0/CORRESPONDING_SOURCE.md`. Those files describe dependency provenance, source verification, build prerequisites, and rebuild commands.

Rebuilding requires macOS, Xcode tools and the platform SDK, Rust 1.96.0, Node.js, and pnpm 11.5.1. General-purpose unmodified compilers, SDKs, package managers, and build tools remain prerequisites. Fetching frontend build tools can require network access. The package does not claim a fully offline frontend tool installation.

Apple signing and notarization credentials are unnecessary to compile or modify the program. Signed or notarized artifacts are not guaranteed to rebuild byte for byte.

## Historical Watower 1.2

The [1.2 release](https://github.com/iacompa/watower-releases/releases/tag/v1.2.0) retains its original binaries, matching source archive and checksums unchanged. Its source archive contains the release-specific build and dependency guide.

## Historical Watower 1.1

The [original 1.1 release](https://github.com/iacompa/watower-releases/releases/tag/v1.1.0) retains its original DMG, ZIP, source archive, and checksum file unchanged.

The additional [Watower-1.1.0-GPL-source-supplement.tar.gz](https://github.com/iacompa/watower-releases/releases/download/v1.1.0/Watower-1.1.0-GPL-source-supplement.tar.gz) retains first-party source from revision `0c34e758f281dfb15b8a1c3e6db272b99ae2aa4e`. It adds matching dependency sources, notices, Cargo configuration, rebuild information, and the additional first-party GPLv3 grant.

Use [SHA256SUMS-GPL.txt](https://github.com/iacompa/watower-releases/releases/download/v1.1.0/SHA256SUMS-GPL.txt) to check the supplemental download. Its `GPL-SUPPLEMENT` directory contains the grant and complete GPL version 3 text. The original MIT `LICENSE` remains intact, and recipients retain the permissions supplied with the original MIT copies. See [LICENSING.md](LICENSING.md) for the standalone grant, license, notice, and checksum downloads.

## Scope and third-party terms

These packages supply source for the shipped macOS arm64 app and CLI. They do not claim Windows or Android build qualification or source completeness for inactive Android binary aggregates.

Third-party materials retain their original terms and per-file notices. Unmodified MPL-2.0 components retain their original notices and source. The detailed guide inside the source archive explains the included inactive target dependencies and the limits of the package.
