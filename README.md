# AGM Reputation Management — All-Staff Presentation Micro-Site

**INTERNAL — AGM Real Estate Group staff material. Private repository. Do not make public.**

A digital presentation for AGM's all-staff meeting on the Reputation Management Program: where our online reputation started, where it is today, and the everyday habits that keep it moving forward. Built to be driven live in the meeting (roughly 20–30 minutes) and left up afterward as a reference for the team.

Single-file static site (`index.html`). No build step, no dependencies. Based on the AGM micro-site template used for the White Heather owner presentation, with content tailored for the Reputation Management Program.

## Local preview
Open `index.html` in a browser. That's it.

## Sections
- **Overview** — the meeting purpose, at-a-glance numbers, why reviews matter, and a jump-off to every section.
- **Agenda** — the meeting run-of-show, with presenters and timing.
- **Where We Stand** — the before/after profile slider (2.2★ → 4.5★), the momentum chart, the math of momentum, and recent reviews.
- **The Program** — objectives, ground rules, how it works, best-practice habits, the review-moment map, and example talking points.
- **Recognition & Goals** — featured team members, the monthly review goal, and the closing.
- **Reputation Portal** — the print and digital tools, plus a printable pocket reminder.

## Before the meeting (content still to load / confirm)
Every pending item is flagged in-page with a yellow "to load / to confirm" note:
- **At-a-glance numbers** — current rating, total reviews, and five-star count (shown in brackets today).
- **Before/after screenshots** — swap the two placeholder panels in the "Where We Stand" slider for the actual profile screenshots (old AGM Inc at 2.2★, new AGM Real Estate Group at 4.5★). Each panel is a `.ba-layer`; replace its contents with `<img src="images/profile-before.png" ... />` / `profile-after.png`.
- **This month's progress** — set the current review count in the "Setting the Pace" goal bar.
- **Recognition** — confirm featured team members, review counts, and any recognition planned.
- **Reputation Portal link** — add the live portal URL.
- **Presenters** — confirm names on the Agenda (currently Soraya, Leary, Gerry).

## Statistics cited
Figures on the "Why It Matters" and "The Program" sections are from BrightLocal's Local Consumer Review Survey, Harvard Business School (Luca, *Reviews, Reputation, and Revenue*), and industry renter surveys (Apartments.com). Used sparingly to support the reasoning behind the program.

## Deploy — Cloudflare Pages (AGM standard pattern)
1. Cloudflare dashboard → **Workers & Pages → Create → Pages → Connect to Git** → select this repo.
2. Settings: Framework preset **None** · Build command **(empty)** · Build output directory **/**
3. Every push to the default branch auto-deploys production; every branch/PR gets its own preview URL.

## REQUIRED before sharing any URL: Cloudflare Access
Zero Trust → Access → Applications → **Add self-hosted application**:
- Application domain: `<project>.pages.dev` **and** `*.<project>.pages.dev` (previews are otherwise public).
- Policy: Allow → Emails → AGM team. One-time PIN works without SSO setup.

## Operational notes
- `_headers` enforces `noindex` and security headers at the edge.
- Analytics events are stubbed on `window.dataLayer` / `posthog` — add the PostHog snippet in `<head>` and set the project key to go live.
- To add imagery: each photo slot is a `.frame`/`.ba-layer` div; convert the photo to a base64 data URI or place it in `/images` and swap the placeholder for an `<img>`.

Managed by AGM Real Estate Group · 12330 Northup Way, Bellevue, WA 98005.
