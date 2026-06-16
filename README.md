# sparxpg-assets

Public asset host for **assets.sparxpg.com** (served by Vercel).

## How it works

- Everything inside `public/` is served read-only over HTTPS at the root of the domain.
  - `public/ken.png` → `https://assets.sparxpg.com/ken.png`
  - `public/reports/2026-q2.pdf` → `https://assets.sparxpg.com/reports/2026-q2.pdf`
- Push to `main` → Vercel auto-deploys → files go live.
- The public can **view/download** assets but cannot edit or delete them — the only way to change a file is a new commit.

## Adding assets

1. Drop files into `public/` (subfolders are fine and become URL paths).
2. `git add . && git commit -m "add <thing>" && git push`
3. Live within seconds.

## Notes

- URLs are public and cacheable/indexable — do not put anything sensitive here.
- Large/numerous files: prefer Vercel Blob or object storage instead of committing to Git.
- Caching + content-type headers are configured in `vercel.json`.
