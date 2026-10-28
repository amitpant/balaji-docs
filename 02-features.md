# Features — user stories

Each story has an ID used in task names and pull requests.

## Visitor

| ID | As a visitor I can… | Done when |
| --- | --- | --- |
| V1 | See what the company does in the first screen of the home page | Hero shows photo, one-line promise, "Get a free consultation" button |
| V2 | Browse ongoing and completed projects | Projects page has two tabs; only published projects appear |
| V3 | Filter projects by category | Category chips filter the grid without a page reload |
| V4 | Open a project and see photos, videos and details | Detail page shows gallery, YouTube embeds, and only filled fields |
| V5 | View photos full screen on my phone | Tap opens a swipeable lightbox |
| V6 | Contact the company instantly | Floating WhatsApp and call buttons on every page |
| V7 | Request a free consultation | Form submits name, phone, location, project type, message; shows success message |
| V8 | Read what other clients say | Testimonials section shows published testimonials |
| V9 | See the company's track record | Stats strip shows numbers from site settings |

## Admin

| ID | As an admin I can… | Done when |
| --- | --- | --- |
| A1 | Log in securely | Email + password; session in httpOnly cookie; logout works |
| A2 | Add a project | Form with all fields from the data model; required fields validated |
| A3 | Upload and reorder photos, choose the cover | Drag to reorder; one photo marked as cover |
| A4 | Add videos | Paste YouTube links; preview shows the embed |
| A5 | Keep a project hidden until ready | Publish switch; unpublished projects never reach the public API |
| A6 | Feature projects on the home page and set order | Featured flag and display order fields |
| A7 | Edit and delete projects | Delete asks for confirmation |
| A8 | Manage testimonials | Add, edit, hide, delete |
| A9 | Handle enquiries | Inbox list, newest first; status new / contacted / closed; email alert on new enquiry |
| A10 | Update site settings | Stats, phone, WhatsApp, email, address, map link, socials |
