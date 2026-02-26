# Personal Website for GitHub Pages

This project is a static personal website built from:
- `index.html` (main portfolio/home page)
- `blog.html` (blog page)
- `cool-links.html` (links page with card layout)
- `styles.css` (shared site styles)
- `assets/profile-primary.jpeg` and `assets/profile-secondary.jpeg` (portrait photos)

## 1. Run locally

From this folder:

```bash
cd /Users/baxtersapp/Projects/Website
python3 -m http.server 8000
```

Then open:

- [http://localhost:8000](http://localhost:8000)
- Blog page: [http://localhost:8000/blog.html](http://localhost:8000/blog.html)
- Cool Links page: [http://localhost:8000/cool-links.html](http://localhost:8000/cool-links.html)

To stop the server, press `Ctrl + C`.

## 2. Publish to GitHub Pages

If this folder is not yet a git repo, initialize and connect it first:

```bash
cd /Users/baxtersapp/Projects/Website
git init
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
```

Use these steps once the remote is configured.

### A) Commit and push

```bash
cd /Users/baxtersapp/Projects/Website
git add .
git commit -m "Create personal website with blog and GitHub Pages setup"
git push origin main
```

If your default branch is `master`, replace `main` with `master`.

### B) Enable Pages (recommended: GitHub Actions)

1. Open your repository on GitHub.
2. Go to **Settings** -> **Pages**.
3. Under **Build and deployment**, set **Source** to **GitHub Actions**.
4. Commit/push will trigger the included workflow at `.github/workflows/pages.yml`.
5. Go to the **Actions** tab and wait for `Deploy static site to Pages` to complete.

This repository now includes a ready-to-use Pages workflow:
- `.github/workflows/pages.yml`

### C) If you prefer branch deploy (only if available)

Some repos still show this option:
- Source: **Deploy from a branch**
- Branch: **main** (or `master`)
- Folder: **/ (root)**

If you do not see **Deploy from a branch**, that is expected for some repo/account/org setups. Use **GitHub Actions**.

### D) Common blockers

Your site URL will typically be one of these:
- `https://<your-username>.github.io/<repo-name>/`
- `https://<your-username>.github.io/` (if the repo name is `<your-username>.github.io`)

If deployment still does not work, check:
- Repo visibility/plan limits for private repos.
- Org policy restricting Pages.
- **Settings** -> **Actions** -> **General** -> Workflow permissions set to allow workflow writes.

## 3. Update your content

- Home page content:
  - Edit biography, experience, and skills in `index.html`.
  - Update nav links in the `<header>` blocks if you add/remove pages.
  - MTG random card widget lives near the bottom of `index.html` and uses Scryfall API (`https://api.scryfall.com/cards/random`).
- Blog page content:
  - Add posts by duplicating a `<article class="blog-post">...</article>` block in `blog.html`.
- Cool Links page content:
  - Edit cards in `cool-links.html`.
  - Current structure is 6 cards total, shown 3 per row on desktop.
  - Filled cards are linkable `<a class="link-card link-card-link">...</a>`.
  - Placeholder cards are non-link `<article class="link-card placeholder">...</article>`.
- Styling:
  - Shared styles are in `styles.css`.
  - `cool-links.html` also includes a small inline `<style>` block for card-specific styling/cache reliability.

## 4. Quick edit examples

- Add a new cool link card:
  1. Copy one existing linked card block in `cool-links.html`.
  2. Update card title (`<h2>`), URL (`href`), and hover text (`<p class="link-card-hover">`).
- Change the number of columns:
  - In `styles.css`, update `.cool-links-grid { grid-template-columns: ... }`.
  - Mobile breakpoints are near the bottom of `styles.css` (`900px` and `620px`).
