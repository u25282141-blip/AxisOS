# Axis Package Manager (`axis`)

This directory contains the native AxisOS package manager and supporting assets.

## Contents

- `bin/axis`: Main package manager CLI (Python 3 script).
- `configs/axis.conf`: Example repository configuration file.
- `tools/repo-builder.py`: Helper script to build a `repo-index.json` from package artifacts.
- `examples/`: Sample `.axis` packages, package source trees, and test repo index/config files.

## Core Commands

From this repository, run the CLI directly:

```bash
python3 pkg-mgr/bin/axis <command>
```

Available commands:

- `update`: Synchronize package indices from configured repositories.
- `install <packages...>`: Install one or more packages with dependency resolution.
- `remove <packages...>`: Remove installed packages (`--force` supported).
- `list`: List installed packages.
- `search <query>`: Search available packages from the local index cache.
- `info <package>`: Show package metadata/details.
- `build <source_dir>`: Build a `.axis` package from a directory with `metadata.json` and `rootfs/`.

Useful global flags:

- `--root <path>`: Target root filesystem (defaults to `/`).
- `--config <path>`: Use a custom config file instead of `/etc/axis/axis.conf`.
- `--no-color`: Disable ANSI colors in output.

## Local Example Config

For local testing, you can point `--config` to:

- `pkg-mgr/examples/test-axis.conf`

This keeps tests isolated from a system-wide `/etc/axis/axis.conf`.
