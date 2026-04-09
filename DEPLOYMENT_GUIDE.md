# Portfolio Deployment Guide

Complete walkthrough for deploying your portfolio to GitHub Pages, Vercel, or Netlify.

---

## 📋 Pre-Deployment Checklist

Before deploying, ensure you've updated:

- [ ] Personal email in contact section
- [ ] Phone number in contact section
- [ ] GitHub username in all links
- [ ] LinkedIn profile URL
- [ ] Project live demo URLs
- [ ] Project GitHub repository URLs
- [ ] Replace `nadeem.merchant@example.com` with your real email
- [ ] Update `+91 98765 43210` with your real phone

---

## 🚀 Option 1: GitHub Pages (Recommended for Beginners)

**Pros:** Free, simple, GitHub-integrated  
**Cons:** Static sites only (perfect for this portfolio)

### Step 1: Create GitHub Repository

```bash
# Navigate to your portfolio folder
cd /path/to/portfolio

# Initialize git (if not already done)
git init

# Add all files
git add .

# Commit
git commit -m "Initial portfolio commit"

# Create repository on GitHub
# Go to: https://github.com/new
# Repository name: portfolio (or portfolio-website)
# Keep it public
# Don't initialize with README (you already have one)

# Connect local repo to GitHub
git remote add origin https://github.com/nadeem12-cloud/portfolio.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 2: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. Scroll to **Pages** (left sidebar)
4. Under **Source**:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**
6. Wait 2-3 minutes for deployment

### Step 3: Access Your Site

Your portfolio will be live at:
```
https://nadeem12-cloud.github.io/portfolio/
```

**Note:** If your repo name is exactly your username (e.g., `nadeem12-cloud.github.io`), the URL will be:
```
https://nadeem12-cloud.github.io/
```

### Step 4: Custom Domain (Optional)

If you have a custom domain (e.g., `nadeemmerchant.dev`):

1. In GitHub Pages settings, add your domain to **Custom domain**
2. In your domain registrar (GoDaddy, Namecheap, etc.):
   - Add A records pointing to GitHub IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - Or add CNAME record: `nadeem12-cloud.github.io`

---

## 🚀 Option 2: Vercel (Recommended for Speed)

**Pros:** Instant deployments, preview URLs, fast CDN  
**Cons:** Requires account signup

### Method A: Via Vercel Dashboard

1. Go to [vercel.com](https://vercel.com)
2. Sign up with GitHub
3. Click **Add New Project**
4. Import your `portfolio` repository
5. Settings:
   - Framework Preset: **Other**
   - Build Command: (leave empty)
   - Output Directory: (leave empty)
6. Click **Deploy**

Your site will be live at: `portfolio-username.vercel.app`

### Method B: Via Vercel CLI

```bash
# Install Vercel CLI
npm i -g vercel

# Navigate to portfolio folder
cd /path/to/portfolio

# Deploy
vercel

# Follow prompts:
# - Set up and deploy? Y
# - Which scope? (select your account)
# - Link to existing project? N
# - What's your project's name? portfolio
# - In which directory is your code located? ./
# - Auto-detected settings, continue? Y

# Your site is now deployed!
# Production URL will be shown

# For custom domain:
vercel --prod
vercel domains add nadeemmerchant.dev
```

---

## 🚀 Option 3: Netlify

**Pros:** Drag-and-drop, forms backend, split testing  
**Cons:** Build minutes limit on free plan

### Method A: Drag & Drop

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag your **portfolio folder** to the upload area
3. Wait for deployment
4. Site is live at: `random-name-123.netlify.app`
5. Click **Site settings** > **Change site name** to customize

### Method B: Git Integration

1. Go to [app.netlify.com](https://app.netlify.com)
2. Click **Add new site** > **Import an existing project**
3. Connect to GitHub
4. Select your `portfolio` repository
5. Build settings:
   - Build command: (leave empty)
   - Publish directory: (leave empty)
6. Click **Deploy**

---

## 🔧 Post-Deployment Tasks

### 1. Update README with Live URL

In your `README.md`:
```markdown
**Live Demo:** https://your-deployed-url.com
```

### 2. Update Portfolio Links in Project READMEs

Go to your project repositories (CareerIQ, IPL Predictor, Digital Mushayara) and add:
```markdown
**Developer Portfolio:** https://your-deployed-url.com
```

### 3. Pin Repository on GitHub

1. Go to your GitHub profile
2. Click **Customize your pins**
3. Select `portfolio` repository
4. Save

### 4. Add Website to GitHub Profile

1. Edit your GitHub profile
2. Add your portfolio URL to **Website** field

---

## 📱 Add to LinkedIn

### Option 1: Featured Section

1. Go to your LinkedIn profile
2. Scroll to **Featured** section
3. Click **Add featured** > **Link**
4. URL: `https://your-deployed-url.com`
5. Title: `My Developer Portfolio`
6. Description: See LinkedIn post template below

### Option 2: LinkedIn Post

Create a new post with this template:

```
🚀 Excited to share my new portfolio website!

After months of building ML models, deploying full-stack apps, and shipping real projects, I've finally created a space to showcase my work.

What's inside:
✅ IPL Match Predictor (XGBoost + SHAP explainability)
✅ CareerIQ (NLP-powered job search, 30k+ listings)
✅ Digital Mushayara (React poetry platform with analytics)
✅ Live demos, code walkthroughs, and case studies

Built from scratch with HTML/CSS/JS — no templates, no frameworks, just clean code and bold design.

🔗 Check it out: [YOUR_URL]

Would love to hear your feedback! 💬

#WebDevelopment #MachineLearning #Portfolio #DataScience #Python #React #OpenToWork

---

P.S. Special thanks to everyone who's supported my journey so far. Looking forward to connecting with fellow developers and exploring opportunities! 🙏
```

### Option 3: Update LinkedIn About Section

Add this to your **About** section:
```
📍 Portfolio: https://your-deployed-url.com
```

---

## 🎯 SEO Optimization (Post-Deployment)

### 1. Submit to Google Search Console

1. Go to [search.google.com/search-console](https://search.google.com/search-console)
2. Add property: `https://your-deployed-url.com`
3. Verify ownership (HTML tag method)
4. Submit sitemap (if you create one)

### 2. Generate Sitemap (Optional)

Create `sitemap.xml`:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://your-deployed-url.com/</loc>
    <lastmod>2025-04-08</lastmod>
    <priority>1.0</priority>
  </url>
</urlset>
```

### 3. Add robots.txt

Create `robots.txt`:
```
User-agent: *
Allow: /

Sitemap: https://your-deployed-url.com/sitemap.xml
```

---

## 🐛 Troubleshooting

### GitHub Pages 404 Error
- Check if repo is public
- Ensure branch is `main` not `master`
- Wait 5-10 minutes after enabling

### Vercel Build Failed
- Ensure no `package.json` in root (remove if present)
- Check build logs in Vercel dashboard

### Netlify Forms Not Working
- Add `netlify` attribute to form tag
- Add hidden input: `<input type="hidden" name="form-name" value="contact">`

### Custom Domain Not Working
- Check DNS propagation (can take 24-48 hours)
- Use [dnschecker.org](https://dnschecker.org) to verify
- Ensure HTTPS is enabled in settings

---

## 📊 Analytics (Optional)

### Google Analytics 4

1. Create account at [analytics.google.com](https://analytics.google.com)
2. Add tracking code before `</head>`:
```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Plausible (Privacy-Friendly Alternative)

1. Sign up at [plausible.io](https://plausible.io)
2. Add script before `</head>`:
```html
<script defer data-domain="yourdomain.com" src="https://plausible.io/js/script.js"></script>
```

---

## ✅ Final Deployment Checklist

- [ ] All personal information updated
- [ ] All project links working
- [ ] Responsive design tested on mobile
- [ ] Lighthouse audit passed (90+ scores)
- [ ] Site deployed and accessible
- [ ] Custom domain configured (if applicable)
- [ ] README updated with live URL
- [ ] GitHub profile updated
- [ ] LinkedIn profile updated
- [ ] LinkedIn post published
- [ ] Analytics configured (optional)
- [ ] Sitemap submitted to Google (optional)

---

**Congratulations! Your portfolio is now live! 🎉**

Share it with the world and start attracting opportunities!
