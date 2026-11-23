# coparentingsg.org: Complete Guide for GitHub, Vercel & Google Search Console SEO

This step-by-step master guide outlines the exact actions required to host `coparentingsg.org` via **GitHub** and **Vercel**, and index it immediately on **Google Search Console** so it appears in Google search results.

---

## 1. Quick Diagnosis: Why It Is Not Showing on Google Yet

When a brand-new website or custom domain is launched:
1. **Google does not automatically discover brand-new domains** until a link points to them or the sitemap is directly submitted in **Google Search Console (GSC)**.
2. **Vercel Canonical Domain Configuration:** If both `coparentingsg.org` and `www.coparentingsg.org` are added, one must be set as the Primary Domain with an automatic 301 redirect to the other, preventing split search authority.
3. **Repository Sync:** Any recent code improvements (sitemap, meta tags, founder photo) must be pushed to GitHub so Vercel rebuilds and serves the latest production version.

---

## 2. Step 1: Push Latest Website Files to GitHub

All core website files are located in your local folder:
`/Users/saibalbhattacharya/Library/CloudStorage/OneDrive - bolttech/Goals 2026/coparentingsg-website/`

Files to commit and push:
- `index.html` (Main website code with official Tree of Life SVG logo, founder photo, and toolkits)
- `case-studies.html` (Central hub with 4 resident segment filters: Singaporeans local, Singaporeans overseas, Expats local, Expats overseas)
- `case-study-school-holidays.html` (SG with kids in SG: 6-week MOE year-end holiday and travel protocol)
- `case-study-primary-school-transition.html` (SG with kids in SG: Primary 1 registration and cross-island transit)
- `case-study-shared-expense-tracking.html` (SG with kids in SG: Tuition, enrichment, and maintenance cost sharing)
- `case-study-expat-international-school-fees.html` (Expats with kids in SG: $84k/yr school fees, DP pass sponsorship, FX risk)
- `case-study-cross-border-relocation-hague.html` (Expats with kids overseas: Relocation to UK, mirror court orders, Hague safeguards)
- `case-study-virtual-visitation-timezones.html` (SG with kids overseas: 12-hr timezone video call schedules, asynchronous voice notes)
- `sitemap.xml` (Updated XML sitemap containing all 8 canonical indexable URLs)
- `robots.txt` (Grants full access to search crawlers and references the sitemap)
- `images/saibal-bhattacharya.jpg` (Founder profile photo)
- `images/logo-tree.svg` (Official brand logo vector)

### Option A: Using GitHub Desktop or Web Interface
1. Open your repository `coparentingsg-website` on [GitHub](https://github.com).
2. Upload / replace `index.html`, `sitemap.xml`, `robots.txt`, and the `images/` directory.
3. Commit to the `main` branch.

### Option B: Using Git in Terminal
```bash
cd "/Users/saibalbhattacharya/Library/CloudStorage/OneDrive - bolttech/Goals 2026/coparentingsg-website"
git init
git add .
git commit -m "Update SEO metadata, sitemap, and founder image"
git branch -M main
git remote add origin https://github.com/<your-github-username>/coparentingsg-website.git
git push -u origin main --force
```

---

## 3. Step 2: Configure Domains & Canonical Redirects on Vercel

1. Log into your [Vercel Dashboard](https://vercel.com).
2. Select your `coparentingsg-website` project.
3. Go to **Settings** → **Domains**.
4. Confirm both domains are listed:
   - `coparentingsg.org`
   - `www.coparentingsg.org`
5. **Set the Primary Domain & Redirect:**
   - In Vercel, click **Edit** next to `coparentingsg.org`.
   - Ensure `coparentingsg.org` is designated as the **Production** / **Primary Domain**.
   - Ensure `www.coparentingsg.org` is configured to **Redirect to coparentingsg.org** (Status Code: 301 Permanent Redirect).
   - *Why this matters:* Having both domains respond independently divides domain authority; a 301 redirect consolidates all Google ranking signals onto your primary domain.
6. **Verify DNS Status:**
   - Vercel should display green checkmarks (`Valid Configuration`) next to both domains.
   - If marked invalid, ensure your registrar DNS has:
     - **Type A:** `@` points to `76.76.21.21`
     - **CNAME:** `www` points to `cname.vercel-dns.com`

---

## 4. Step 3: Google Search Console (GSC) Setup & Indexing

Google Search Console is the direct tool to tell Google's crawlers to visit and rank your site.

### A. Add and Verify the Property
1. Go to [Google Search Console](https://search.google.com/search-console).
2. Sign in with your Google account.
3. In the top-left dropdown, select **Add Property**.
4. You will see two options:
   - **Domain** (Recommended — covers `https://coparentingsg.org`, `www`, and all subdomains):
     - Enter: `coparentingsg.org`
     - Click **Continue**.
     - Google will provide a **TXT record** (e.g. `google-site-verification=xxxx`).
     - Go to your domain registrar DNS panel (GoDaddy, Namecheap, Cloudflare, SingHost, etc.), add a DNS Record:
       - **Type:** `TXT`
       - **Host / Name:** `@`
       - **Value:** Paste the verification code.
     - Return to GSC and click **Verify**.
   - **URL Prefix** (Alternative quick method):
     - Enter: `https://coparentingsg.org`
     - Choose **HTML Tag** method.
     - Copy the meta tag provided (`<meta name="google-site-verification" content="..." />`).
     - Paste this tag inside the `<head>` of `index.html` and push to GitHub.
     - Click **Verify** in GSC.

### B. Submit the Sitemap
1. In the left navigation of Google Search Console, click **Sitemaps**.
2. Under "Add a new sitemap", type: `sitemap.xml`
3. The full URL submitted will be: `https://coparentingsg.org/sitemap.xml`
4. Click **Submit**.
5. The status should switch to **"Success"** within a few minutes.

### C. Request Immediate Crawling via URL Inspection
1. At the top search bar of Google Search Console ("Inspect any URL in coparentingsg.org"), enter:
   `https://coparentingsg.org/`
2. Press Enter.
3. You will likely see: *"URL is not on Google"*.
4. Click **Test Live URL** (takes ~30-45 seconds to verify Googlebot can load the page without errors).
5. Once verified green, click **Request Indexing**.
6. Repeat for `https://www.coparentingsg.org/` if desired.

---

## 5. Expected Indexing Timeline & How to Check

- **Googlebot Visit:** Typically occurs within **24 to 72 hours** after submitting the sitemap and requesting indexing.
- **Search Appearance:** First appears for brand queries like:
  - `site:coparentingsg.org` (shows all indexed pages from your domain)
  - `"coparentingsg"` or `"CoParenting SG"`
- **Target Keyword Rankings:** Rankings for terms like *"coparenting Singapore"*, *"Singapore parenting plan"*, and *"child custody access schedules Singapore"* build authority over 2 to 4 weeks as the page is evaluated.

---

## 6. Verification Checklist

- [ ] Repository committed and pushed to GitHub
- [ ] Vercel deployment status shows green (Production)
- [ ] `https://coparentingsg.org` opens securely over HTTPS in browser
- [ ] `https://coparentingsg.org/robots.txt` loads and displays the sitemap link
- [ ] `https://coparentingsg.org/sitemap.xml` loads cleanly
- [ ] Domain verified in Google Search Console
- [ ] `sitemap.xml` submitted under GSC Sitemaps
- [ ] URL Inspection → "Request Indexing" submitted for `https://coparentingsg.org/`
