# 002 — Run everything on Cloudflare with D1

**Date:** 2026-10-29 · **Status:** accepted · **Replaces:** the hosting and database rows of 001

## Decision

| Layer | Before (001) | Now |
| --- | --- | --- |
| API runtime | Node.js + Express on Render or Railway | Cloudflare Worker + Hono (Express-style) |
| Database | MongoDB Atlas | Cloudflare D1 (SQLite) |
| Website hosting | Vercel or Netlify | Cloudflare Worker (static assets) |
| Site ↔ API | Cross-origin with CORS | Same origin: website Worker forwards `/api/*` to `balaji-api` via a service binding |
| Photos / videos | Cloudinary / YouTube | unchanged |

## Why

- Vercel, Netlify and other hosts are blocked on the owner's internet connection; Cloudflare works.
- One free account for site, API and database; every push to `main` deploys.
- D1 lets the full API be tested end to end on a local copy (`npm test` in `balaji-api`).
- Same origin means the admin login cookie works in all browsers, including Safari.

## Notes

- Tables are created automatically on first request (`src/db.js`).
- Records keep searchable columns plus a JSON `data` column, so new optional fields need no migration.
- Passwords use PBKDF2 (Web Crypto) to stay within the Workers free CPU budget.
- Enquiry email alerts are not wired yet (Workers can't use SMTP); the admin panel shows a badge for new enquiries. Add an email API (e.g. Resend) later if wanted.
