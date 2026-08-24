# The Just-In-Case Plan — Site

Single-page site for The Just-In-Case Plan, the $29 self-guided workbook from Legacy Architect RVA.

**Live site:** https://jicplan.legacyarchitectrva.com

## What this is

A static HTML page. No framework, no build step, no dependencies. Everything (styles, scripts, content) lives in `index.html`. Edit the file, commit, done.

## Structure

```
index.html                  The whole site, one page
assets/
  craig-headshot.jpg/.webp  Founder photo
  logo-lockup.png           Site logo
  share-card.jpg            Social preview image (og:image / twitter:image)
  favicon-16.png            Favicon set
  favicon-32.png
  favicon-48.png
  favicon-96.png
  favicon-180.png
  hero/
    jic-hero.mp4             Hero background video
    jic-hero-poster.jpg      Poster frame shown before the video loads
  pillars/
    pillar-digital.jpg/.webp     Seven pillar images, used in the tap-to-expand pillar grid
    pillar-emergency.jpg/.webp
    pillar-financial.jpg/.webp
    pillar-household.jpg/.webp
    pillar-vital.jpg/.webp
    pillar-legacy.jpg/.webp
    pillar-business.jpg/.webp
  samples/
    jic-cover.jpg/.webp             Sample workbook pages shown in "Real pages from the workbook"
    jic-contents.jpg/.webp
    jic-how-to-use-it.jpg/.webp
    jic-readiness-snapshot.jpg/.webp
    jic-digital-life.jpg/.webp
    jic-financial-assets.jpg/.webp
    jic-health-medical.jpg/.webp
    jic-next-step.jpg/.webp
```

## Updating the sample pages

Every sample needs a matching `.jpg` and `.webp` pair at the same filename (for example `jic-cover.jpg` and `jic-cover.webp`). The page loads both automatically through a `<picture>` tag, so swapping a page's content only means replacing those two files. You only need to touch `index.html` if you're adding a page, removing one, or renaming a file.

Two spots in `index.html` reference sample filenames:

- The hero section near the top, which always shows `jic-cover.jpg`/`.webp`
- The `<section id="samples">` block further down, which lists every sample page shown in the strip

## Updating the pillar images

The seven pillar images are built by a small script in `index.html` (search for `PILLARS =`). Each pillar's `img` value is a path with no extension, and the script appends `.jpg` and `.webp` itself. Keep both files present at that path for any pillar you touch.

## Deployment

This repo is meant to connect to a Cloudflare Pages project with Git integration. Once that's set up, any commit to `main` auto-deploys to `jicplan.legacyarchitectrva.com`.

Before this repo existed, the site was deployed through Cloudflare's Direct Upload, a separate, manual process with no version history and no way to edit a single file without re-uploading the whole folder. That's why it's moving here.

## Related

- Main site: [legacyarchitectrva.com](https://legacyarchitectrva.com) — [LegacyArchitectRVA-Main-Site](https://github.com/LegacyArchitectRVA/LegacyArchitectRVA-Main-Site)
- Client portal: portal.legacyarchitectrva.com
- Contact: Craig@LegacyArchitectRVA.com · (804) 866-1320
# JICPLAN-