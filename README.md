# Simril Solutions — website

Single-page business site for **Simril Solutions Ltd**, hosted on GitHub Pages at
[simril.co.uk](https://simril.co.uk).

Static HTML/CSS — no build step. Edit `index.html` / `styles.css` and push to `main`.

## Files
| File | Purpose |
|------|---------|
| `index.html` | The page (hero, services, about, contact). |
| `styles.css` | Light, responsive styling. |
| `CNAME` | Custom domain for GitHub Pages (`simril.co.uk`). |
| `favicon.svg` | "S" monogram favicon. |
| `robots.txt`, `sitemap.xml` | Basic SEO. |

## Local preview
```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

## Hosting (GitHub Pages)
Repo **Settings → Pages** → Source: `Deploy from a branch`, branch `main`, folder `/ (root)`.
The `CNAME` file sets the custom domain. Keep **Enforce HTTPS** ticked once the cert issues.

## DNS (registrar: IONOS)
Point the domain at GitHub Pages **without touching email**:
- Apex `A` records → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- `www` `CNAME` → `joshm-simril.github.io`
- **Leave `MX` and SPF `TXT` records exactly as they are** — email (Google Workspace) depends on them.

## Analytics
Two trackers, both privacy-friendly:
1. **Plausible** — the `<script data-domain="simril.co.uk">` tag in `index.html` is live once you
   add `simril.co.uk` as a site in your Plausible dashboard.
2. **Cloudflare Web Analytics** — already live. Because the site is proxied through Cloudflare
   (orange cloud), the beacon is **auto-injected at the edge** — no `<script>` needed. Leave the
   commented-out beacon in `index.html` commented out; uncommenting it would double-count visits.

## Booking
The "Book a meeting" buttons point to
`https://calendly.com/simril/enquiry?guests=joshua.may@eonnext.com` — a cloned
20-minute event with business-qualifying questions; the `guests` param auto-adds the
contract calendar so the slot is blocked in both diaries. Update the URL if the slug changes.

## To confirm
- [x] Company registration number — 16326011 (Companies House).
- [x] Calendly slug — `enquiry`.
- [x] Cloudflare Web Analytics — auto-injected via the proxy (no beacon token needed).
