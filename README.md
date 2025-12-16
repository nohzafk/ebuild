[![MacOS Build for GNU Emacs](https://github.com/RadioNoiseE/ebuild/actions/workflows/build.yml/badge.svg)](https://github.com/RadioNoiseE/ebuild/actions/workflows/build.yml)

This repository builds GNU Emacs 30.2 for macOS with static linking and
emacs-plus patches. Builds are triggered manually via workflow dispatch.

No package manager is used during the build process, as all external
dependencies are fetched from upstream and compiled from source. A
statically linked Emacs is produced (except the system components),
making link time optimization possible.

## Patches Applied

The following patches from [emacs-plus](https://github.com/d12frosted/homebrew-emacs-plus) are applied:

- **fix-window-role** - Fixes accessibility window role for better screen reader support
- **system-appearance** - Adds `ns-system-appearance-change-functions` hook for dark/light mode detection
- **round-undecorated-frame** - Enables rounded corners on undecorated frames

## Features

Emacs is built with:
- GNU MP Bignum Library
- GnuTLS
- Tree-sitter
- libxml2
- zlib
- Native Image API
- Dynamic modules support

> [!Note]
> Native compilation is not supported, since compiling libgccjit is
> considered too resource-intensive.
