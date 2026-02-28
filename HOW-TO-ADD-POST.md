# HJTrending: Auto-Publish Blog Workflow (GitHub + Markdown)

## What happens now

When you upload a new `.md` file to `/content/[category]/` and push to GitHub:

1. GitHub Action runs `scripts/build-content.mjs`
2. It automatically updates:
   - `/data/posts.json`
   - `/data/[category]-posts.json`
   - `/data/breaking-news.json`
   - `/sitemap.xml`
   - `/sitemap-news.xml`
3. Action commits these generated files back to your repo
4. Your deployed site instantly sees the new post in lists and search

No manual JSON editing is required.

## Required frontmatter in each markdown file

Add this block at the top of every markdown article:

```yaml
---
id: fifa-010
title: Your SEO Title Here
slug: your-seo-url-slug
category: fifa
subcategory: world-cup-2026
date: 2026-02-26
modified: 2026-02-26
author: HJTrending Sports Desk
thumbnail: https://images.unsplash.com/photo-xxxx?w=1200&q=85&auto=format
thumbnailAlt: Descriptive image alt text
excerpt: 150-155 character SEO summary with target keywords.
readTime: 6 min
wordCount: 1200
featured: false
trending: true
breaking: false
tags: [fifa world cup 2026, world cup 2026 schedule, football news today 2026]
schemaType: NewsArticle
---
```

## Article structure (recommended)

1. One `# H1` title at top
2. Intro paragraph with primary keyword
3. Logical `## H2` sections with related keywords
4. Clear conclusion and internal links

## Local build command

```bash
npm run build:content
```

## GitHub files added

- `.github/workflows/build-content.yml`
- `scripts/build-content.mjs`
- `package.json` script: `build:content`
