# smfc DEB repository

This repository hosts the DEB packages for [smfc](https://github.com/petersulyok/smfc) — a fan controller for SuperMicro servers.

## Compatible distributions

Requires Python ≥ 3.10. Supported on:

| Distribution    | Version                                              |
|-----------------|------------------------------------------------------|
| Debian          | 12 (Bookworm), 13 (Trixie), Sid                      |
| Ubuntu          | 22.04 LTS (Jammy), 24.04 LTS (Noble), 25.04 (Plucky) |
| Proxmox VE      | 8+                                                   |
| Linux Mint      | 21+                                                  |
| Pop!_OS         | 22.04+                                               |
| Raspberry Pi OS | Bookworm+                                            |

## Installation

```bash
sudo curl -fsSL https://petersulyok.github.io/smfc-deb/smfc.sources \
  -o /etc/apt/sources.list.d/smfc.sources
sudo apt update && sudo apt install smfc
```

## Updating

```bash
sudo apt update && sudo apt upgrade smfc
```

## Removing

```bash
sudo apt remove smfc
sudo rm /etc/apt/sources.list.d/smfc.sources
```