# 🚀 KnowledgeWall Deployment Guide

Complete instructions for deploying the KnowledgeWall Retro Design System to GitHub Pages or Vercel.

---

## 📋 Table of Contents

1. [Option 1: GitHub Pages (Recommended)](#option-1-github-pages-recommended)
2. [Option 2: Vercel](#option-2-vercel)
3. [Local Development](#local-development)
4. [Troubleshooting](#troubleshooting)

---

## Option 1: GitHub Pages (Recommended)

GitHub Pages is **free**, simple, and perfect for static HTML/CSS projects like this.

### Step 1: Enable GitHub Pages

1. **Go to your GitHub repository:**
   ```
   https://github.com/Ti04ti/Wallpaper-wisdom-
   ```

2. **Click on "Settings"** (top navigation)

3. **Scroll down to "Pages"** (left sidebar)

4. **Configure Source:**
   - **Source:** Select "Deploy from a branch"
   - **Branch:** Select `claude/retro-ui-design-011CUVfknvvu8hJihAsJaQXW`
   - **Folder:** Select `/ (root)`

5. **Click "Save"**

6. **Wait 1-2 minutes** for deployment

7. **Your site will be live at:**
   ```
   https://ti04ti.github.io/Wallpaper-wisdom-/
   ```

### Step 2: Access Your Demos

Once deployed, you can access:

- **Landing Page:** https://ti04ti.github.io/Wallpaper-wisdom-/
- **Wallpaper Generator:** https://ti04ti.github.io/Wallpaper-wisdom-/wallpaper-template-retro.html
- **Component Library:** https://ti04ti.github.io/Wallpaper-wisdom-/retro-components-examples.html
- **Design System Docs:** https://ti04ti.github.io/Wallpaper-wisdom-/retro-design-system.md

### Step 3: Merge to Main (Optional)

If you want the site on the main branch instead:

1. **Merge your branch to main:**
   ```bash
   git checkout main
   git merge claude/retro-ui-design-011CUVfknvvu8hJihAsJaQXW
   git push origin main
   ```

2. **Update GitHub Pages settings:**
   - Change branch from `claude/retro-ui-design-011CUVfknvvu8hJihAsJaQXW` to `main`

### GitHub Pages Benefits

✅ **Free forever**
✅ **No configuration needed**
✅ **Automatic HTTPS**
✅ **Fast CDN**
✅ **Perfect for static sites**
✅ **No limits for public repos**

---

## Option 2: Vercel

Vercel offers faster builds, preview deployments, and analytics.

### Step 1: Sign Up / Login to Vercel

1. Go to [vercel.com](https://vercel.com)
2. Sign up with GitHub (recommended)

### Step 2: Import Your Repository

**Method A: Using Vercel Dashboard**

1. Click **"Add New..."** → **"Project"**
2. Select **"Import Git Repository"**
3. Search for `Wallpaper-wisdom-`
4. Click **"Import"**
5. Configure:
   - **Project Name:** `knowledgewall-retro` (or your choice)
   - **Framework Preset:** Other
   - **Root Directory:** `./`
   - **Build Command:** (leave empty for static site)
   - **Output Directory:** `./`
6. Click **"Deploy"**

**Method B: Using Vercel CLI**

```bash
# Install Vercel CLI
npm install -g vercel

# Navigate to your project
cd /path/to/Wallpaper-wisdom-

# Deploy
vercel

# Follow the prompts:
# Set up and deploy? [Y/n] Y
# Which scope? (select your account)
# Link to existing project? [y/N] N
# What's your project's name? knowledgewall-retro
# In which directory is your code located? ./
# Want to override the settings? [y/N] N

# Your project is now deployed!
```

### Step 3: Access Your Deployment

After deployment, Vercel will provide URLs:

- **Production:** `https://knowledgewall-retro.vercel.app`
- **Preview:** `https://knowledgewall-retro-git-<branch>.vercel.app`

### Step 4: Custom Domain (Optional)

1. Go to your project in Vercel Dashboard
2. Click **"Settings"** → **"Domains"**
3. Add your custom domain
4. Update DNS records as instructed

### Vercel Benefits

✅ **Automatic deployments** on git push
✅ **Preview deployments** for every branch
✅ **Analytics** and performance monitoring
✅ **Custom domains** with automatic SSL
✅ **Edge network** (faster globally)
✅ **Free tier** for personal projects

---

## Local Development

To run the project locally:

### Option 1: Python HTTP Server

```bash
# Navigate to project directory
cd /path/to/Wallpaper-wisdom-

# Python 3
python3 -m http.server 8000

# Open browser
# http://localhost:8000
```

### Option 2: Node.js HTTP Server

```bash
# Install http-server globally
npm install -g http-server

# Navigate to project directory
cd /path/to/Wallpaper-wisdom-

# Start server
http-server -p 8000

# Open browser
# http://localhost:8000
```

### Option 3: VS Code Live Server

1. Install **Live Server** extension
2. Right-click `index.html`
3. Select **"Open with Live Server"**

### Option 4: Just Open the File

For basic testing:

```bash
# On macOS
open index.html

# On Linux
xdg-open index.html

# On Windows
start index.html
```

**Note:** Some features (like fonts) work better with a local server.

---

## 📁 Project Structure

```
Wallpaper-wisdom-/
├── index.html                      # Landing page
├── wallpaper-template-retro.html   # Wallpaper generator
├── retro-components-examples.html  # Component library
├── retro-styles.css                # Main stylesheet
├── retro-theme-config.json         # Theme configuration
├── retro-design-system.md          # Documentation
├── vercel.json                     # Vercel configuration
├── .nojekyll                       # GitHub Pages config
├── DEPLOYMENT.md                   # This file
└── README.md                       # Project README
```

---

## 🔧 Configuration Files

### `.nojekyll`

This empty file tells GitHub Pages to:
- Not process files with Jekyll
- Serve files as-is
- Allow files/folders starting with `_`

### `vercel.json`

Configures Vercel deployment:
- Static file serving
- Caching headers
- Route configuration

---

## 🌐 URLs Reference

### GitHub Pages URLs

```
Main Site:        https://ti04ti.github.io/Wallpaper-wisdom-/
Wallpaper Gen:    https://ti04ti.github.io/Wallpaper-wisdom-/wallpaper-template-retro.html
Components:       https://ti04ti.github.io/Wallpaper-wisdom-/retro-components-examples.html
Design Docs:      https://ti04ti.github.io/Wallpaper-wisdom-/retro-design-system.md
Stylesheet:       https://ti04ti.github.io/Wallpaper-wisdom-/retro-styles.css
Config JSON:      https://ti04ti.github.io/Wallpaper-wisdom-/retro-theme-config.json
```

### Vercel URLs (Example)

```
Production:       https://knowledgewall-retro.vercel.app
Preview:          https://knowledgewall-retro-git-<branch>.vercel.app
```

---

## 🐛 Troubleshooting

### GitHub Pages

**Problem:** 404 Page Not Found
- **Solution:** Ensure you've selected the correct branch and folder in Settings → Pages
- **Check:** Wait 2-3 minutes after enabling Pages
- **Verify:** Check the Actions tab for build status

**Problem:** Styles not loading
- **Solution:** The `.nojekyll` file should be in the root directory
- **Check:** Ensure all CSS paths are relative (no leading `/`)

**Problem:** Fonts not displaying
- **Solution:** Google Fonts CDN should work. Check browser console for errors

### Vercel

**Problem:** Build fails
- **Solution:** Vercel works best with framework projects. For static sites:
  - Set Framework Preset to "Other"
  - Leave Build Command empty
  - Set Output Directory to `./`

**Problem:** Routes not working
- **Solution:** Check `vercel.json` is in root directory
- **Verify:** Routes are configured correctly

### Local Development

**Problem:** CORS errors
- **Solution:** Use a local server (http-server, Python, or Live Server)
- **Don't:** Open files directly with `file://` protocol for full functionality

**Problem:** Fonts not loading locally
- **Solution:** Run a local server to allow external resource loading

---

## 📱 Mobile Testing

### Test on Real Devices

1. **Deploy to GitHub Pages or Vercel**
2. **Open on your phone:**
   - Visit the deployment URL
   - Bookmark the wallpaper generator
   - Generate and download wallpapers
   - Set as wallpaper on your phone

### Test Locally on Mobile

1. **Find your local IP:**
   ```bash
   # macOS/Linux
   ifconfig | grep "inet "

   # Windows
   ipconfig
   ```

2. **Start local server:**
   ```bash
   python3 -m http.server 8000
   ```

3. **Access from phone:**
   ```
   http://YOUR_LOCAL_IP:8000
   # Example: http://192.168.1.100:8000
   ```

**Note:** Ensure your phone and computer are on the same WiFi network.

---

## 🎨 Customization

### Changing Themes

Edit `retro-styles.css`:
```css
:root {
  --color-bg-dark-void: #0A0A0F;
  --color-terminal-green: #00FF41;
  --color-neon-pink: #FF006E;
  /* ... more colors */
}
```

### Adding New Components

1. Study existing components in `retro-components-examples.html`
2. Follow the design system guidelines in `retro-design-system.md`
3. Use the retro CSS classes from `retro-styles.css`
4. Test across themes

### Modifying Wallpaper Layouts

Edit `wallpaper-template-retro.html`:
- Change dimensions in `.wallpaper-canvas`
- Adjust safe zones
- Modify content sections
- Update themes and colors

---

## 📊 Performance

### Optimization Tips

1. **Images:** This project uses no images (pure CSS)
2. **Fonts:** Google Fonts are cached by CDN
3. **CSS:** Single stylesheet, minified in production
4. **HTML:** Minimal inline styles, semantic markup

### Lighthouse Scores Target

- **Performance:** 95+
- **Accessibility:** 100
- **Best Practices:** 95+
- **SEO:** 90+

---

## 🔒 Security

All deployments use HTTPS:
- **GitHub Pages:** Automatic HTTPS
- **Vercel:** Automatic SSL certificates
- **No backend:** Static files only (no security vulnerabilities)

---

## 📞 Support

- **Issues:** [GitHub Issues](https://github.com/Ti04ti/Wallpaper-wisdom-/issues)
- **Documentation:** See `retro-design-system.md`
- **Examples:** See `retro-components-examples.html`

---

## ✅ Quick Start Checklist

For the fastest deployment:

- [ ] Push your code to GitHub
- [ ] Go to repo Settings → Pages
- [ ] Enable Pages on your branch
- [ ] Wait 2 minutes
- [ ] Visit your site at `https://ti04ti.github.io/Wallpaper-wisdom-/`
- [ ] Done! 🎉

---

**Version:** 1.0.0
**Last Updated:** October 26, 2025
**Status:** Ready for Deployment

▓▓▓ KNOWLEDGEWALL RETRO DESIGN SYSTEM ▓▓▓
