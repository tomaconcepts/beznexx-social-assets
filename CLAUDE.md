# CLAUDE.md — beznexx-social-assets

Repo-local context for AI agents. For workspace-level orientation, see `../map.md` and `../source-of-truth.md`.

## Purpose

Public asset host. Serves Instagram media via GitHub Pages so the Meta API can fetch images at publish time. **Not** a source of truth for anything beyond delivery.

GitHub Pages base URL: `https://tomaconcepts.github.io/beznexx-social-assets/`

## How Files Get Here

Files are written by `beznexx-social-ops`'s `render-canva-asset.yml` workflow — Puppeteer renders HTML templates to JPEG, then commits to this repo via the `ASSETS_PAT` token. **Do not add or edit files by hand** — they will be overwritten or orphaned from the campaign that references them.

## Path Convention

```
instagram/YYYY/MM/{campaign-id}/{template-key}-v{version}.jpg                 # single image
instagram/YYYY/MM/{campaign-id}/{template-key}-slide-{n}-v{version}.jpg       # carousel slide
instagram/YYYY/MM/{campaign-id}/manifest.json                                  # render manifest
```

Legacy path (older posts): `instagram/images/{filename}.png`.

Supported aspect ratios at publish: **1:1** or **4:5**.

## Rules

- **Public.** Anything committed is world-readable. Never place anything sensitive here.
- **Live at publish time.** The Meta API fetches synchronously; broken or missing URLs fail the publish workflow.
- **Delivery only.** Never treat files here as source material — go to `../beznexx-social-ops/campaigns/instagram/` for the campaign record, or `../the-craddle/marketing/exports/` for the upstream brief.

## What This Repo Does Not Answer

- Why a post was published — see `../beznexx-social-ops/campaigns/instagram/published/`.
- What the campaign was about — see the source export in `../the-craddle/marketing/exports/`.
- Performance data — see `../beznexx-social-ops/analytics/`.
