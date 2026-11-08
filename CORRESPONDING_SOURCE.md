# Watower corresponding source

This repository hosts release downloads. The app's source is available in the separately uploaded archives below. GitHub's automatic source downloads contain this hosting repository, not the app.

## Watower 1.3

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
