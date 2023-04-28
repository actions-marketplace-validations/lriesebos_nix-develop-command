# Nix develop command GitHub action

![GitHub Actions badge](https://github.com/lriesebos/nix-develop-command/workflows/nix-develop-command%20test/badge.svg)

This GitHub action is used to run commands in a Nix development shell (i.e. using a flake).

## Usage

This GitHub action does not install Nix,
use the [cachix/install-nix-action](https://github.com/marketplace/actions/install-nix) before using this action.
By default, this action assumes the `flake.nix` file is located in the current working directory.

```yaml
jobs:
  ubuntu:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: cachix/install-nix-action@v20
      - uses: lriesebos/nix-develop-command@v1
        with:
          command: "hello"
```

## Inputs

- `command`: The command to run (required)
- `devshell`: Name of the development shell (default: `default`)
- `options`: Additional options/arguments for nix develop
- `working-directory`: Working directory (default: `./`)
