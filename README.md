# luciletranchant — personal site

Static site. No build step, no JS, no dependencies. Three pages sharing one stylesheet:

```
index.html          — landing / positioning
case-study.html     — HI pipelines case study (public version)
about.html          — bio
assets/style.css    — design tokens & all styling
```

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

## Custom domain (later, optional — nothing breaks by waiting)

Once you own `luciletranchant.com` (Cloudflare Registrar or Porkbun):

1. At your DNS provider, add **four A records** on the apex (`@`):

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

2. Add one **CNAME record**: `www` → `<your-username>.github.io`
3. Repo → Settings → Pages → Custom domain → enter `luciletranchant.com` → Save
   (this commits a `CNAME` file to the repo — keep it).
4. Wait for the DNS check to pass, then tick **Enforce HTTPS**.

Old `github.io` links redirect automatically after this — nothing already shared breaks.

## House rules for future edits

- The job-digest pipeline is never mentioned on this site.
- No "open to opportunities" language anywhere; this is a practice site.
- Same redaction discipline as the case study: no internal IFRC material,
  no colleague names, personal-initiative framing stays explicit.
- When the practitioner post is written, it gets a `writing/` section here
  and LinkedIn links back to it — not the other way around.
