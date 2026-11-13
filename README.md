# Personal homepage

A simple, static academic homepage. No framework or build step is needed.

## Files

- `index.html` — text, links, preprints, talks and teaching
- `style.css` — fonts, spacing, layout and pond image positioning
- `assets/pond-desktop.jpg` and `assets/pond-mobile.jpg` — banner images
- `.nojekyll` — tell GitHub Pages to serve the files as written

## Work locally in VS Code

1. Open this folder in VS Code.
2. Edit `index.html` for the words and hyperlinks. Edit `style.css` for appearance.
3. Open `index.html` in a browser to preview it (or start `python -m http.server 8000` and visit `http://localhost:8000`).
4. Save and review the changes before publishing.

## Publish edits (in the VS Code terminal)

```bash
git pull --ff-only
# Edit, save and preview your site
git status
git add index.html style.css assets/
git commit -m "Update homepage"
git push
```

When staging all changes using VS Code Source Control, you can simply click `+` beside each changed file, enter a message, click **Commit**, and then **Push**.

**Important:** Your source branch (normally `main`) is your live homepage. Pushing to `main` publishes those changes via GitHub Pages. Test locally first.

## Initial setup

1. Create a public GitHub repository named `<your-github-username>.github.io`.
2. Clone it using VS Code's **Git: Clone**, then copy the contents of this directory into the cloned folder.
3. Commit and push the files.
4. Go to GitHub repository **Settings → Pages** and select **Deploy from a branch**, branch **main**, folder **/(root)**.
5. Check the default site at `https://<your-github-username>.github.io`.
6. Once the domain is registered, configure **Custom domain** under **Settings → Pages**, verify it on GitHub and set DNS records at the registrar; use HTTPS.

Do not edit the site in GitHub's web UI unless necessary; keep one canonical working copy on your computer to avoid conflicts. If you do edit on GitHub, run `git pull --ff-only` before your next local edit.

## Email privacy

Your web page prints an obfuscated address, without a clickable `mailto:` link. Git commits themselves can expose an address: configure a GitHub-provided `noreply` commit email in Git if you want to keep your institutional email private.

## Content maintenance

- New preprint: duplicate an existing `<div class="paper">` block inside the Preprints section.
- New seminar: add a venue to the relevant `<ul class="talk-venues">`, or add a new `<li class="talk-group">` for a new talk title.
- External links: edit only `href="..."` values and visible names.
- Crop: adjust `.hero-photo { object-position: ... }` in `style.css`.
- This site is intentionally static. Do not add complex tooling unless it becomes necessary.
