# getseis.app

The marketing site: `index.html`, `privacy.html`, `support.html`, `assets/`. Static, no build step.
Fonts come from Google Fonts; everything else is in this folder.

## Placeholders to fill before going live

- `APP_STORE_URL` (in all three pages): the App Store link, `https://apps.apple.com/app/id<APPLE_ID>`,
  known once the app record exists in App Store Connect (App Information › Apple ID).
- `© 2026 Nessa Studio` in the footer: the copyright name.
- The App Store button is a plain brand button. Apple's official "Download on the App Store" badge
  can replace it once downloaded from developer.apple.com/app-store/marketing/guidelines (it may
  not be redrawn).

## Deploying on GitHub Pages with the custom domain

1. Create a public repository (for example `getseis.app`) and push this folder as its root, or as
   the `docs/` folder with Pages set to serve from it. `CNAME` is already here.
2. Repository › Settings › Pages: source = the branch and folder; custom domain = getseis.app;
   tick Enforce HTTPS once the certificate is issued (a few minutes after DNS resolves).
3. At the registrar, DNS for `getseis.app`:
   - four A records at the apex (`@`): 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - one CNAME for `www` → `<github-user>.github.io`
4. In App Store Connect use `https://getseis.app/privacy.html` as the Privacy Policy URL and
   `https://getseis.app/support.html` as the Support URL.

Any other static host (Cloudflare Pages, Netlify, Vercel) works the same: point it at this folder.
