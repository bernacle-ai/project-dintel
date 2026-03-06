# Simple Upload System - No Authentication Required

## What You Got

A completely client-side presentation upload system that works without any backend, authentication, or database. Everything is stored in the browser's localStorage.

## How It Works

1. **Upload Page** (`upload.html`) - Drag & drop or click to upload PPT files
2. **Presentations Page** (`presentations.html`) - View and download all uploaded presentations
3. **Main Site** (`index.html`) - Has buttons to access both pages

## Features

✅ **No Authentication** - Anyone can upload (perfect for internal use)  
✅ **No Backend** - Pure client-side JavaScript  
✅ **No Database** - Uses browser localStorage  
✅ **Drag & Drop** - Modern file upload interface  
✅ **Instant Upload** - No server processing needed  
✅ **Download Anytime** - Click to download any presentation  

## How to Use

### For You/Co-Founder:

1. **Open your site** (index.html)
2. **Click "⬆ Upload PPT"** button in navigation
3. **Fill in**:
   - Title (e.g., "Founder POC Q1 2025")
   - Description (optional)
   - Drag & drop your PPT file or click to browse
4. **Click "Upload Presentation"**
5. **Done!** It's saved instantly

### To View Presentations:

1. Click **"📊 Presentations"** in navigation
2. See all uploaded presentations
3. Click **"Download PPT"** to get the file

## Important Notes

### Storage Limits

- Browser localStorage has a limit of ~5-10MB
- Each PPT file should be under 5MB for best results
- If you need to store larger files, consider using a backend

### Data Persistence

- Data is stored in the browser's localStorage
- Data persists even after closing the browser
- Data is specific to the domain (e.g., yoursite.com)
- Clearing browser data will delete all presentations

### Sharing Between Users

Since this uses localStorage, each user's browser has its own storage:
- **Same computer, same browser** = Same presentations
- **Different computer** = Different presentations
- **Different browser** = Different presentations

### For Team Use

If you want all team members to see the same presentations, you have two options:

**Option A: Use One Computer**
- Set up one computer as the "upload station"
- Everyone uses that computer to upload/view

**Option B: Upgrade to Backend**
- Deploy to Netlify (free)
- Enable Git Gateway
- Use the `/admin` CMS panel
- All uploads sync via Git

## File Structure

```
website/
├── index.html              # Main site (has upload button)
├── upload.html             # Upload page (drag & drop interface)
├── presentations.html      # View all presentations
├── admin/                  # CMS (optional, for backend sync)
│   ├── index.html
│   └── config.yml
└── uploads/                # (not used in localStorage mode)
```

## Deployment

### GitHub Pages

1. Push to GitHub
2. Enable GitHub Pages in repo settings
3. Your site is live!
4. Upload page works immediately (no setup needed)

### Any Static Host

Works on:
- GitHub Pages
- Netlify
- Vercel
- Hostinger
- Any web server

Just upload the files and it works!

## Troubleshooting

### "Upload button doesn't work"
- Make sure JavaScript is enabled in browser
- Check browser console for errors (F12)

### "Presentations not showing"
- Make sure you're on the same browser/computer where you uploaded
- Check if localStorage is enabled (some browsers block it in private mode)

### "File too large"
- Keep PPT files under 5MB
- Compress images in your PowerPoint
- Or upgrade to backend storage

### "Lost all presentations"
- Browser data was cleared
- Using different browser/computer
- Solution: Use backend (Netlify + Git Gateway) for permanent storage

## Upgrade Path

When you're ready for team-wide access:

1. Deploy to Netlify (free)
2. Enable Identity + Git Gateway
3. Use `/admin` panel instead of `/upload.html`
4. All uploads sync to Git repository
5. Everyone sees the same presentations

See `GITHUB_PAGES_SETUP.md` for backend setup instructions.

## Summary

- **Current Setup**: Client-side only, localStorage, no auth
- **Perfect For**: Single user or same-computer access
- **Upgrade When**: You need multi-user sync or larger files
- **Cost**: $0 (completely free)

---

**You're ready to upload!** Just open `upload.html` and start uploading presentations.
