# rustnet-bsd

FreeBSD builds for [RustNet](https://github.com/domcyrus/rustnet), a cross-platform network monitoring tool built with Rust.

## Features

- Real-time monitoring of TCP, UDP, ICMP, and ARP connections
- Deep packet inspection (DPI) for HTTP, HTTPS/TLS, DNS, SSH, QUIC, and more
- Process identification via `sockstat`
- Service name resolution and connection state tracking
- Advanced filtering with vim/fzf-style search
- Terminal user interface built with ratatui

## Installation

Download the latest FreeBSD binary from the [releases](https://github.com/domcyrus/rustnet-bsd/releases) page:

```bash
tar xzf rustnet-*-x86_64-unknown-freebsd.tar.gz
sudo cp rustnet /usr/local/bin/
```

## Building Locally

```bash
# On FreeBSD with rust and libpcap installed
pkg install rust libpcap
cargo build --release --no-default-features
```

The `--no-default-features` flag is required because eBPF and Landlock are Linux-specific features.

## Usage

```bash
sudo rustnet              # Start network monitoring
sudo rustnet --help       # Show all options
sudo rustnet -i em0       # Monitor specific interface
```

Root or elevated privileges are required for packet capture on FreeBSD.

## Why a Separate Repo?

FreeBSD builds require the `vmactions/freebsd-vm` action which runs code in a VM. To isolate this from the main repository's secrets and release artifacts, builds are performed here.

## License

Apache License 2.0 - see the [LICENSE](https://github.com/domcyrus/rustnet/blob/main/LICENSE) in the main RustNet repository.
