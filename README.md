# Thre4dripper Tap

[![tests](https://github.com/Thre4dripper/homebrew-tap/actions/workflows/tests.yml/badge.svg)](https://github.com/Thre4dripper/homebrew-tap/actions/workflows/tests.yml)
[![license](https://img.shields.io/github/license/Thre4dripper/homebrew-tap)](LICENSE)

Official [Homebrew](https://brew.sh) tap for CLI tools built by [@Thre4dripper](https://github.com/Thre4dripper).

## Install

```sh
brew tap Thre4dripper/tap
brew install --cask tidefetch
```

Or in a single command, without tapping first:

```sh
brew install --cask Thre4dripper/tap/tidefetch
```

Or with a [`Brewfile`](https://docs.brew.sh/Brew-Bundle-and-Brewfile):

```ruby
tap "Thre4dripper/tap"
cask "tidefetch"
```

## Available packages

| Package | Type | Description | Source |
| --- | --- | --- | --- |
| [`tidefetch`](Casks/tidefetch.rb) | Cask | Terminal UI and self-hosted web UI for the aria2 download engine | [Thre4dripper/tidefetch](https://github.com/Thre4dripper/tidefetch) |

Every package ships prebuilt binaries for macOS and Linux, on both Intel and Apple Silicon / ARM.

## Upgrade

```sh
brew update
brew upgrade --cask tidefetch
```

## Uninstall

```sh
brew uninstall --cask tidefetch
brew untap Thre4dripper/tap   # optional, removes the tap itself
```

## Repository layout

```
Casks/      # cask definitions (prebuilt binaries)
Formula/    # formula definitions (built from source), added as needed
.github/    # CI workflows and automation
```

Cask and formula files carrying a `DO NOT EDIT` header are generated and pushed
automatically by [GoReleaser](https://goreleaser.com) when a new version of a
tool is released. Edit the tool's release configuration upstream instead of
changing those files by hand.

## Troubleshooting

**`Error: Cask 'x' is unavailable`** — refresh the tap metadata:

```sh
brew update --force
```

**macOS says the binary is damaged or from an unidentified developer** — the
casks already strip the `com.apple.quarantine` attribute during install. If the
warning persists, re-run the install after `xattr -dr com.apple.quarantine` on
the installed binary.

**Where to report bugs** — problems with a tool itself belong in that tool's own
repository (see the *Source* column above). Use this repository's
[issues](https://github.com/Thre4dripper/homebrew-tap/issues) only for
packaging problems: bad checksums, broken download URLs, missing dependencies,
or install failures.

## Documentation

`brew help`, `man brew`, or [Homebrew's documentation](https://docs.brew.sh).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

The packaging in this repository is released under the [MIT License](LICENSE).
Each packaged tool keeps the license of its own upstream project.
