# rustnet-bsd

FreeBSD builds for [RustNet](https://github.com/domcyrus/rustnet).

## Why a separate repo?

FreeBSD builds require the `vmactions/freebsd-vm` action which runs code in a VM. To isolate this from the main repository's secrets and release artifacts, builds are performed here.

## Releases

FreeBSD binaries are published as [releases](https://github.com/domcyrus/rustnet-bsd/releases) in this repository, matching the version tags from the main RustNet repo.

## Building locally

```bash
# On FreeBSD with rust and libpcap installed
cargo build --release --no-default-features
```
