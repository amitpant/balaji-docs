# Backlog

One task = one branch = one pull request. Tick when merged.

## Phase 0 — Discovery (week 1)

- [ ] P0-1 Collect client answers to the open questions in `01-product-brief.md`
- [ ] P0-2 Collect logo and a few sample projects with photos
- [x] P0-3 Create `balaji-docs`, `balaji-api`, `balaji-web` repos with starter code
- [ ] P0-4 Wireframe home, projects, project detail, add-project form; client approval
- [ ] P0-5 Replace placeholder accent colour with the logo colour in `05-design-guide.md`

> **2026-10-29:** Phases 1–3 were built in one go on Cloudflare (see `decisions/002-cloudflare-d1.md`). Remaining: deploy `balaji-api`, add secrets, first login, client loads real projects.

## Phase 1 — Foundation (week 2)

- [x] P1-1 API: connect MongoDB Atlas; env validation. **Done when** `/api/health` reports DB connected
- [x] P1-2 API: AdminUser model, seed script, login / logout / me. **Done when** tests cover all three
- [ ] P1-3 API: deploy to Cloudflare (`balaji-api`). **Done when** live `/api/health` returns ok
- [x] P1-4 Web: layout shell, header, footer, floating WhatsApp + call buttons. **Done when** checked at 375px and 1280px
- [x] P1-5 Web: admin login page wired to API. **Done when** login works on the live URL
- [x] P1-6 Web: deploy to Vercel or Netlify

## Phase 2 — Backend API (week 3)

- [x] P2-1 Project model + public and admin routes with tests
- [x] P2-2 Cloudinary signed uploads
- [x] P2-3 Testimonial routes with tests
- [x] P2-4 Enquiry route: validation, rate limit, honeypot (email alert: later)
- [x] P2-5 Site settings routes

## Phase 3 — Admin panel (week 4)

- [x] P3-1 Projects list with publish switch and featured flag
- [x] P3-2 Project form: fields, photo upload, reorder, cover, YouTube links
- [x] P3-3 Testimonials screens
- [x] P3-4 Enquiries inbox with status
- [x] P3-5 Site settings form

## Phase 4 — Public site (weeks 5–6)

- [x] P4-1 Home page sections from the design guide
- [x] P4-2 Projects page: tabs + category filter
- [x] P4-3 Project detail: gallery lightbox, videos, details
- [ ] P4-4 Services, About, Contact pages
- [x] P4-5 Enquiry form wired to API

## Phase 5 — Launch (week 7)

- [ ] P5-1 Client loads projects
- [ ] P5-2 Custom domain + HTTPS
- [ ] P5-3 SEO basics: titles, descriptions, Open Graph images, sitemap
- [ ] P5-4 Analytics and Google Business Profile link
- [ ] P5-5 Launch checklist on phone and desktop

## Added from client feedback (2026-10-29)

- [x] Social media tab: Facebook, Instagram, YouTube links; WhatsApp number and message
- [x] Facebook (Meta) Pixel ID: tracks page views, call/WhatsApp taps and enquiries for ads
- [ ] Enquiry email alerts via an email API
