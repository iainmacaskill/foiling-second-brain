# Deploying this site

This is a [Quartz](https://quartz.jzhao.xyz/) v4 static site built from the content in
`~/Claude/Projects/Foiling Second Brain/Wiki/` (Entities, Concepts, Summaries copied into
`content/`). It's currently previewed locally only.

## Local preview

From this folder, on Node 22 (via nvm):

```bash
export NVM_DIR=$HOME/.nvm; . $NVM_DIR/nvm.sh; nvm use 22
npx quartz build --serve --port 8080
```

Or ask Claude Code to run the `foiling-second-brain-site` launch config.

## Going live on GitHub Pages (free)

1. Create a new **public** GitHub repo for this (e.g. `foiling-second-brain`):
   ```bash
   cd "/Users/iainmacaskill/Claude/Projects/Foiling Second Brain Site"
   gh repo create foiling-second-brain --public --source=. --remote=origin
   ```
2. Update `quartz.config.ts` → `baseUrl` to your real domain or
   `<username>.github.io/foiling-second-brain`.
3. Push:
   ```bash
   git add -A && git commit -m "Foiling second brain site"
   git push -u origin main
   ```
4. In the repo settings → Pages, or via Quartz's built-in GitHub Action
   (`npx quartz create` offers to add one, or see
   [quartz.jzhao.xyz/hosting](https://quartz.jzhao.xyz/hosting) for the
   `.github/workflows/deploy.yml` to drop in) — enable Pages, source = GitHub Actions.
5. Optional: point a subdomain (e.g. `foiling.iainmacaskill.co.uk`) at it via CNAME,
   same pattern as the main portfolio site.

## Refreshing content later

Re-run the copy from the vault whenever the Foiling Second Brain vault gets more
episodes ingested:

```bash
SRC="/Users/iainmacaskill/Claude/Projects/Foiling Second Brain/Wiki"
DST="/Users/iainmacaskill/Claude/Projects/Foiling Second Brain Site/content"
rm -rf "$DST/Entities" "$DST/Concepts" "$DST/Summaries"
cp -R "$SRC/Entities" "$DST/Entities"
cp -R "$SRC/Concepts" "$DST/Concepts"
cp -R "$SRC/Summaries" "$DST/Summaries"
```

Then rebuild/redeploy.
