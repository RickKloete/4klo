# Kloete Group — Website

The official landing page for **Rick Kloete**, Executive Recruiter & Compensation Expert, and **Kloete Group, Inc.**

A single-page, self-contained site built in a premium neo-brutal style with full SEO and Answer Engine Optimization (AEO) so that search engines and AI assistants (Google, Perplexity, ChatGPT, Claude) can cite it directly.

---

## What's in this repository

| File | Purpose |
|------|---------|
| `index.html` | **The website.** Self-contained landing page — the portrait is embedded directly inside the file, so it works on any device with no broken images. This is the page visitors see. |
| `rick-kloete.jpg` | The portrait photo, kept as a separate file so social-share previews (LinkedIn, X/Twitter, Facebook) and AI answer engines have a real image URL to pull. Referenced by the page's Open Graph and structured-data tags. |
| `favicon.svg` | The little "RK" icon that shows in the browser tab. |
| `404.html` | A custom, on-brand "page not found" screen. GitHub Pages shows this automatically when someone hits a bad URL. |
| `robots.txt` | Tells search engines and AI crawlers they're welcome to index the site. |
| `sitemap.xml` | A map of the site for search engines. |
| `CNAME` | Connects the site to your custom domain (`www.kloetegroup.com`). |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is (faster, no processing). |
| `.gitignore` | Keeps junk files (OS clutter, editor temp files) out of the repository. |
| `README.md` | This file. |

---

## How to publish the site with GitHub Pages (free hosting)

You only need to do this once. After that, every time you update a file, the live site updates automatically.

### Step 1 — Create the repository
1. Go to [github.com/new](https://github.com/new).
2. Name it something like `kloete-group-website`.
3. Set it to **Public** (GitHub Pages is free for public repos).
4. Click **Create repository**.

### Step 2 — Upload these files
The easiest way (no command line needed):
1. On your new repo page, click **uploading an existing file**.
2. Drag **all** the files from this folder into the box — including the hidden ones (`.gitignore`, `.nojekyll`, `CNAME`). If your computer hides dotfiles, enable "show hidden files" first.
3. Click **Commit changes**.

> Prefer the command line? See the "Git commands" section at the bottom.

### Step 3 — Turn on GitHub Pages
1. In your repo, go to **Settings → Pages**.
2. Under **Source**, choose **Deploy from a branch**.
3. Branch: **main**, folder: **/ (root)**. Click **Save**.
4. Wait 1–2 minutes. GitHub will show you the live URL (something like `https://yourusername.github.io/kloete-group-website/`).

### Step 4 — Connect your custom domain (kloetegroup.com)
1. The included `CNAME` file already points to `www.kloetegroup.com`.
2. In **Settings → Pages → Custom domain**, confirm `www.kloetegroup.com` is filled in.
3. At your domain registrar (wherever you bought kloetegroup.com), add these DNS records:
   - A **CNAME** record: host `www` → value `yourusername.github.io`
   - For the bare domain (`kloetegroup.com`), add four **A** records pointing to GitHub's IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
4. Back in **Settings → Pages**, check **Enforce HTTPS** once it becomes available (can take up to 24 hours).

That's it — your site is live at https://www.kloetegroup.com.

---

## How to update the site later

1. Open the repo on GitHub.
2. Click the file you want to change (e.g., `index.html`).
3. Click the pencil ✏️ icon to edit, or upload a replacement.
4. Click **Commit changes**.
5. The live site updates within a minute or two.

GitHub keeps a full history of every version, so you can always roll back if something breaks.

---

## Updating the photo

The portrait lives in **two** places, so if you change your headshot, update both:
1. Replace `rick-kloete.jpg` with the new photo (keep the same filename).
2. In `index.html`, the photo is also embedded as a long `data:image/jpeg;base64,...` string in two spots. Updating this requires re-encoding the image — easiest to ask Claude to "re-embed my new headshot into the landing page."

---

## Important: if you change your domain

If you ever use a different domain than `www.kloetegroup.com`, update these references so SEO and social sharing keep working:
- `CNAME` — your new domain
- `sitemap.xml` — the `<loc>` URLs
- `robots.txt` — the `Sitemap:` line
- `index.html` — the `canonical`, `og:url`, `og:image`, and JSON-LD `@id`/`url`/`image` values

---

## Git commands (optional, for command-line users)

```bash
# From inside this folder:
git init
git add .
git commit -m "Initial commit: Kloete Group website"
git branch -M main
git remote add origin https://github.com/YOURUSERNAME/kloete-group-website.git
git push -u origin main
```

To push an update later:
```bash
git add .
git commit -m "Describe what you changed"
git push
```

---

## Technical notes

- **No build step, no dependencies.** Pure HTML/CSS/vanilla JavaScript. Only external call is to Google Fonts.
- **Responsive** at three breakpoints: 1024px (tablet), 640px (phone), 380px (small phone).
- **Accessible**: rich ALT text, ARIA labels, keyboard-navigable FAQ, `prefers-reduced-motion` support.
- **SEO + AEO**: complete meta tags, Open Graph, Twitter cards, and JSON-LD structured data (`Person`, `Organization`, `Service`, `FAQPage`) for citation by answer engines.

---

© Kloete Group, Inc. · Franklin, TN · (615) 823-7723 · rick@kloetegroup.com
