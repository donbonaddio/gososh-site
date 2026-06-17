# gososh.app static site

Self-contained static site for gososh.app. No build step, no dependencies.

## Files

- `index.html` — Landing page (premium dark theme with icon, features, pricing summary)
- `privacy.html` — Privacy policy (light/dark adaptive)
- `terms.html` — Terms of service (light/dark adaptive)
- `icon.png` — 1024×1024 app icon, referenced by all pages
- `CNAME` — GitHub Pages custom-domain config (points to gososh.app)
- `README.md` — this file

## Before publishing

Both `privacy.html` and `terms.html` contain the placeholder `[DATE OF FIRST PUBLIC RELEASE]`. Replace with the actual launch date (e.g., `June 24, 2026`) before going live.

## Deploy to GitHub Pages

1. Create a new public GitHub repo (e.g., `gososh-site`)
2. Push all files in this folder to the repo's main branch
3. In the repo: Settings → Pages → Source = "Deploy from a branch", Branch = `main` / root
4. GitHub Pages will detect the CNAME file and configure the custom domain automatically
5. At your domain registrar (where gososh.app is registered), add DNS records:
   - **A records** for the apex (gososh.app):
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - **CNAME record** for the www subdomain:
     - `www` → `<your-github-username>.github.io`
6. Wait 5-60 min for DNS propagation
7. Back in GitHub Pages settings, enable "Enforce HTTPS" once the cert provisions

## URLs that need to resolve before App Store submission

The in-app paywall links to:

- https://gososh.app/privacy
- https://gososh.app/terms

GitHub Pages serves `privacy.html` at `/privacy` and `terms.html` at `/terms` automatically (with the `.html` extension stripped). Both will work without further configuration.

## Local preview

Open `index.html` in any browser. All paths are relative — works from the filesystem with no server needed.
