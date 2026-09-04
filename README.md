# unphuped.com

Source for the public site at **https://unphuped.com**.

One static page. No build step, no framework, no dependencies. What is in this
repository is exactly what is served.

---

## What is in here

| File | Served? | What it is |
|---|---|---|
| `index.html` | yes | The entire site. Structure, styles and content in one file. |
| `404.html` | yes | Shown for any unknown path. GitHub Pages picks this up by name. |
| `CNAME` | no | Tells GitHub Pages the custom domain is `unphuped.com`. One line, bare domain, no scheme and no trailing slash. |
| `robots.txt` | yes | Allows crawling and points at the sitemap. |
| `sitemap.xml` | yes | One entry. Enough for a single-page site. |
| `.nojekyll` | no | Stops GitHub running the page through Jekyll. Not strictly needed for plain HTML, included so a future file beginning with an underscore does not silently vanish. |
| `README.md` | no | This file. Visible to anyone browsing the repository, not part of the site. |

Fonts are the only external request the page makes.

---

## Deploying

1. Push these files to the repository root on the default branch.
2. **Settings → Pages → Build and deployment → Deploy from a branch**, select that
   branch and the `/ (root)` folder.
3. In the same screen, put `unphuped.com` in **Custom domain**. GitHub will keep
   `CNAME` in step with that field, so change it in one place, not both.
4. At the DNS host, point the apex and the `www` label at GitHub:

   ```
   A      @      185.199.108.153
   A      @      185.199.109.153
   A      @      185.199.110.153
   A      @      185.199.111.153
   CNAME  www    <account>.github.io.
   ```

   Those four addresses are GitHub's published apex targets. Confirm them against
   GitHub's current documentation before relying on them; they have changed before.
5. Wait for DNS to propagate, then tick **Enforce HTTPS**. The certificate is
   issued automatically and the tickbox stays greyed out until it exists.

---

## Before it goes live

**`hello@unphuped.com` must be forwarding.** The page has exactly one call to
action and it is that address. A site that collects nothing and answers nowhere is
worse than no site.

---

## Editing the page

Everything lives in `index.html`. The palette is at the top of the stylesheet:

```css
--paper:#F7F7F5;   /* background */
--ink:#000000;     /* text and the verdict block */
--seal:#E0A53A;    /* used once, on the refusal */
--rule:#D8D6D0;    /* hairlines */
```

Two rules the page is built on, worth keeping if you edit it:

- **Every number on the page is measured.** The test counts, the manifest count,
  the mutation score and the entity number all come from the asset's own
  `START_HERE.md`. If the asset changes, the page changes with it. Nothing here is
  rounded, estimated or written from memory.
- **"What it does not do" carries the same visual weight as "What it is."** Same
  type size, same rule, same spacing. The product is sold on the difference
  between a citation and a reading, so hiding the limits would contradict it.

There is no logo yet. The masthead is a typographic wordmark and the favicon is a
placeholder line glyph. The PHUP monogram is a separate mark and is deliberately
not used here.

---

## Rights

Proprietary work product of Range Art and Design LLC (CA 202359212028), trading as
COLMACpulse.

**No open-source license is granted.** There is no `LICENSE` file in this
repository and that is deliberate, not an oversight: absent one, default copyright
applies and all rights are reserved. The absence of a license is not permission.

This repository contains the marketing page only. It does not contain the UNPHUPED
asset, its source, or any part of it.
