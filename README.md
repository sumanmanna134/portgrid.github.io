# PortGrid Official Product Website & Documentation

This repository contains the complete, standalone open-source product landing page, interactive showcase, and technical documentation for **PortGrid: Deterministic Local Cloud Services & Developer Platform**.


## 2. Previewing Locally

To inspect the website on your local machine before publishing:

### Option A: Using Python 3 (Built-in)
```bash
cd /Users/sumanmanna/Documents/product/portgrid.github.io
python3 -m http.server 8080
```
Open your browser at `http://localhost:8080`.

### Option B: Using Node.js Serve
```bash
npx serve .
```

---

## 3. How to Launch & Publish to GitHub Pages

Follow these exact steps to launch the website live to the world in under two minutes:

### Step 1: Create a GitHub Repository
1. Navigate to [GitHub New Repository](https://github.com/new).
2. Set the repository name:
   - For a user root page: Name it `portgrid.github.io` (will publish to `https://<username>.github.io`).
   - For a project page: Name it `portgrid-site` or `portgrid` (will publish to `https://<username>.github.io/portgrid`).
3. Set visibility to **Public**.
4. Click **Create repository** (do not initialize with README since you already have this folder).

### Step 2: Initialize Git and Push

Run the following commands in your terminal:

```bash
cd /Users/sumanmanna/Documents/product/portgrid.github.io

# 1. Initialize local git repository
git init -b main

# 2. Add all files (HTML pages, screenshots, workflows)
git add .

# 3. Create initial commit
git commit -m "feat: launch PortGrid product website and documentation"

# 4. Link your GitHub remote (replace with your repository URL)
git remote add origin https://github.com/mannasuman134/portgrid.github.io.git

# 5. Push to GitHub
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. In your GitHub repository, click on **Settings** (top bar).
2. In the left navigation menu, click **Pages**.
3. Under **Build and deployment -> Source**, select **GitHub Actions**.
4. That is it. The workflow at `.github/workflows/deploy.yml` will automatically build and publish your site.
5. Within 45 seconds, your site is live at:
   `https://mannasuman134.github.io/portgrid` (or `https://<your-username>.github.io`).

---

## 4. Custom Domain Setup (Optional)

If you own a custom domain (e.g. `portgrid.dev` or `portgrid.io`):

1. Create a file named `CNAME` in the repository root:
   ```bash
   echo "portgrid.dev" > CNAME
   git add CNAME
   git commit -m "chore: add custom domain CNAME"
   git push
   ```
2. Configure DNS records at your domain registrar (Cloudflare, Namecheap, GoDaddy):
   - **For apex domain (`portgrid.dev`):** Add 4 `A` records pointing to GitHub Pages IP addresses:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - **For subdomain (`docs.portgrid.dev` or `www.portgrid.dev`):** Add a `CNAME` record pointing to `<username>.github.io`.
3. In GitHub repository **Settings -> Pages**, verify the domain and check **Enforce HTTPS**.

---

## 5. Technology Stack

- **Pure Static HTML5**: Zero server-side build steps required.
- **Tailwind CSS (CDN)**: Ultra-responsive utility design with dark obsidian theme.
- **JetBrains Mono & Inter typography**: Optimized for technical readability.
- **Interactive UI**: Native vanilla JavaScript media switchers and tab navigators.
- **Self-Contained Assets**: High-resolution screenshots and live demonstration GIF embedded directly.
- **Continuous Deployment**: Automated GitHub Actions pages upload.
