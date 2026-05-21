# Mohammad Javed — Book landing page

Static marketing site for **Why Smart People Stay Broke: From Degree to Dollars — The Practical Blueprint to Build Real Wealth** by Mohammad Javed. Single-page layout: hero with cover, social proof, problem, what you’ll learn, Amazon reviews, email signup, author, and final CTA.

## What’s in the repo

| Item | Purpose |
|------|--------|
| `index.html` | Full page: cover-matched CSS variables, responsive layout, mobile hamburger nav, meta/OG tags, Amazon CTAs |
| `DOMAIN-SETUP.md` | Step-by-step Netlify + DNS instructions for `whysmartpeoplestaybroke.com` |
| `netlify.toml` | Publish root `.` — Netlify parses `index.html` at deploy for Forms |
| `_redirects` | Redirect Netlify subdomain to custom domain |
| `images/` | Book cover (`book-cover.png`) and optional author photo — see `images/README.md` |
| `LICENSE` | MIT License (Copyright © 2026 Ilmacademy) |

## Tech stack

- Plain **HTML5**
- **Tailwind CSS** via CDN (`tailwindcss.com`) for a few layout utilities
- **Google Fonts** (Playfair Display, Inter)

Smooth scrolling uses **Lenis** (ES module from jsDelivr) and light UI motion uses **Anime.js** 3.2.1 (CDN); both are skipped when the visitor prefers reduced motion.

No build step or package manager is required.

## Run locally

**Option A — open the file**

Double-click `index.html` or open it from your browser. Some features behave best when the page is served over HTTP (relative URLs, certain security policies).

**Option B — quick static server** (from this folder)

If you have Python 3:

```bash
python -m http.server 8080
```

Then visit `http://localhost:8080` and open `index.html` if needed.

With Node.js (`npx`):

```bash
npx --yes serve .
```

## Deploying

Upload the folder to any static host (GitHub Pages, Netlify, Vercel, etc.) with `index.html` as the default document.

## Custom domain (Netlify)

See [DOMAIN-SETUP.md](DOMAIN-SETUP.md) for DNS and HTTPS steps.

## Netlify Forms (email signup)

The “Get the First Chapter Free” form posts to **[Netlify Forms](https://docs.netlify.com/forms/setup/)** as **`chapter-signup`** (`data-netlify="true"` in `index.html`). After enabling Forms in Netlify:

1. **Deploy** — push or trigger **Deploy site** so Netlify re-parses `index.html` and registers **`chapter-signup`**.
2. Verify **Forms** in the dashboard lists **`chapter-signup`** with submissions stored there.
3. **Test only on production** (`https://whysmartpeoplestaybroke.com` or your `*.netlify.app` URL), not `file://`.
4. **Notifications** — **Site configuration → Forms → Form notifications** to email / Slack / webhook when a submission arrives.

Spam control: honeypot field **`bot-field`** is wired via **`netlify-honeypot="bot-field"`** on the form.

## License

See [LICENSE](LICENSE) for the MIT terms.
