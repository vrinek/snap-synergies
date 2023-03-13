## Prerequisites

Get the [Nix package manager](https://nixos.org/download.html) installed.

## Developing

### Pull in all dependencies

```bash
nix-shell -p nodePackages_latest.npm nodejs --run "npm update"
```

# Run a dev server

```bash
nix-shell -p mprocs --run mprocs
```

## TODO

- [x] visually differentiate deck cards from the rest
- [ ] visually differentiate relations between deck cards and others
- [x] add prettier (or other formatter) to the toolchain
- [ ] rename Counter component to something that makes sense
- [ ] rename the repo
- [ ] remove irrelevant header and footer
