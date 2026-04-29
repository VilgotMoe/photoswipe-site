# photoswipe-site

GitHub Pages site for PhotoSwipe. Three pages:

- `index.md` — landing page (App Store URL goes here once approved)
- `privacy.md` — GDPR-compliant privacy policy (URL: `/privacy/`)
- `support.md` — support page with FAQ (URL: `/support/`)

The privacy and support URLs are what you paste into App Store Connect.

## Deploy in 5 minutes

These steps assume you have a GitHub account. If not, sign up at github.com first.

### 1. Create a new GitHub repo

1. Go to https://github.com/new
2. **Repository name:** `photoswipe-site`
3. **Public** (required for free GitHub Pages)
4. Do NOT initialize with README/license — we already have files
5. Click **Create repository**

### 2. Push this folder to the repo

Open Terminal in this folder (`~/Developer/photoswipe-site/`) and run:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<YOUR_GITHUB_USERNAME>/photoswipe-site.git
git push -u origin main
```

Replace `<YOUR_GITHUB_USERNAME>` with your actual GitHub username.

### 3. Enable GitHub Pages

1. On GitHub, go to your repo → **Settings** (top right)
2. Left sidebar → **Pages**
3. Under **Build and deployment** → **Source**: pick **Deploy from a branch**
4. **Branch:** `main` / `(root)` → **Save**
5. Wait 30–90 seconds. The page will reload with a green banner showing your site URL — something like `https://<your-username>.github.io/photoswipe-site/`

### 4. Update `_config.yml` with your real URL

Edit `_config.yml`, replace these two lines with your actual GitHub username:

```yaml
url: https://<YOUR_GITHUB_USERNAME>.github.io
baseurl: /photoswipe-site
```

Commit and push:

```bash
git add _config.yml
git commit -m "Set production URLs"
git push
```

GitHub redeploys automatically (~1 min).

### 5. Get the URLs you need for App Store Connect

After step 3 succeeds, your URLs will be:

| App Store Connect field | URL |
|---|---|
| **Privacy Policy URL** | `https://<your-username>.github.io/photoswipe-site/privacy/` |
| **Support URL** | `https://<your-username>.github.io/photoswipe-site/support/` |
| **Marketing URL** (optional) | `https://<your-username>.github.io/photoswipe-site/` |

Paste those into App Store Connect → your app → **App Information** when filling out the listing.

## Updating the site later

Edit any `.md` file, then:

```bash
git add .
git commit -m "Update privacy / FAQ / whatever"
git push
```

GitHub rebuilds within ~1 minute.

## Optional: use a custom domain later

If you want `photoswipe.app` (or similar) instead of the long github.io URL:

1. Buy the domain (~$15/yr, Cloudflare Registrar is cheap)
2. In repo Settings → Pages → **Custom domain**, enter the domain
3. Add the DNS records GitHub shows you, in your registrar's dashboard
4. Once verified, also update `url:` in `_config.yml`

Not needed for App Store submission — the github.io URL is 100% acceptable.

## Local preview (optional)

If you want to preview the site locally before pushing:

```bash
gem install bundler jekyll
bundle init
echo 'gem "jekyll-theme-minimal"' >> Gemfile
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```

You don't need this — GitHub Pages will render correctly without local testing.
