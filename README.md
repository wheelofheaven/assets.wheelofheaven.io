# Wheel of Heaven Assets CDN

Static asset hosting for the Wheel of Heaven project.

**URL:** https://assets.wheelofheaven.io

## Overview

This repository serves as the CDN for multimedia assets used across the Wheel of Heaven ecosystem. Hosted on Cloudflare Pages for optimal performance and CORS support.

## Structure

```
assets.wheelofheaven.io/
├── images/
│   ├── wiki/           # Wiki article images
│   ├── timeline/       # Timeline/World Ages images
│   ├── library/        # Library and book images
│   ├── og/             # Open Graph social images
│   ├── icons/          # Icons and logos
│   └── backgrounds/    # Background images
├── fonts/              # Web fonts
├── videos/             # Video files
├── audio/              # Audio files
├── downloads/          # Downloadable resources (PDFs, etc.)
├── _headers            # Cloudflare Pages headers (CORS, caching)
└── README.md
```

## Usage

Reference assets directly in your HTML/CSS:

```html
<!-- Image -->
<img src="https://assets.wheelofheaven.io/images/wiki/elohim-symbol.webp" alt="Elohim Symbol">

<!-- Open Graph -->
<meta property="og:image" content="https://assets.wheelofheaven.io/images/og/default.jpg">

<!-- Font -->
@font-face {
  font-family: 'CustomFont';
  src: url('https://assets.wheelofheaven.io/fonts/custom.woff2') format('woff2');
}
```

## CORS

All assets are served with permissive CORS headers:

```
Access-Control-Allow-Origin: *
Access-Control-Allow-Methods: GET, HEAD, OPTIONS
```

This allows assets to be loaded from:
- www.wheelofheaven.io
- api.wheelofheaven.io
- Any other domain

## Caching

| Asset Type | Cache Duration |
|------------|----------------|
| Images | 1 year (immutable) |
| Fonts | 1 year (immutable) |
| Videos | 24 hours |
| Audio | 24 hours |
| Downloads | 1 hour |

## Deployment

Hosted on Cloudflare Pages. Deployments trigger automatically on push to `main`.

### Setup (Cloudflare Pages)

1. Connect repository to Cloudflare Pages
2. Build command: (none - static files)
3. Build output directory: `/` (root)
4. Add custom domain: `assets.wheelofheaven.io`

## Image Guidelines

- Use WebP format for photos (with JPG fallback if needed)
- Use SVG for icons and logos
- Use PNG for images requiring transparency
- Optimize images before committing (target: < 500KB for large images)
- Name files descriptively: `world-age-aquarius-banner.webp`

## Consumers

- [www.wheelofheaven.io](https://www.wheelofheaven.io) - Main website
- [api.wheelofheaven.io](https://api.wheelofheaven.io) - JSON API

## License

CC0-1.0 (Public Domain) unless otherwise noted in specific files.
