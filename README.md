## Developing

```bash
nix-shell -p nodePackages_latest.vercel nodePackages_latest.npm nodejs --run $SHELL

# pull in all dependencies
npm update

# run a dev server
vercel dev
```
