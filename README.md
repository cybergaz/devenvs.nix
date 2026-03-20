# nix-devenv

Minimal, portable, self-contained development environment flakes for Nix and NixOS.

## Usage

Copy the relevant flake to your project root as `flake.nix`, then enter the environment:

```bash
nix develop
```

Or use [direnv](https://direnv.net/) for automatic shell activation:

```bash
echo "use flake" > .envrc
direnv allow
```

## Environments

### Flutter

| Flake | Targets |
|-------|---------|
| `minimal-android+web.flake.nix` | Android + Web |
| `android-only.flake.nix` | Android |
| `all-platforms+emulator.flake.nix` | Android, Web, Linux + emulator |

See [`flutter/README.md`](flutter/README.md) for setup notes and troubleshooting.
