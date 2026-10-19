# smfc DEB repository

This repository hosts the DEB packages for [smfc](https://github.com/petersulyok/smfc) — a fan controller for SuperMicro (home) servers.

## Compatible distributions

Requires Python ≥ 3.11. Supported on:

| Distribution    | Version                          |
|-----------------|----------------------------------|
| Debian          | 12 (Bookworm), 13 (Trixie), Sid  |
| Ubuntu          | 24.04 LTS (Noble) and newer      |
| Proxmox VE      | 8+                               |
| Linux Mint      | 22+                              |
| Pop!_OS         | 24.04+                           |

Ubuntu 22.04, Linux Mint 21 and Pop!_OS 22.04 are not supported, because their Python 3.10 is too old.

## Installation

a) `deb822` format (recommended), a single file with the embedded signing key (requires `apt` 2.4+):

```bash
sudo curl -fsSL https://petersulyok.github.io/smfc-deb/smfc.sources \
  -o /etc/apt/sources.list.d/smfc.sources
sudo apt update && sudo apt install smfc
```

b) One-line format with a separate key file:

```bash
curl -fsSL https://petersulyok.github.io/smfc-deb/smfc-repo.gpg \
  | sudo gpg --dearmor -o /etc/apt/keyrings/smfc-repo.gpg
echo "deb [arch=amd64,arm64 signed-by=/etc/apt/keyrings/smfc-repo.gpg] https://petersulyok.github.io/smfc-deb stable main" \
  | sudo tee /etc/apt/sources.list.d/smfc.list
sudo apt update && sudo apt install smfc
```

## Updating

```bash
sudo apt update && sudo apt upgrade smfc
```

## Removing

```bash
sudo apt remove smfc
sudo rm -f /etc/apt/sources.list.d/smfc.sources                              # a)
sudo rm -f /etc/apt/sources.list.d/smfc.list /etc/apt/keyrings/smfc-repo.gpg  # b)
```