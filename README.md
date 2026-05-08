# beznexx-social-assets

Public asset repository for BezNexx social media campaigns.

This repo acts as a **public CDN** for images and videos used in the `beznexx-social-ops` Instagram publishing pipeline. Because this repo is public, all assets committed here are accessible via raw GitHub URLs — which is required by the Meta/Instagram Graph API.

## Folder Structure

```
beznexx-social-assets/
  instagram/
    images/        # Static images (PNG, JPG) for Instagram posts
    carousels/     # Carousel slide images (numbered: slide-01.png, slide-02.png...)
    reels/         # Video files for Reels (MP4)
  linkedin/
    images/
  x/
    images/
```

## How to Add an Asset

1. Export your image/video from Canva (or wherever)
2. Rename it using the convention: `YYYY-MM-DD-short-slug.png`
   - Example: `2026-05-08-alpha-access-open.png`
3. Upload it to the correct folder (e.g. `instagram/images/`)
4. Commit directly to `main`

The raw GitHub URL will be:
```
https://raw.githubusercontent.com/tomaconcepts/beznexx-social-assets/main/instagram/images/YOUR-FILE.png
```

## Usage in beznexx-social-ops

In your approved post `.md` file, set `image_file` like this:

```yaml
image_file: instagram/images/2026-05-08-alpha-access-open.png
```

The `publish-instagram.yml` workflow will automatically build the full raw URL from this path.

## Rules

- Only **approved, brand-safe** assets belong here
- No internal documents, private data, or unreleased product screenshots
- This repo is **public** — everything committed is visible to anyone
- Keep filenames lowercase, hyphenated, no spaces
