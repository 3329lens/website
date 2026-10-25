# 3329lens.dev

The website for [3329lens](https://github.com/3329lens/3329lens). Plain static HTML and CSS, with
no build step, no framework, no JavaScript and no third-party resources. It is deployed to
Cloudflare Pages from the `main` branch, with **no build command** and **`public` as the build
output directory**. Only `public/` is served, so this README and the LICENSE aren't published.

## Layout

Paths are relative to `public/`.

| Path | Page |
| --- | --- |
| `index.html` | Home |
| `pricing/` | Free and Pro tiers |
| `security/` | Summary of the security policy |
| `terms/`, `refunds/`, `privacy/` | Legal pages |
| `404.html` | Not-found page (Cloudflare Pages serves it automatically) |
| `.well-known/security.txt` | RFC 9116 contact file. **Renew `Expires` before 2027-10-24.** |
| `_headers` | Security headers (CSP, HSTS and others), applied by Cloudflare Pages |
| `robots.txt`, `sitemap.xml`, `favicon.svg`, `styles.css` | Supporting files |

The header and footer are repeated in every page. Change all of them together.

## Preview locally

```bash
python3 -m http.server 8000 --directory public
```

Then open <http://localhost:8000>. The local server ignores `_headers`, so check the headers on
the `*.pages.dev` preview deployment instead.

## Conventions

- **Keep the CSP intact.** It allows only same-origin stylesheets and images, and no scripts. Link
  out to external pages (for example a hosted checkout); don't embed their scripts or iframes.
- The README in the 3329lens repository is the reference documentation. Link to it rather than
  copying it here.

## Licence

The site content is copyright Lomyen Ltd, all rights reserved. See [LICENSE](LICENSE). The
3329lens software is licensed separately under Apache-2.0.
