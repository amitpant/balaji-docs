# Data model

Database: MongoDB (Atlas) via Mongoose. All records have `createdAt` and `updatedAt`.

**Display rule:** the public site renders a field only when it has a value. Never show "N/A", "0" or empty labels.

## Project

| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| `title` | string | yes | e.g. "3BHK Villa, Kathgodam" |
| `slug` | string | yes | Auto-generated from title, unique, used in URLs |
| `category` | enum | yes | `residential`, `commercial`, `interior`, `renovation` (to confirm) |
| `status` | enum | yes | `completed`, `ongoing`, `upcoming` |
| `coverImage` | Image | yes | Shown on cards |
| `location` | string | no | Area or town |
| `gallery` | Image[] | no | Ordered |
| `videos` | string[] | no | YouTube URLs; store the video ID |
| `plotAreaSqft` | number | no | |
| `builtUpAreaSqft` | number | no | |
| `floors` | number | no | |
| `cost` | object | no | `{ amountInr?: number, onRequest?: boolean }` |
| `startDate`, `completionDate` | date | no | |
| `description` | string | no | Plain text with paragraphs |
| `highlights` | string[] | no | Materials, special features |
| `published` | boolean | yes | Default `false` |
| `featured` | boolean | no | Default `false` |
| `displayOrder` | number | no | Lower shows first |

`Image` = `{ url, publicId, width, height, alt? }` (Cloudinary).

## Testimonial

| Field | Type | Required |
| --- | --- | --- |
| `name` | string | yes |
| `location` | string | no |
| `text` | string | yes |
| `rating` | number 1–5 | no |
| `photo` | Image | no |
| `published` | boolean | yes (default `false`) |
| `displayOrder` | number | no |

## Enquiry

| Field | Type | Required |
| --- | --- | --- |
| `name` | string | yes |
| `phone` | string | yes (10-digit Indian mobile) |
| `email` | string | no |
| `location` | string | no |
| `projectType` | string | no |
| `message` | string | no |
| `status` | enum | `new` (default), `contacted`, `closed` |
| `source` | string | page the form was sent from |

## SiteSettings (single document)

`stats: [{ label, value }]`, `phone`, `whatsapp`, `email`, `address`, `mapUrl`, `social: { facebook?, instagram?, youtube? }`, `trustBadges: string[]`.

## AdminUser

`name`, `email` (unique), `passwordHash` (bcrypt), `role` (`owner` | `editor`).
