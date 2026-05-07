# guanyu.github.io

Personal academic homepage of **Yu Guan (管羽)** — undergraduate at the Department of
Electronic Engineering, Tsinghua University. Research interests: humanoid motion tracking,
Vision-Language-Action (VLA) models, World Action Models, and General Reward Models.

🔗 Live site: <https://giraffeguan.github.io/guanyu.github.io/>

> ⚠ Note: the URL `https://guanyu.github.io/` does **not** point to this site
> (the username `guanyu` is taken by another GitHub user). To shorten the URL,
> see the "Custom domain" section below.

---

## Stack

- Plain **HTML / CSS / vanilla JavaScript** — no build step, no framework.
- Hosted on **GitHub Pages**.
- Light & dark themes (toggle persisted in `localStorage`, respects `prefers-color-scheme`).
- Fully responsive (mobile-friendly).
- SEO-ready: Open Graph + Twitter Card meta, `robots.txt`, `sitemap.xml`,
  and JSON-LD `Person` structured data.

## Repository layout

```
.
├── index.html              # the entire site (single-page)
├── robots.txt              # allow all crawlers + sitemap pointer
├── sitemap.xml             # for Google Search Console
├── README.md               # this file
└── assets/
    ├── Yu_Guan_CV.pdf      # English CV
    └── 管羽_CV.pdf          # Chinese CV
```

## Local preview

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

Or just open `index.html` directly in a browser.

## Custom domain (planned)

To get a shorter URL (`https://guanyu.page/`, `https://yuguan.dev/`, etc.):

1. Buy the domain from a registrar (e.g. Cloudflare Registrar, Namecheap, Porkbun).
2. Create a single-line file at the repo root named `CNAME` with **only** the
   domain name inside, e.g.:

   ```
   guanyu.page
   ```

3. In the domain's DNS, add an **ALIAS / ANAME / flattened CNAME** at the apex
   (`@`) pointing to `giraffeguan.github.io`.
   If your registrar doesn't support apex CNAMEs, use four A records instead:

   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```

4. In GitHub: Settings → Pages → Custom domain → enter the domain → enable
   "Enforce HTTPS" once the certificate is issued (usually < 1 hour).
5. Update `index.html` (`<link rel="canonical">`, `og:url`, JSON-LD `url`)
   and `sitemap.xml` to use the new domain.

## Updating content

All text lives directly in `index.html`. To add a publication, copy an
existing `<div class="pub">…</div>` block. To add a news item, prepend a
new `<li>` inside the `#news` section.

To replace the avatar placeholder (`YG` monogram), drop a square image at
`assets/avatar.jpg` and replace the `<div class="avatar">YG</div>` block
with `<img src="assets/avatar.jpg" alt="Yu Guan" class="avatar">`
(remember to add `object-fit: cover;` to the style).

## Getting indexed by Google

After pushing changes:

1. Visit <https://search.google.com/search-console>.
2. Add the property `https://giraffeguan.github.io/guanyu.github.io/`
   (or the custom domain when ready).
3. Verify ownership via the HTML tag method (paste the `<meta>` into `index.html`).
4. Submit the sitemap URL: `sitemap.xml`.
5. Use "URL Inspection" → "Request Indexing" on the homepage URL.

Indexing typically takes 3–14 days for a fresh site.

## License

The code in this repository is released under the MIT license.
The textual and visual content is © Yu Guan, all rights reserved.
