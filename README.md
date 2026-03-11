# hiittrack-web

Landing website for the HIIT training app **HIITTrack**.

A minimalist, retro-inspired static site built with pure HTML + CSS.  
No frameworks, no trackers, no bloat — just like the app itself.

---

## Files

| File | Purpose |
|------|---------|
| `index.html` | Main (and only) page — all eight sections |
| `style.css` | All styling — responsive, retro-inspired |
| `screenshots/` | Drop app screenshots here (see below) |

---

## Customizing before launch

Search the HTML for these comments and replace the placeholder values:

- **App Store link** – find `https://apps.apple.com/` and replace with your real listing URL
- **Price** – find `$6.99` and update to match your App Store price
- **Email form** – find the `EMAIL FORM PLACEHOLDER` comment block and paste in your ConvertKit / Mailchimp / Beehiiv embed code
- **Screenshots** – add PNG files to a `screenshots/` folder named `screen-timer.png`, `screen-presets.png`, `screen-custom.png`, `screen-history.png`
- **App icon** – uncomment the `<img>` tag in the header and add your `icon.png`
- **Contact email** – find `support@millertech.dev` and update
- **"Coming soon" banners** – uncomment those `<p class="coming-soon">` lines if the app isn't live yet, and comment out the App Store button

---

## Deploying to GitHub Pages

### Step 1 — Create the repository (skip if you already have one)

1. Go to <https://github.com/new>
2. Name it `hiittrack-web` (or any name you like)
3. Leave it **public** (required for the free GitHub Pages tier)
4. Click **Create repository**

### Step 2 — Push the files

```bash
git init
git add .
git commit -m "Initial site"
git remote add origin https://github.com/YOUR_USERNAME/hiittrack-web.git
git branch -M main
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. In your repository, go to **Settings → Pages**
2. Under **Source**, choose **Deploy from a branch**
3. Branch: `main`, Folder: `/ (root)`
4. Click **Save**
5. GitHub will show your live URL, typically:  
   `https://YOUR_USERNAME.github.io/hiittrack-web/`

### Step 4 — Add a custom domain (optional)

1. In **Settings → Pages → Custom domain**, enter your domain (e.g. `hiittrack.app`)
2. Click **Save** — GitHub creates a `CNAME` file automatically
3. At your DNS registrar, add the following records:

   | Type | Host | Value |
   |------|------|-------|
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |
   | CNAME | www | YOUR_USERNAME.github.io |

4. Wait for DNS propagation (up to 24 h), then enable **Enforce HTTPS** in the Pages settings

---

## Local preview

No build step required — just open `index.html` in any browser:

```bash
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

Or serve it locally with Python:

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

---

## License

© Miller Technologies. All rights reserved.
