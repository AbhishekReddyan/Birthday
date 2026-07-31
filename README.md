# Ankitha's Birthday Site

A single-page surprise site: countdown → login → "how much do you mean to me?" meter →
message → gift picker → friendship certificate → feedback.

Everything lives in one file: **index.html**. No build step, no server.

---

## Before you publish — fill in 3 things

Open `index.html` and find the CONFIG block near the top of the `<script>` section.

1. **`FORM_URL`** — paste your Formspree endpoint so gift + feedback replies reach your inbox.
   Sign up free at formspree.io, create a form, copy the URL like
   `https://formspree.io/f/abcd1234`, and replace the `XXXXXXXX` one.
   (Submit the form once yourself to activate it — Formspree emails you a confirm link.)

2. **`UNLOCK_NOW`** — must be `false` for the real launch, so the countdown runs and the
   site opens automatically at midnight on Aug 3. Set it to `true` only when previewing.

3. Double-check **`HER_NAME`** (Ankitha) and **`HER_DOB`** (your birthday, 2001-12-27),
   and **`YOUR_NAME`** (Reddy) on the certificate.

---

## Publish on GitHub Pages with your domain (my.ankitha.world)

### 1. Put the files on GitHub
- Create a free account at github.com if you don't have one.
- Click **New repository**, name it anything (e.g. `birthday`), set it **Public**, create it.
- Click **Add file → Upload files**, drag in **index.html** and **CNAME**, then **Commit**.

### 2. Turn on Pages
- In the repo: **Settings → Pages**.
- Under **Build and deployment → Source**, choose **Deploy from a branch**.
- Branch: **main**, folder: **/ (root)**. Save.
- Wait ~1 minute; it'll show a live `https://<username>.github.io/birthday` link.

### 3. Connect my.ankitha.world
- Still in **Settings → Pages → Custom domain**, type `my.ankitha.world` and Save.
  (The CNAME file in this repo already sets this too.)

### 4. Point the subdomain at GitHub (in Spaceship DNS)
Because this is a SUBDOMAIN (my.ankitha.world, not the bare ankitha.world),
you only need ONE CNAME record — not the four A records.

Log in to Spaceship → your domain **ankitha.world** → **DNS / Advanced DNS**.
Add this record:

| Type  | Host / Name | Value                |
|-------|-------------|----------------------|
| CNAME | my          | <username>.github.io |

Replace `<username>` with your GitHub username. The trailing dot (github.io.) is
added automatically by most panels — don't worry if you don't see it.

Note: "Host" is just `my` (Spaceship adds the `.ankitha.world` part for you). If the
panel asks for the full name, enter `my.ankitha.world`.

### 5. Wait, then enable HTTPS
DNS can take anywhere from a few minutes to a few hours to take effect.
Once it resolves, go back to **Settings → Pages** and tick **Enforce HTTPS**.
Now `https://my.ankitha.world` shows your site.

---

## Final launch checklist
- [ ] `FORM_URL` filled in and Formspree activated
- [ ] `UNLOCK_NOW = false`
- [ ] Name / DOB / YOUR_NAME correct
- [ ] Tested the whole flow once in a normal browser
- [ ] DNS records added in Spaceship
- [ ] Enforce HTTPS ticked

Happy birthday to Ankitha! 🎉
