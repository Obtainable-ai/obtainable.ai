# Obtainable.ai Website

A modern, SEO-optimized static website built with Astro and Tailwind CSS, featuring a cosmic starfield design and Google Analytics 4 integration.

## Features

- **Astro + Tailwind CSS** - Fast, modern static site generation with utility-first CSS
- **Cosmic Design** - Beautiful starfield background with frosted glass UI elements
- **Articles Section** - Content collections for blog-style articles (labeled as "Articles" instead of "Blog")
- **Bot-Proof Contact** - JavaScript-obfuscated email address with copy-to-clipboard functionality
- **GA4 Analytics** - Production-only Google Analytics 4 with Consent Mode v2
- **SEO Optimized** - Sitemap, robots.txt, OpenGraph, Twitter cards, and semantic HTML
- **Accessible** - Skip links, ARIA labels, semantic markup, and focus management
- **GitHub Pages Ready** - Automated deployment via GitHub Actions
- **WebP Images** - Optimized background images with JPEG fallback

## Quick Start

### Prerequisites

- Node.js 18+
- npm or pnpm

### Installation

```bash
# Clone the repository
git clone https://github.com/obtainable.ai/obtainable.ai.git
cd obtainable.ai

# Install dependencies
npm install

# Copy environment template
cp .env.example .env

# Start development server
npm run dev
```

Visit `http://localhost:4321` to see the site.

## Configuration

### GitHub Actions Secrets

For deployment, add this secret to your GitHub repository settings:

- `GA_MEASUREMENT_ID` - Your GA4 Measurement ID (optional)

### Site URL

Update `astro.config.mjs` with your production URL:

```js
export default defineConfig({
  site: "https://yourdomain.com", // or https://username.github.io/repo
  // ...
});
```

## Content Management

### Adding Articles

Create a new `.md` file in `src/content/articles/`:

```markdown
---
title: "Your Article Title"
description: "A brief description for SEO and listings"
author: "Your Name"
publishDate: 2025-12-22
tags: ["ai", "product"]
draft: false
---

Your article content goes here...
```

Articles are automatically:

- Listed on `/articles` (sorted by date, newest first)
- Generated with SEO metadata
- Filtered out if `draft: true`

## Deployment

### GitHub Pages

1. Enable GitHub Pages in your repository settings (Settings → Pages)
2. Set source to "GitHub Actions"
3. Add required secrets (see Configuration above)
4. Push to `main` branch - the site will build and deploy automatically

### Custom Domain

1. Add your custom domain in GitHub Pages settings
2. Update `site` in `astro.config.mjs` to your domain
3. Configure DNS with your provider

## Development

```bash
# Start dev server
npm run dev

# Type-check
npm run astro check

# Build for production
npm run build

# Preview production build
npm run preview
```

## Performance & Best Practices

- **GA4**: Only loads in production builds (`import.meta.env.PROD`)
- **Consent Mode v2**: Pre-configured for GDPR compliance
- **WebP Images**: Background uses WebP with JPEG fallback for optimal loading
- **Sitemap**: Auto-generated on build
- **SEO**: Canonical URLs, OpenGraph, Twitter cards on all pages
- **Accessibility**: Skip links, semantic HTML, ARIA labels
- **Bot-Proof Email**: JavaScript-obfuscated email address prevents scraping
