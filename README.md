## Developing

```bash
nix-shell -p nodePackages_latest.vercel yarn --run $SHELL

# pull in all dependencies
yarn

# run a dev server
vercel dev
```
