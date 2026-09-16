# personal-site

A single static page, `index.html`, with no build step and no backend. It uses the CollectShine theme ("The Listening Room After Dark").

The Bio, Talks and Projects sections act like separate pages through the URL hash (`/#talks`, `/#projects`). If JavaScript is off, the page shows as one long scroll.

## Edit content
Everything is in `index.html`. Search for `TODO` and `[Placeholder]`.

- **Hero photo:** save a portrait as `assets/hero.jpeg` (about 1200×1500). The placeholder shows until that file exists.
- **Talks:** copy an `<li class="card talk">` block to add another talk.
- **Projects:** copy an `<article class="card project">` block to add another project. For a thumbnail, replace the letter in `.project-thumb` with `<img src="assets/..." alt="">`.
- **Name:** it appears in `<title>`, `.brand`, `h1`, the footer and `siteName` in the script.

## Preview locally
```bash
python3 -m http.server 8000
```
Then open http://localhost:8000.

## Deploy to GitHub Pages (free)
1. Create a **public** repo and push this folder to `main`.
2. In the repo, open **Settings → Pages**. Set **Source** to *Deploy from a branch*, then choose `main` and `/ (root)`.
3. Put your domain in `CNAME` (one line, e.g. `yourname.com`) and push. You can also set it under Settings → Pages → Custom domain.
4. At your domain registrar, add these DNS records:
   | Type  | Name | Value |
   |-------|------|-------|
   | A     | @    | 185.199.108.153 |
   | A     | @    | 185.199.109.153 |
   | A     | @    | 185.199.110.153 |
   | A     | @    | 185.199.111.153 |
   | CNAME | www  | `<your-github-username>.github.io` |

   These IPv6 records are optional: `AAAA @` with `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153` and `2606:50c0:8003::153`.
5. Once DNS resolves (minutes to a few hours), tick **Enforce HTTPS** in Settings → Pages.
6. Optional but recommended: verify the domain under your GitHub account's Settings → Pages. This stops anyone else from claiming it.

The only cost is the domain renewal.
