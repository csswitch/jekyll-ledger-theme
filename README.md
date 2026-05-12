# jekyll-ledger-theme

**The General Ledger** — a Jekyll theme for accountants, CPAs, bookkeepers, and finance writers.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-csswitch.github.io-1a4731?style=flat-square)](https://csswitch.github.io/jekyll-ledger-theme/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](LICENSE)
[![Jekyll](https://img.shields.io/badge/Jekyll-3.10-red?style=flat-square)](https://jekyllrb.com)

---

## Features

- **Ledger-style post list** — date | entry | account category | reading time in clean accounting columns
- **Professional credentialing** — display CPA, CFA, or other qualifications in header and bylines
- **Accountant-grade table styling** — debit/credit columns, totals rows, caption support
- **Print-ready** — clean print stylesheet for articles clients print out
- **4 accent palettes** — Green (default), Navy, Burgundy, Slate — switch in `_config.yml`
- **Author card** — bio, credentials, firm name
- **Archive page** — grouped by fiscal year
- **GitHub Pages compatible** — no unsupported plugins
- **No jQuery** — vanilla JS only
- **Responsive** — mobile navigation + collapsing columns

---

## Live Demo

👉 [https://csswitch.github.io/jekyll-ledger-theme/](https://csswitch.github.io/jekyll-ledger-theme/)

---

## Quick Start

### Option A — Use as a GitHub template

1. Click **"Use this template"** → create your own repo
2. Enable GitHub Pages under **Settings → Pages → Source: GitHub Actions**
3. Edit `_config.yml` with your details

### Option B — Clone and run locally

```bash
git clone https://github.com/csswitch/jekyll-ledger-theme.git
cd jekyll-ledger-theme
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000` in your browser.

---

## Configuration

Edit `_config.yml`:

```yaml
title: "The General Ledger"
description: "Insights on accounting, finance, and numbers that matter."
author:
  name: "Jane Smith"
  credentials: "CPA, CMA"
  firm: "Smith & Associates"
  email: "jane@example.com"
  linkedin: "janesmith"

ledger:
  accent: "green"           # green | navy | burgundy | slate
  show_column_headers: true
  show_entry_numbers: true
  print_ready: true
  tagline: "Your Finance Blog Tagline"
```

---

## Writing Posts

Create files in `_posts/` named `YYYY-MM-DD-title.md`:

```markdown
---
layout: post
title: "Understanding Deferred Tax Assets"
date: 2024-03-01
categories: [Tax Planning]
tags: [deferred tax, GAAP, IAS 12]
description: "A practical guide to deferred tax assets and liabilities."
---

Your content here...
```

### Special table classes

Add classes to table cells for accounting-specific styling:

```markdown
| Account | Debit | Credit |
|---------|------:|-------:|
| Cash | 10,000 | |
| Revenue | | 10,000 |
{:.accounting-table}
```

Use `class="debit"`, `class="credit"`, `class="total"`, `class="amount"` on `<td>` elements in HTML posts for styled formatting.

---

## Colour Palettes

Change `ledger.accent` in `_config.yml`:

| Value | Look |
|-------|------|
| `green` | Classic accounting ledger paper — dark forest green |
| `navy` | Corporate finance — deep navy blue |
| `burgundy` | Traditional practice — rich burgundy |
| `slate` | Modern advisory — cool dark slate |

---

## Notices / Callout Boxes

Use raw HTML in your posts for callout boxes:

```html
<div class="notice notice--info">
  <strong>Note:</strong> This applies to UK GAAP only.
</div>

<div class="notice notice--warning">
  <strong>Important:</strong> Regulations changed in April 2024.
</div>
```

Available types: `--info`, `--note`, `--warning`, `--tip`

---

## License

MIT License — see [LICENSE](LICENSE).

---

## Part of the csswitch theme collection

Explore more professional Jekyll themes at [github.com/csswitch](https://github.com/csswitch).
