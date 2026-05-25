# 🚀 Complete Deployment Guide: GitHub → Vercel

This guide walks you through deploying your portfolio to Vercel from GitHub.

## 📋 Prerequisites

You'll need:
- GitHub account (free at github.com)
- Vercel account (free at vercel.com)
- Your domain (pragma-gtm.com) from Namecheap
- Git installed locally (optional, can use GitHub web)

---

## PART 1: CREATE GITHUB REPOSITORY

### Option A: Using GitHub Web Interface (Easiest)

**Step 1:** Create Repository
1. Go to https://github.com/new
2. Repository name: `pragma-gtm`
3. Description: `GTM Engineer Portfolio - Yuval Gross`
4. Select "Public" (required for free Vercel)
5. ✅ Check "Add a README file"
6. Click "Create repository"

**Step 2:** Upload Files
1. Click "Add file" → "Upload files"
2. Drag & drop all files from this folder:
   - index.html
   - og-image.png
   - robots.txt
   - sitemap.xml
   - GTM_-_Yuval_Gross.pdf
   - vercel.json
   - .gitignore
   - README.md
3. Click "Commit changes"

Done! Your files are on GitHub. ✅

---

### Option B: Using Git Command Line (For Developers)

**Step 1:** Install Git
```bash
# macOS
brew install git

# Ubuntu/Debian
sudo apt install git

# Windows
# Download from git-scm.com
```

**Step 2:** Initialize Local Repository
```bash
cd /path/to/pragma-gtm-github
git init
git add .
git commit -m "Initial commit: GTM portfolio by Yuval Gross"
git branch -M main
```

**Step 3:** Create Repository on GitHub
1. Go to https://github.com/new
2. Repository name: `pragma-gtm`
3. Do NOT initialize with README (you already have files)
4. Click "Create repository"

**Step 4:** Connect & Push
```bash
git remote add origin https://github.com/YOUR_USERNAME/pragma-gtm.git
git push -u origin main
```

Replace `YOUR_USERNAME` with your GitHub username.

Done! Your files are on GitHub. ✅

---

## PART 2: DEPLOY TO VERCEL

### Step 1: Create Vercel Account
1. Go to https://vercel.com/signup
2. Click "Continue with GitHub"
3. Authorize Vercel to access GitHub
4. Complete signup

### Step 2: Create New Project
1. Go to https://vercel.com/new
2. Select your `pragma-gtm` repository
3. Vercel auto-detects it's a static site
4. Settings should show:
   - Framework: None (detected)
   - Root Directory: ./
   - Build Command: (empty)
   - Output Directory: ./
5. Click "Deploy"

**Wait 30 seconds...** Your site is live! 🎉

You'll get a URL like: `https://pragma-gtm.vercel.app`

### Step 3: Verify Deployment
1. Visit your Vercel URL
2. Test all features:
   - ✅ Animations work
   - ✅ Responsive on mobile
   - ✅ Dark/light mode toggles
   - ✅ CV download works
   - ✅ Links work

---

## PART 3: CONNECT CUSTOM DOMAIN

### Step 1: Add Domain to Vercel
1. In Vercel Dashboard → Your Project → Settings
2. Go to "Domains" tab
3. Enter: `pragma-gtm.com`
4. Click "Add"
5. Vercel shows options:
   - **Option A:** Use Vercel's nameservers (recommended)
   - **Option B:** Add CNAME record manually

### Step 2A: Using Vercel Nameservers (Easiest)

**In Vercel Dashboard:**
1. Copy the nameservers Vercel provides:
   - `ns1.vercel-dns.com`
   - `ns2.vercel-dns.com`

**In Namecheap Dashboard:**
1. Go to Your Domains
2. Click "Manage" on pragma-gtm.com
3. Go to "Nameservers" tab
4. Select "Custom DNS"
5. Replace with Vercel nameservers:
   ```
   ns1.vercel-dns.com
   ns2.vercel-dns.com
   ```
6. Save changes
7. Wait 24-48 hours for propagation

### Step 2B: Using CNAME Records (If Keeping Cloudflare)

**In Vercel Dashboard:**
1. Select "Add a CNAME record"
2. Copy the CNAME target

**In Namecheap Dashboard:**
1. Go to DNS settings
2. Add CNAME record:
   ```
   Name: pragma-gtm
   Type: CNAME
   Value: (Vercel's CNAME target)
   TTL: 30 min (or auto)
   ```
3. Save changes
4. Wait 30 minutes - 2 hours

### Step 3: Verify Domain
After 24-48 hours:
1. Visit `https://pragma-gtm.com`
2. Should show your portfolio (green checkmark in Vercel)
3. HTTPS should work automatically
4. og-image.png should be accessible

✅ Domain connected!

---

## PART 4: TEST SOCIAL SHARING

Your og-image.png is now live and ready for social sharing.

### Test on LinkedIn
1. Go to https://www.linkedin.com/feed/
2. Start a post
3. Paste: `https://pragma-gtm.com`
4. Preview shows your custom og-image.png
5. Post it! 🎉

### Test on Twitter
1. Go to https://twitter.com/compose/tweet
2. Paste: `https://pragma-gtm.com`
3. Preview shows your custom og-image.png
4. Tweet it! 🎉

### Test with Tools
- https://www.opengraph.xyz/url/pragma-gtm.com
- https://www.linkedin.com/post-inspector/
- https://twittercommunity.com/t/twitter-card-validator-disappears/164214 (use X.com instead)

---

## 📊 VERCEL DASHBOARD GUIDE

After deployment, explore:

### Overview Tab
- Current deployment status (green = live)
- Deployment history
- Last commit info
- Production URL

### Deployments Tab
- All deployment history
- Rollback options (revert to previous)
- Deployment logs
- Build time

### Settings Tab
- **Domains:** Manage custom domains
- **Environment:** Environment variables (if needed)
- **Advanced:** Cache behavior, security

### Analytics Tab (Pro Feature)
- View count
- Top pages
- Referrers
- Browsers/OS

---

## 🔄 UPDATING YOUR SITE

After initial deployment, updating is easy:

### Make Changes Locally
```bash
cd /path/to/pragma-gtm-github
# Edit index.html (or other files)
```

### Commit & Push
```bash
git add .
git commit -m "Update: Added new experience"
git push
```

### Automatic Deployment
- Vercel sees your push
- Auto-builds and deploys (takes 30-60 seconds)
- Your site updates automatically
- No manual deployment needed

---

## 🚨 TROUBLESHOOTING

### Site Not Loading
- Clear browser cache (Ctrl+Shift+Delete)
- Wait 5 minutes (sometimes slower)
- Check Vercel deployment status (green checkmark?)
- Try incognito window

### Custom Domain Not Working
- Check Nameservers propagated:
  - https://whatsmydns.net/?domain=pragma-gtm.com
  - Most should show green ✅
- Wait up to 48 hours (DNS is slow)
- Verify Namecheap shows correct nameservers

### og-image.png Not Showing in Social
- Check image exists: https://pragma-gtm.com/og-image.png
- Clear social site cache (harder)
- Use debuggers:
  - LinkedIn: https://www.linkedin.com/post-inspector/
  - Twitter: Use card validator
- Wait 24 hours (social sites cache)

### Performance Issues
- Check Vercel Analytics
- Verify no heavy scripts added
- Test with Lighthouse: https://pagespeed.web.dev/

---

## ✅ VERIFICATION CHECKLIST

Before considering deployment complete:

- [ ] GitHub repository created
- [ ] All files pushed to GitHub
- [ ] Vercel project created
- [ ] Vercel shows green checkmark
- [ ] Site loads at vercel.app URL
- [ ] Dark/light mode works
- [ ] Animations play smoothly
- [ ] CV download works
- [ ] Mobile responsive works
- [ ] Custom domain added to Vercel
- [ ] DNS updated at Namecheap
- [ ] Custom domain resolves (after 24-48h)
- [ ] og-image.png accessible
- [ ] Social sharing shows preview
- [ ] HTTPS working (green lock icon)
- [ ] robots.txt accessible
- [ ] sitemap.xml accessible

---

## 📞 SUPPORT

If you get stuck:

**Vercel Support:**
- Docs: https://vercel.com/docs
- Community: https://github.com/vercel/vercel/discussions

**GitHub Support:**
- Docs: https://docs.github.com
- Community: https://github.community

**Your DNS (Namecheap):**
- Docs: https://www.namecheap.com/support/
- Live chat available

---

## 🎉 YOU'RE DONE!

Your portfolio is now:
- ✅ Live on custom domain
- ✅ Fast global CDN
- ✅ Automatically deploys on push
- ✅ Professional hosting
- ✅ Free forever (for static sites)
- ✅ SEO optimized
- ✅ Social sharing ready

Congratulations! 🚀

---

**Last Updated:** May 23, 2026  
**For:** Yuval Gross GTM Portfolio  
**Hosting:** Vercel + GitHub
