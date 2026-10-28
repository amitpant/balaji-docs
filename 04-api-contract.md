# API contract

Base URL: `/api`. JSON in and out. Errors use one shape:

```json
{ "error": { "code": "VALIDATION_ERROR", "message": "Phone is required", "fields": { "phone": "Required" } } }
```

Admin routes require the `session` httpOnly cookie set by login. Public routes never return unpublished records.

## Public

| Method | Path | Notes |
| --- | --- | --- |
| GET | `/api/health` | `{ status: "ok" }` |
| GET | `/api/projects` | Query: `status`, `category`, `featured`, `page`, `limit` (default 12). Returns `{ items, total, page }` with card fields only |
| GET | `/api/projects/:slug` | Full project; 404 if missing or unpublished |
| GET | `/api/testimonials` | Published, by `displayOrder` |
| GET | `/api/settings` | Public site settings |
| POST | `/api/enquiries` | Body: `name`, `phone`, optional rest. Rate-limited (5 per IP per hour) + honeypot field `website` must be empty. Returns `201 { id }` |

## Auth

| Method | Path | Notes |
| --- | --- | --- |
| POST | `/api/auth/login` | Body: `email`, `password`. Sets cookie. Returns `{ user }` |
| POST | `/api/auth/logout` | Clears cookie |
| GET | `/api/auth/me` | Current admin or 401 |

## Admin

| Method | Path | Notes |
| --- | --- | --- |
| GET | `/api/admin/projects` | All projects incl. unpublished |
| POST | `/api/admin/projects` | Create |
| GET / PUT / DELETE | `/api/admin/projects/:id` | Read, update, delete |
| POST | `/api/admin/uploads/sign` | Returns a signed Cloudinary upload payload; browser uploads directly |
| GET / POST | `/api/admin/testimonials` | List, create |
| PUT / DELETE | `/api/admin/testimonials/:id` | Update, delete |
| GET | `/api/admin/enquiries` | Query: `status`, `page` |
| PATCH | `/api/admin/enquiries/:id` | Body: `status` |
| GET / PUT | `/api/admin/settings` | Read, update |
