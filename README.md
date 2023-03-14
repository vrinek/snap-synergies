## Prerequisites

Get the [Nix package manager](https://nixos.org/download.html) installed.

Enable flakes and the nix command [experimental features](https://github.com/Xe/site/blob/cedbd439f156cbc89de739a1d45d03a2ae8315f8/blog/nix-flakes-1-2022-02-21.markdown?plain=1#L81-L86).

## Developing

### Pull in all dependencies

```bash
nix develop
# all system dependencies will be installed

npm install
# all node packages will be installed
```

# Run a dev server

```bash
# when in `nix develop`
mprocs
```

## TODO

- [x] visually differentiate deck cards from the rest
- [ ] visually differentiate relations between deck cards and others
- [x] add prettier (or other formatter) to the toolchain
- [ ] rename Counter component to something that makes sense
- [ ] rename the repo
- [x] remove irrelevant header and footer
- [ ] remove irrelevant header links
