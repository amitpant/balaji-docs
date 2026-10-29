# Balaji Construction — Docs

Single source of truth for the Balaji Construction portfolio website and admin panel.
Humans and AI agents read these files before changing code in `balaji-api` or `balaji-web`.

| File | What it covers |
| --- | --- |
| [01-product-brief.md](01-product-brief.md) | Goal, audience, scope, reference site |
| [02-features.md](02-features.md) | User stories for visitors and admins |
| [03-data-model.md](03-data-model.md) | Records, fields, display rules |
| [04-api-contract.md](04-api-contract.md) | REST endpoints, request and response shapes |
| [05-design-guide.md](05-design-guide.md) | Colours, type, layout, page structure |
| [06-admin-guide.md](06-admin-guide.md) | Plain-language guide for the client |
| [decisions/](decisions/) | One short note per significant decision |
| [tasks/backlog.md](tasks/backlog.md) | Small tasks, each with a "done when" line |
| [tasks/changelog.md](tasks/changelog.md) | What shipped, newest first |

## Repos

| Repo | Contains | Deploys to |
| --- | --- | --- |
| `balaji-docs` | This documentation | Not deployed |
| `balaji-api` | REST API: Cloudflare Worker + Hono + D1 | Cloudflare (`balaji-api`) |
| `balaji-web` | React app: public site + admin panel at `/admin`; forwards `/api` to `balaji-api` | Cloudflare (`balaji-web`) |

## Rules

- `main` is always deployable.
- One task per branch and pull request.
- When a decision changes, update these docs in the same week as the code.
