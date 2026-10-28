# The Imāmī Review — free static research website

A complete, responsive HTML/CSS/JavaScript website for source-led Imāmī research and critical responses to Al-Islaah. Designed to deploy on **GitHub Pages for £0**, with no paid hosting, no database, no login, and no build dependencies for visitors.

## What's included

- Elegant homepage, four article pages, searchable/filterable article archive
- Dedicated methodology, source library, about, and 404 pages
- Arabic right-to-left source excerpts with translations
- Numbered citations, linked footnotes/backlinks, mobile navigation
- Dark mode, reading-progress bar, copy-link and print actions
- Search engine metadata, accessible labels and responsive layouts
- **Sample content is labelled editorial draft**: carefully verify everything before public academic publication

## Preview locally

Open `index.html` in your browser. Or (recommended, especially for testing links) run:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000/`.

## Publish for free on GitHub Pages

1. Sign in at https://github.com and select **New repository**.
2. Choose a name such as `imami-review` and set the repository to **Public** (required on GitHub Free for Pages).
3. Upload the **contents of this folder** (including `index.html`, `articles/`, `assets/` and `.nojekyll`) to the root of the repository. Do not upload the ZIP as a single file.
4. Commit to the `main` branch.
5. Open **Settings → Pages**. Under *Build and deployment*, select **Deploy from a branch**, branch **main**, folder **/(root)**; then **Save**.
6. GitHub will provide a URL similar to `https://YOUR-USERNAME.github.io/imami-review/`.

This design uses relative URLs, so it works both at a project URL and a top-level `YOUR-USERNAME.github.io` repository without editing paths. See GitHub's official instructions: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Change the project name or branding

- The current name is **The Imāmī Review** (an editable working title).
- To rename it consistently, search-and-replace `The Imāmī Review` inside `editorial/build_site.py` and regenerate.
- Change colours, layout and typography in `assets/styles.css`.
- Change the icon in `assets/favicon.svg`.
- The font CSS uses freely available Google Fonts with local fallbacks; the website remains usable without loading these fonts.

## Add or edit an article

This starter includes a lightweight Python generator with **no third-party dependencies**. It has already generated all public HTML files, so GitHub Pages does not need to run Python.

1. Open `editorial/build_site.py` in a text editor.
2. Find the `ARTICLES = [` array. Copy one complete `dict(...)` entry to make a new article.
3. Change its unique `slug`, title, subtitle, category (`hadith`, `rijal`, `quran` or `theology`), sections, and references.
4. Each section is `('Section heading', '''<p>Article HTML here...</p>''')`.
5. Number footnote links as `<a class="ref-link" href="#fn-1" id="ref-1">1</a>` and put the matching bibliographic entry in `refs`. Keep footnote numbers unique on each page.
6. Run `python3 editorial/build_site.py`.
7. Commit the regenerated `index.html` and `articles/*.html` files (and the source editor changes) to GitHub; the site updates automatically.

If you prefer a no-code editorial workflow later, the pages can be migrated to Jekyll, Astro, or a headless CMS.

## Essential editorial checklist before publishing

- Replace working title/author information with the real publication identity you choose.
- Verify all Arabic quotations against the exact book edition and check translation accuracy.
- Give full footnotes including volume/page/hadith number, publisher and date where useful.
- Distinguish explicit quotations from your analysis and label uncertain issues.
- Keep neutral source attribution when engaging scholars with differing Imāmī methodologies.
- Remove draft labels **only after** the essays are fully fact-checked.
- Never upload private information or unpublished files to a public GitHub repository.

## Hosting and privacy

No analytics scripts, cookies, newsletters, tracking pixels or contact forms are included. Fonts are requested from Google Fonts when available; remove the `@import` at the start of `assets/styles.css` if you want no third-party web requests. Dark mode preferences are saved locally in the visitor's browser.

The content and source links are supplied for research and illustration, not as a claim of endorsement by Al-Islaah, listed scholars, or cited libraries.
