# luciletranchant — personal site

Static site. No build step, no JS, no dependencies. Three pages sharing one stylesheet:

```
index.html                      — landing + Work grid
case-study/index.html           — HI pipelines case study      → /case-study/
work/digest-architecture/       — executive-readout engine     → /work/digest-architecture/
work/mirrorline/                — AI-answer auditing (R&D)     → /work/mirrorline/
about/index.html                — bio                          → /about/
contact/index.html              — contact form (Formspree, armed)
assets/style.css                — design tokens & all styling
CNAME                           — custom domain (luciletranchant.com)
```

URLs are root-relative and clean (`/case-study/`, `/about/`) — they work both at
`<username>.github.io` before DNS and at `luciletranchant.com` after.

## Deploy to GitHub Pages (~5 minutes)

1. Create a **public** repo named exactly `<your-username>.github.io`
   (e.g. `luciletranchant.github.io`). The name is what makes it serve at the root URL.
2. Push these files to it:

```bash
cd site
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin git@github.com:<your-username>/<your-username>.github.io.git
git push -u origin main
```

3. Repo → Settings → Pages → confirm Source = `main` branch, `/ (root)`.
4. Live at `https://<your-username>.github.io` within a minute or two.

Local preview any time: `python3 -m http.server` from this folder, then open http://localhost:8000

## Custom domain — luciletranchant.com (owned; CNAME file already in this repo)

After pushing, do this once at your domain registrar:

1. At your DNS provider, add **four A records** on the apex (`@`):

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

2. Add one **CNAME record**: `www` → `<your-username>.github.io`
3. Repo → Settings → Pages: the `CNAME` file in this repo makes GitHub pick up
   `luciletranchant.com` automatically once DNS resolves.
4. When the DNS check passes, tick **Enforce HTTPS**.

Old `github.io` links redirect automatically after this — nothing already shared breaks.

## Contact form

Armed and live: Formspree form `xpqvlwwd`, submissions arrive at
lucile.tranchant@gmail.com, honeypot + Formspree spam filtering in place.

## House rules for future edits

- The job-digest pipeline is never mentioned on this site.
- Work entries are engineering write-ups only: no pricing, no offers, no client
  names, no "work with me" language. Commercial framing waits for the IFRC
  outside-activity check and lives on Mirrorline's own site if/when it launches.
- No "open to opportunities" language anywhere; this is a practice site.
- Same redaction discipline as the case study: no internal IFRC material,
  no colleague names, personal-initiative framing stays explicit.
- When the practitioner post is written, it gets a `writing/` section here
  and LinkedIn links back to it — not the other way around.
