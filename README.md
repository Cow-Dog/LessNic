# How to host the LessNic legal pages

These three HTML files are designed to drop straight into a free GitHub Pages site. Steps below take ~5 minutes.

## Option A: GitHub Pages (free, recommended)

1. **Create a new public GitHub repo** named `legal` (under any user/org you control — for example, `lessnic`).
2. **Drag the contents of this folder** (`privacy.html`, `terms.html`, `index.html`) into the root of the repo and commit.
3. **Enable Pages**: Repo → Settings → Pages → Source: `main` branch, `/ (root)` folder → Save.
4. **Wait ~1 minute**. Your URLs will be:
   - `https://YOUR_USERNAME.github.io/legal/`
   - `https://YOUR_USERNAME.github.io/legal/privacy.html`
   - `https://YOUR_USERNAME.github.io/legal/terms.html`
5. **Update the URLs** in [src/config/appConfig.ts](../src/config/appConfig.ts):
   ```ts
   privacyUrl: 'https://YOUR_USERNAME.github.io/legal/privacy.html',
   termsUrl:   'https://YOUR_USERNAME.github.io/legal/terms.html',
   ```
6. **Add the privacy URL** in App Store Connect when you create the app record.

> The placeholder URLs in `appConfig.ts` use `https://lessnic.github.io/legal/...` — if you grab the GitHub username `lessnic`, the placeholders will Just Work.

## Option B: Custom domain

If you grab `lessnic.app` or `lessnic.com`:
1. Host the same files on any static host (Netlify, Vercel, Cloudflare Pages — all free).
2. Update `appConfig.ts` URLs accordingly.

## What you still need to do

- **Add a real support email**: `support@lessnic.app` is referenced in both files. Either set up forwarding from your domain (Cloudflare/Google Workspace), or change every reference to your personal email.
- **Get the policies reviewed** if you're worried — for TestFlight + early App Store you're almost certainly fine, but a lawyer should look at them once you start making real money.
- **Check the "Last updated" date** matches your actual launch date.

## What's in each file

- `privacy.html` — what data is collected (very little, all local), what isn't, permissions, deletion, contact
- `terms.html` — disclaimer (not medical advice), 18+, subscription/billing language, limitation of liability, etc.
- `index.html` — simple landing page that links the other two
