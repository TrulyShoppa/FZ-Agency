# FZ Agency website

Single-page site for FZ Agency (Shoppaholics Family) — recruiting paid BIGO Live broadcasters.
Plain HTML/CSS/JS, no build step. Just upload and it works.

## Files
```
index.html            ← the whole site
assets/img/           ← photos, logos, video poster
assets/video/         ← showcase.mp4 (25s clip, web-optimized)
```

## 1. Connect the application form (do this before going live)
The form currently points at a placeholder and won't deliver submissions until you connect it.

1. Go to **formspree.io** and create a free account.
2. Create a new form and copy its **form ID** (looks like `xnqABCDE`).
3. Open `index.html`, find `YOUR_FORM_ID` (one spot, in the `<form action=...>` line), and replace it with your ID.
4. Delete the small "Owner setup" note line just below the submit button if you like.

Submissions will then land in your Formspree inbox (and your email). Prefer a spreadsheet instead? Swap the `<form>` for an embedded Google Form — say the word and I'll do it.

## 2. Publish on GitHub Pages
1. Create a new repository on your GitHub (github.com/TrulyShoppa) — e.g. `fz-agency`.
2. Upload everything in this folder (keep the `assets` folder structure intact).
3. Repo **Settings → Pages → Build from branch → main / root → Save**.
4. Your site goes live at `https://trulyshoppa.github.io/fz-agency/` in a minute or two.

All paths are relative, so it works in that subfolder as-is.

## 3. Custom domain (when you're ready)
1. In **Settings → Pages → Custom domain**, enter your domain and Save (this creates a `CNAME` file).
2. At your domain registrar, point the domain to GitHub Pages (A records to GitHub's IPs, or a CNAME to `trulyshoppa.github.io`).
3. Tick **Enforce HTTPS** once the certificate is issued.

## Editing content later
- Text: everything is in `index.html` — search for the words you want to change.
- Awards / stats: in the `STATS` and `PERKS` sections.
- Add photos: drop them in `assets/img/` and add a `<figure>` in the gallery.
- WhatsApp number appears in three places (hero, apply, and it's easy to find — search `917`).

## Adding articles to "In The Know" (SEO blog)
The blog lives at `fashzip.com/in-the-know/` (a subdirectory — best for SEO).

To publish a new AutoSEO article:
1. In `in-the-know/`, make a copy of `article-template.html` and rename it to something keyword-friendly, e.g. `grow-your-bigo-audience.html` (lowercase, hyphens, no spaces).
2. Open it and edit the four SEO fields at the top (title, description, canonical URL, og:url) plus the headline and date. Paste your AutoSEO article HTML into the marked `<div class="article-body">` area.
3. Open `in-the-know/index.html` and duplicate one `<a class="card">` block so the new article shows on the hub. Point its `href` to your new file name.
4. Open `sitemap.xml` (site root) and add a `<url>` line for the new article so Google finds it.
5. Upload the changed files to GitHub and commit.

SEO tips: give every article a unique title and description, use one `<h1>` and `<h2>` subheadings, link back to the apply page, and add real photos with descriptive alt text. After publishing, submit `https://fashzip.com/sitemap.xml` in Google Search Console to get indexed faster.
