# Way of the Peaceful Coder — kiranbir.github.io

Personal website for Kiranbir Sodhia. Plain HTML/CSS — no build step, no dependencies.

## Structure

- `index.html` — home/bio
- `publications.html` — technical papers + leadership interviews
- `blog/index.html` — blog index; one HTML file per post (16 posts, migrated from Wix)
- `css/style.css` — the entire theme (cream/navy/gold palette, Fraunces + Inter via Google Fonts)
- `.nojekyll` — tells GitHub Pages to serve files as-is

To edit a page, just edit its HTML. To add a blog post, copy any post file in `blog/`, change the title/date/content, and add an entry to the list in `blog/index.html`.

## Publish on GitHub Pages

Repo: `kiranbir/kiranbir.github.io`. From this folder (the first command removes a partially-initialized `.git` with stale lock files — recreate it fresh):

```
rm -rf .git
git init
git add .
git commit -m "Way of the Peaceful Coder — initial site"
git branch -M main
git remote add origin https://github.com/kiranbir/kiranbir.github.io.git
git push -u origin main
```

If the repo already has a placeholder commit (e.g. an auto-generated README), the push will be rejected — use `git push -u origin main --force` to replace it.

Pages serves `<username>.github.io` repos from main automatically; the site goes live at https://kiranbir.github.io within a minute or two. If it doesn't, check **Settings → Pages → Source: Deploy from a branch → main / (root)**.

## Point your domain at it (when ready)

1. At your DNS provider, add a `CNAME` record: `www` → `<username>.github.io`. For the apex domain (`kiranbirsodhia.com`), add `A` records to GitHub Pages' IPs: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`.
2. On GitHub: **Settings → Pages → Custom domain** → enter your domain → Save (this commits a `CNAME` file to the repo). Check **Enforce HTTPS** once the certificate is issued.

## Note on images

The 6 blog-post images and the original cover thumbnails are still hotlinked from the Wix CDN (`static.wixstatic.com`) — direct downloads weren't possible from this environment. They'll keep working even after the Wix site is unpublished as long as the media stays in your Wix media manager, but for full independence download them into an `images/` folder and update the `<img src>` paths in `blog/the-most-valuable-benefits.html`, `blog/unexpected-surprises-of-following-guidelines.html`, `blog/simple-clean.html`, and `blog/imessage-when-your-code-sucks.html`.
