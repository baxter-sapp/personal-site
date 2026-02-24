# Personal Website for GitHub Pages

This project is a static personal website built from:
- `index.html` (main portfolio page)
- `blog.html` (blog landing page)
- `styles.css` (shared styles)
- `assets/profile-primary.jpeg` and `assets/profile-secondary.jpeg` (portrait photos framed with CSS crop/focus)

## 1. Run locally

From this folder:

```bash
cd /Users/baxtersapp/Projects/Website
python3 -m http.server 8000
```

Then open:

- [http://localhost:8000](http://localhost:8000)
- Blog page: [http://localhost:8000/blog.html](http://localhost:8000/blog.html)

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

### B) Enable GitHub Pages

1. Open your repository on GitHub.
2. Go to **Settings** -> **Pages**.
3. Under **Build and deployment**:
- Source: **Deploy from a branch**
- Branch: **main** (or `master`)
- Folder: **/ (root)**
4. Save.

Your site URL will typically be one of these:
- `https://<your-username>.github.io/<repo-name>/`
- `https://<your-username>.github.io/` (if the repo name is `<your-username>.github.io`)

## 3. Update your content

- Edit biography/experience text in `index.html`.
- Add blog posts by duplicating a `<article class="blog-post">...</article>` block in `blog.html`.
- Replace photos in `assets/` if needed (keep similar file names or update HTML paths).

## 4. Notes on resume content

I pulled as much content as possible from your provided resume PDF in this environment. If you want exact line-for-line wording from the resume, I can do a final copy pass after you confirm the text sections.
