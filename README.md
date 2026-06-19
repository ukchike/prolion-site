# Prolion Integrated Services — Website

A single-page static marketing site (one `index.html`, no build step, no dependencies).
Fonts load from Google Fonts; the favicon is inline. It is ready to deploy to Vercel as-is.

## Files
- `index.html` — the website (this is all that's strictly required)
- `vercel.json` — optional config: clean URLs + basic security headers

---

## Deploy to Vercel — choose ONE method

### Option A — Drag & drop (no account setup, fastest)
1. Go to **https://vercel.com/new**
2. Sign in (GitHub, GitLab, Google or email).
3. Look for the **"deploy a template / upload"** area, or use the Vercel CLI in Option C.
   (If drag-and-drop isn't shown, use Option B or C — they always work.)

### Option B — From a Git repository (recommended for ongoing edits)
1. Create a new repo on GitHub and upload `index.html` and `vercel.json`.
2. Go to **https://vercel.com/new** → **Import** the repo.
3. Framework preset: **Other**. Build command: **none**. Output directory: **leave blank** (root).
4. Click **Deploy**. Done — you get a `*.vercel.app` URL in ~20 seconds.
5. Every future `git push` redeploys automatically.

### Option C — Vercel CLI (one command)
```bash
npm i -g vercel          # install once
cd prolion-site          # the folder containing index.html
vercel                   # follow prompts → preview URL
vercel --prod            # promote to production
```

---

## Custom domain (e.g. prolion.ng)
1. In the Vercel project → **Settings → Domains → Add**.
2. Enter your domain and follow the DNS instructions (an A record or CNAME at your registrar).
3. HTTPS is provisioned automatically.

## Before you go live — quick checklist
- [ ] Replace the email `hello@prolion.ng` if it isn't live yet (search the file for it).
- [ ] **Activate the consultation form** (see below) — it won't send until you add a form ID.
- [ ] Confirm WhatsApp / LinkedIn / X / CredoTax / NEXUS links open correctly.
- [ ] (Optional) Add an `og:image` (1200×630 PNG) for richer link previews on social.

---

## Activate the lead-capture form (2 minutes, free)

The "Request a consultation" form is wired for **Formspree**, which emails you each
submission — no backend or database needed.

1. Go to **https://formspree.io** and create a free account.
2. Create a new form; point its notifications to **hello@prolion.ng** (or your inbox).
3. Formspree gives you an endpoint like `https://formspree.io/f/abcdwxyz`.
4. Open `index.html`, find `action="https://formspree.io/f/YOUR_FORM_ID"`, and replace
   `YOUR_FORM_ID` with your real ID (e.g. `abcdwxyz`).
5. Redeploy. Submit a test message — it should land in your inbox, and the visitor
   sees an on-page "Thank you" confirmation.

Notes:
- Until you swap the ID, the form shows a friendly "endpoint not set" message instead of failing silently.
- A hidden honeypot field is already included to reduce spam.
- The free tier covers ~50 submissions/month; paid tiers raise that if needed.
