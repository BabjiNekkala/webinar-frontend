# Claude Masterclass — Landing Page

A single-file, dependency-free landing page for the **Claude Masterclass** 90-minute live AI workshop (₹999, 5 July 2026). Premium dark theme with neural-network hero animation, scroll reveals, 3D tilt cards, live countdown, and a payment-ready checkout button.

## What's in here

```
index.html              ← the entire site (HTML + CSS + JS, all inline)
assets/img/instructor-0.jpg   ← T. Satish photo
README.md               ← this file
vercel.json             ← optional config for Vercel hosting
```

That's it. No build step, no npm install, no framework. Everything (Tailwind, fonts) loads from CDNs.

## 🚀 Fastest way: host it with Claude Code

Open this folder in **Claude Code** and just say:

> "Deploy this folder as a live website."

Claude will spin it up (Vercel/Netlify) and hand you back a public URL in under a minute. You can also tell it things like *"change the price to ₹799"*, *"swap my photo in,"* or *"connect my Razorpay account"* and it'll edit the files for you — no coding needed.

Prefer to do it by hand? The manual options are below.

## How to host it manually (3 options)

**Option A — Just open it.** Double-click `index.html`. Works fully offline.

**Option B — Vercel / Netlify (free, recommended).**
1. Drag this whole folder onto [vercel.com/new](https://vercel.com/new) or [app.netlify.com/drop](https://app.netlify.com/drop).
2. Done. You get a live URL in ~20 seconds.

**Option C — Any web host / cPanel.** Upload the folder contents to your `public_html` (or equivalent). The page is plain static files, so any host works.

## Payments

The "Pay ₹999" buttons are currently a **placeholder** — no payment gateway is connected. Clicking one shows a "Checkout coming soon" message. This keeps the preview safe to share without any live keys in the code.

To connect a real gateway (e.g. Razorpay, Stripe, Cashfree), open `index.html`, find the `pay()` function near the bottom of the `<script>` block, and replace the placeholder modal with your provider's checkout call. For Razorpay you would also add their checkout script in the `<head>` and pass your own publishable key + amount (`99900` = ₹999 in paise).

> **Note:** for production, always verify payments server-side (via a webhook) before granting access — never trust the client-side success callback alone.

## Editing content

All copy lives in clearly-labelled JavaScript arrays at the top of the `<script>` block in `index.html`:

| Want to change…        | Edit this array |
|------------------------|-----------------|
| Rotating hero phrases  | `ROTATOR`       |
| Top ticker items       | `TICKER`        |
| Before/After rows      | `REALITY`       |
| The 6 skills           | `SKILLS`        |
| Agenda timeline        | `AGENDA`        |
| What's included        | `INCLUDED`      |
| Testimonials           | `TESTI`         |
| FAQ                    | `FAQ`           |

Change the workshop date in two places: the visible text (`5 July 2026`) and the countdown target `new Date('2026-07-05T10:00:00+05:30')`.

## Customising the look

Brand colours are defined once in the `tailwind.config` block at the top of `<head>` (the `cm:` palette — `coral`, `violet`, `cyan`, etc.). Change those hex values and the whole site re-themes.
