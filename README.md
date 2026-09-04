# unphuped.com

Source for the public site at **https://unphuped.com**.

One static page. No build step, no framework, no dependencies. What is in this
repository is exactly what is served.

---

## What is in here

| File | Served? | What it is |
|---|---|---|
| `index.html` | yes | The entire site. Structure, styles and content in one file. |
| `logo.svg`, `favicon.svg` | yes | The monogram, rebuilt as vector from measurements of the source image. |
| `404.html` | yes | Shown for any unknown path. GitHub Pages picks this up by name. |
| `lab.html` | yes | **The shipped PHUP TEXT front end, running on the site.** 92 KB, single file, no external requests on load or on use. Verified in a headless browser before publishing: zero network calls either way. It is the tool itself, not a demo, which is why a visitor can prove the offline claim in devtools instead of believing it. |
| `robots.txt` | yes | Allows crawling and points at the sitemap. |
| `sitemap.xml` | yes | One entry. Enough for a single-page site. |
| `README.md` | no | This file. Visible to anyone browsing the repository, not part of the site. |

Fonts are the only external request the page makes.

---

## Deploying

1. Put these files in the repository root on the default branch.
2. **Settings → Pages → Build and deployment → Deploy from a branch**, pick that
   branch and the `/ (root)` folder.
3. Wait a minute. The site is live at `https://colmacpulse.github.io/<repo>/`.

That is the whole thing. No build, no action, no workflow file.

---

## Later, when the domain is ready

There is deliberately **no `CNAME` file here**. A `CNAME` in the repository with no
DNS behind it makes GitHub try to serve the custom domain, fail, and take the
github.io address down with it. So it is left out until the DNS exists.

When you get to it:

1. Point the domain at GitHub in the DNS host's control panel. Delete any default
   parking or redirect records first, or they will fight yours.
2. **Settings → Pages → Custom domain**, type `unphuped.com`, Save. GitHub creates
   the `CNAME` file itself at that moment. Set it there, not by hand, so the file
   and the setting cannot disagree.
3. Tick **Enforce HTTPS** once it stops being greyed out. The certificate is issued
   automatically and that can take a few hours.

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
