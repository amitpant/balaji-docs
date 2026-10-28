# 001 — Tech stack

**Date:** 2026-10-28 · **Status:** accepted

## Decision

| Layer | Choice |
| --- | --- |
| Frontend (site + admin) | React + Vite, React Router, Tailwind CSS, TanStack Query, React Hook Form + Zod |
| Backend | Node.js (LTS) + Express |
| Database | MongoDB Atlas + Mongoose |
| Photos | Cloudinary (signed direct uploads) |
| Videos | YouTube links |
| Auth | JWT in httpOnly cookie, bcrypt |
| Email | Nodemailer (Gmail SMTP) or Resend |
| Hosting | Web: Vercel or Netlify. API: Render or Railway |
| CI | GitHub Actions: lint, test, build |

## Why

- The owner asked for Node.js and React.
- Optional project fields suit a document database.
- Cloudinary resizes and compresses photos, which keeps mobile pages fast.
- YouTube hosts video for free.
- Admin panel lives inside `balaji-web` (lazy-loaded at `/admin`) to share the design system.

## Watch

Free API hosting tiers can sleep when idle. Confirm limits before launch; budget a small paid plan if needed.
