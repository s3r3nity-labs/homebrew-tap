# s3r3nity-labs Homebrew tap

Homebrew casks for the command-line tools of [s3r3nity-labs](https://github.com/s3r3nity-labs).
They are Linux-only and work wherever [Homebrew on Linux](https://docs.brew.sh/Homebrew-on-Linux)
runs, e.g. Bazzite, Fedora Atomic or any other distribution.

## Install

```shell
brew install s3r3nity-labs/tap/<name>
```

This adds the tap the first time. Updates come with everything else:

```shell
brew update
brew upgrade
```

The casks need a current Homebrew; run `brew update` first if an install fails with
"definition is invalid".

## Tools

| Name | Description |
| ---- | ----------- |
| [linux-home-cloud-storage-sync](https://github.com/s3r3nity-labs/linux-home-cloud-storage-sync) | Keep a cloud-storage home folder linked into your Linux home |

```shell
brew install s3r3nity-labs/tap/linux-home-cloud-storage-sync
```

## How the casks get here

Don't edit the files in `Casks/` by hand. Each tool's release workflow runs
[GoReleaser](https://goreleaser.com), which writes its cask (version, download URLs,
checksums) and commits it here as "s3r3nity-labs release". It uses a fine-grained token
with *Contents: read and write* on this repository only, stored as the secret
`HOMEBREW_TAP_GITHUB_TOKEN` in the tool's repository.

To add a tool: put a `homebrew_casks` section with `repository: s3r3nity-labs/homebrew-tap`
into its `.goreleaser.yaml` (see linux-home-cloud-storage-sync's), give its repository
the same secret (the token's repository access stays this tap), and add a row to the
table above.

## Uninstall

```shell
brew uninstall <name>
brew untap s3r3nity-labs/tap
```
