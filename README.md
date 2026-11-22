# Prolion Ltd — Website

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
- [x] Email set to **prolionltd@gmail.com**.
- [x] Consultation form wired to Formspree (`https://formspree.io/f/xwvdokey`).
- [ ] Confirm the first test submission lands in the Formspree inbox / prolionltd@gmail.com.
- [ ] Confirm WhatsApp / LinkedIn / X / CredoTax / NEXUS links open correctly.
- [x] RC number (9642532) and TIN added to the footer.
- [x] Branded **og-image.png** added (1200×630) with meta tags for rich link previews.

### og:image note
The page references the image as `/og-image.png` (root-relative), which works on Vercel as-is.
If a platform's preview ever fails to show it, set an **absolute** URL once your final domain is
live — edit the two `og-image.png` references in `index.html` to e.g.
`https://prolion.ng/og-image.png`. Test previews with the LinkedIn Post Inspector,
the X Card Validator, or **https://www.opengraph.xyz**.

---

## The lead-capture form is already active

The "Request a consultation" form posts to **Formspree** at `https://formspree.io/f/xwvdokey`
and emails each submission — no backend needed.

**One-time step on Formspree's side:** the very first submission to a new form triggers a
confirmation email from Formspree asking you to verify the form. Send one test message from the
live site, then click the verify link in the email Formspree sends to the form's owner address.
After that, all submissions flow through automatically and the visitor sees the on-page
"Thank you" confirmation.

Notes:
- A hidden honeypot field is already included to reduce spam.
- The free tier covers ~50 submissions/month; paid tiers raise that if needed.
- To change the destination inbox later, edit the form settings in your Formspree dashboard.
