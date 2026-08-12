# TIN Development — Client SOWs

Published to [sow.tin.info](https://sow.tin.info).

Each client gets a folder. Each SOW is date-stamped. `latest.html` always points to the most recent.

```
clients/
  canada-lighting-supplies/
    2026-08-12-transparent.html
    2026-08-12-protected.html
    latest.html → 2026-08-12-transparent.html
```

### For the billing system

Link to `https://sow.tin.info/clients/{client-name}/latest.html` — it always resolves to the newest version.

### To add a new SOW

```bash
# Copy the HTML into the client folder
cp ~/sow.html clients/{client-name}/{date}.html

# Update the latest symlink
ln -sf {date}.html clients/{client-name}/latest.html

# Commit and push
git add clients/{client-name}
git commit -m "sow({client-name}): add {date} SOW"
git push
```

Cloudflare Pages auto-deploys in ~30 seconds.
