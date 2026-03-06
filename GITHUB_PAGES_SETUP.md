# GitHub Pages + CMS Setup Guide

## The Simplest Way (Recommended)

### Option 1: Use Netlify Instead (5 minutes, zero config)

GitHub Pages + CMS is complex. Netlify is free and handles everything automatically:

1. **Push your code to GitHub** (you already did this)
2. **Go to**: https://app.netlify.com/signup
3. **Sign up** with GitHub
4. **Click**: "Add new site" → "Import an existing project"
5. **Select**: Your `bernacle-ai/project-dintel` repo
6. **Deploy settings**:
   - Branch: `master`
   - Build command: (leave empty)
   - Publish directory: `/`
7. **Click**: "Deploy site"
8. **Done!** Your site is live at: `https://[random-name].netlify.app`

### Enable CMS on Netlify (2 minutes)

1. In Netlify Dashboard → **Site Settings** → **Identity**
2. Click **"Enable Identity"**
3. Under **Registration**, select **"Invite only"**
4. Scroll down → **Services** → **Git Gateway**
5. Click **"Enable Git Gateway"**
6. **Done!**

### Access Your Admin Panel

1. Go to: `https://[your-site].netlify.app/admin`
2. Click **"Sign up"** (first time only)
3. Check your email → Click confirmation link
4. Set password → Login
5. **You'll see the upload interface!**

---

## Option 2: GitHub Pages (More Complex)

If you must use GitHub Pages, follow these steps:

### Step 1: Enable GitHub Pages

1. Go to: https://github.com/bernacle-ai/project-dintel/settings/pages
2. Under **Source**: Select branch `master` → folder `/ (root)`
3. Click **Save**
4. Wait 2-3 minutes
5. Your site: `https://bernacle-ai.github.io/project-dintel/`

### Step 2: Use GitHub Backend (No Git Gateway Needed)

Your `admin/config.yml` is already configured for GitHub backend.

### Step 3: Authenticate with GitHub

When you visit `/admin`, you'll be asked to:

1. **Authorize with GitHub** (one-time)
2. Grant Decap CMS access to your repo
3. You'll be redirected back to admin panel

### Step 4: Upload Presentations

1. Go to: `https://bernacle-ai.github.io/project-dintel/admin`
2. Click **"Login with GitHub"**
3. Authorize the app
4. Click **"Presentations"** in sidebar
5. Click **"New Presentation"**
6. You'll see:
   - Title field
   - **File upload button** (click to upload PPT)
   - Description field
   - Date picker
7. Click **"Publish"**

---

## Why You Don't See Upload Button

The upload button appears AFTER you:
1. Login to `/admin`
2. Click "Presentations" collection
3. Click "New Presentation"
4. The file upload widget appears in the form

## Troubleshooting

### "Can't access /admin"
- Make sure GitHub Pages is enabled
- Wait 2-3 minutes for deployment
- Try: `https://bernacle-ai.github.io/project-dintel/admin/`

### "No upload button"
- You need to login first
- Click "Login with GitHub"
- Then create new presentation
- The upload field will appear

### "Authentication error"
- Clear browser cache
- Try incognito mode
- Make sure you're logged into GitHub

---

## My Recommendation

**Use Netlify** (Option 1). It's:
- ✅ Free forever
- ✅ Faster than GitHub Pages
- ✅ Automatic HTTPS
- ✅ No OAuth setup needed
- ✅ Built-in CMS authentication
- ✅ Instant deploys on git push
- ✅ Better for your co-founder (simpler login)

GitHub Pages works but requires more setup and the authentication flow is clunkier.

---

## Next Steps

1. **Choose**: Netlify (easy) or GitHub Pages (complex)
2. **Deploy** your site
3. **Enable Identity** (Netlify) or **Login with GitHub** (Pages)
4. **Go to** `/admin`
5. **Upload** your first presentation

Need help? The upload button is inside the "New Presentation" form after you login.

