# Multi-Page Site Plan

**Goal:** Turn the current single-page directory into a multi-page Jekyll site where each top-level category is its own page.

**Status:** Phase 1 (sitemap + robots) shipped. Phase 2 described below — needs operator sign-off before execution.

## Why multi-page

- SEO: each category becomes its own indexable URL.
- Plausible: per-page analytics.
- Maintainability: scope diffs to a single category.
- Linking: external sites can deep-link to a specific category.

## Jekyll scaffold

```
_config.yml
CNAME
robots.txt
sitemap.xml
index.md               # landing page with intro + cards linking to each category
pages/                # one file per category
    foundational-texts.md
    archives-historical-collections.md
    academic-papers.md
    books.md
    organizations-institutions.md
    websites-blogs-communities.md
    guides-documentation.md
    media-documentaries.md
```

Each `pages/*.md` uses Jekyll frontmatter:

```yaml
---
layout: default
title: Foundational Texts
permalink: /library/foundational-texts/
---
```

## URL strategy

- **Option 1 (recommended):** mirror anchors as paths (`/library/foundational-texts/`)
- **Option 2:** flat (`/foundational-texts/`)

Pick option 2 once Plausible token is set up and we have actual anchor-traffic data.

## Phases

1. **Shipped (this PR):** `sitemap.xml` + `robots.txt` + plan + intro + `last verified` markers.
2. **Pending sign-off:** scaffold `_layouts/category.html`, create `pages/` folder with stubs.
3. **Pending sign-off:** split README content into per-page files (or keep README canonical + per-page mirrors).
4. **Pending Plausible token:** add per-page analytics.

## Decisions needed

- Option 1 vs Option 2 for URLs.
- Split README vs README-as-canonical.