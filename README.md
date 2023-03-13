## Developing

```bash
nix-shell -p nodePackages_latest.vercel nodePackages_latest.npm nodejs --run $SHELL

# pull in all dependencies
npm update

# run a dev server
vercel dev
```
## TODO

- [x] visually differentiate deck cards from the rest
- [ ] visually differentiate relations between deck cards and others
- [ ] add prettier (or other formatter) to the toolchain
- [ ] rename Counter component to something that makes sense
- [ ] rename the repo
