# Deploying coparentingsg.org: Step-by-Step Guide

This guide explains how to connect your domain **coparentingsg.org** to your new website using **Cloudflare Pages** or **Vercel** (both 100% free hosting with automatic HTTPS SSL certificates).

---

## Architecture Overview

- **Source Code:** Clean, lightweight HTML5, CSS3, and JavaScript in `index.html`.
- **Domain:** `coparentingsg.org` (already registered).
- **Hosting / CDN:** Cloudflare Pages (Recommended) or Vercel / Netlify.
- **SSL Certificate:** Free automatic TLS/SSL through Cloudflare or Vercel.

---

## Method 1: Cloudflare Pages (Recommended — Fast, Free & Robust)

### Step 1: Create a GitHub Repository
1. Go to [github.com](https://github.com) and log into your account.
2. Click **New Repository**.
3. Name it `coparentingsg-website` and set it to **Public** or **Private**.
4. Upload the files from your folder:
   - `index.html`
   - `README.md`
5. Click **Commit changes**.

### Step 2: Connect to Cloudflare Pages
1. Sign in to your [Cloudflare Dashboard](https://dash.cloudflare.com/).
2. On the left navigation, click **Workers & Pages** → **Create application** → **Pages** tab.
3. Click **Connect to Git** and select your `coparentingsg-website` repository.
4. Set the build configuration:
   - **Framework preset:** `None`
   - **Build command:** *(leave blank)*
   - **Build output directory:** `/` (or leave default root)
5. Click **Save and Deploy**. Your website will be live in 30 seconds on a temporary `.pages.dev` subdomain.

### Step 3: Link Your Custom Domain (`coparentingsg.org`)
1. In Cloudflare Pages, go to your project → **Custom domains** tab.
2. Click **Set up a custom domain**.
3. Type: `coparentingsg.org` and `www.coparentingsg.org`.
4. Cloudflare will automatically configure the DNS records:
   - If your domain's nameservers already point to Cloudflare, it will configure them automatically with 1 click.
   - If your domain is registered elsewhere (e.g., Namecheap, GoDaddy, Google Domains), simply log into that registrar and add the DNS CNAME record indicated by Cloudflare.

---

## Method 2: Vercel (Alternative 1-Click Deployment)

1. Sign up or log into [Vercel](https://vercel.com/).
2. Click **Add New...** → **Project**.
3. Import your GitHub repository (`coparentingsg-website`).
4. Click **Deploy**.
5. Once deployed, navigate to **Settings** → **Domains**.
6. Enter `coparentingsg.org` and add the two DNS records displayed by Vercel to your domain registrar's DNS management panel:
   - **Type A:** `@` → `76.76.21.21`
   - **CNAME:** `www` → `cname.vercel-dns.com`

---

## Local Preview
You can preview your website immediately in any web browser:
Double-click `index.html` in this folder or open:
`coparentingsg-website/index.html`
