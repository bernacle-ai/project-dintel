# CMS Setup Guide — Presentation Upload System

## What You Got

Your site now has a complete CMS workflow for uploading and managing PowerPoint presentations without any backend server.

## Folder Structure

```
website/
│
├── index.html                    # Main site (updated with Presentations link)
├── presentations.html            # Presentations viewer page
│
├── admin/
│   ├── index.html               # CMS admin panel
│   └── config.yml               # CMS configuration
│
├── presentations/               # PPT metadata stored here
│   └── .gitkeep
│
└── uploads/                     # Uploaded PPT files stored here
    └── .gitkeep
```

## How It Works

1. **You/Co-Founder** → Access `/admin`
2. **Login** → Upload PPT via dashboard
3. **Git saves it** → Auto-commits to repository
4. **Site updates** → Presentations appear on `/presentations.html`

## Setup Steps

### Step 1: Enable Git Gateway (Required for CMS)

You need to connect your Git repository to Decap CMS. Choose your hosting:

#### Option A: Netlify (Recommended — Easiest)

1. Push your code to GitHub/GitLab
2. Deploy to Netlify (drag & drop or connect repo)
3. Go to Netlify Dashboard → Site Settings → Identity
4. Click "Enable Identity"
5. Under Registration preferences, select "Invite only"
6. Go to Services → Git Gateway → Enable Git Gateway
7. Done! Access your admin at: `yoursite.netlify.app/admin`

#### Option B: GitHub Pages + Netlify Identity

1. Host your site on GitHub Pages
2. Create a free Netlify account
3. Add Netlify Identity widget to your site
4. Follow Netlify Identity setup (same as Option A)

#### Option C: Self-Hosted with GitHub OAuth

More complex — requires OAuth app setup. See: https://decapcms.org/docs/github-backend/

### Step 2: Create Your First Admin User

1. Go to `/admin` on your deployed site
2. Click "Sign up" (first time only)
3. Check your email for confirmation
4. Set your password
5. You're in!

### Step 3: Upload a Presentation

1. Login to `/admin`
2. Click "Presentations" in sidebar
3. Click "New Presentation"
4. Fill in:
   - **Title**: e.g., "Founder POC Q1 2025"
   - **Upload PPT**: Click to upload your .pptx file
   - **Description**: Optional summary
   - **Date**: Auto-filled
5. Click "Publish"
6. Done! It's now live on `/presentations.html`

### Step 4: View Presentations

- Public page: `yoursite.com/presentations.html`
- Click any presentation to view in Microsoft Office Online Viewer
- No downloads required — viewers see it in-browser

## Admin Panel Features

Your `/admin` dashboard allows:

- ✅ Upload PPT files
- ✅ Edit presentation metadata
- ✅ Delete presentations
- ✅ Preview before publishing
- ✅ Version control (Git history)
- ✅ Multi-user access (invite team members)

## Accessing the Admin

- **URL**: `yoursite.com/admin`
- **Login**: Email + Password (via Netlify Identity)
- **Invite Co-Founder**: Netlify Dashboard → Identity → Invite users

## Customization

### Add More Fields

Edit `admin/config.yml`:

```yaml
fields:
  - { label: "Title", name: "title", widget: "string" }
  - { label: "Upload PPT", name: "file", widget: "file" }
  - { label: "Category", name: "category", widget: "select", options: ["Founder", "Marketing", "Client"] }
  - { label: "Tags", name: "tags", widget: "list" }
```

### Change Upload Folder

Edit `admin/config.yml`:

```yaml
media_folder: "uploads"        # Change to "assets/presentations"
public_folder: "/uploads"      # Change to "/assets/presentations"
```

## Why This Method Is Powerful

✅ **No Backend Server** — Pure static hosting  
✅ **Git Version Control** — Every upload is tracked  
✅ **Free Hosting** — Works on Netlify, GitHub Pages, Hostinger  
✅ **Non-Technical Users** — Co-founders can upload without coding  
✅ **Secure** — Netlify Identity handles authentication  
✅ **Fast** — CDN-delivered, no database queries  

## Troubleshooting

### "Unable to access admin"
- Make sure you've enabled Git Gateway in Netlify
- Check that Identity is enabled
- Clear browser cache and try again

### "Uploads not appearing"
- Check Git repository — files should be in `/uploads`
- Verify `config.yml` paths match your folder structure
- Ensure site is deployed (changes need to be pushed to Git)

### "Can't view PPT"
- Microsoft Office Viewer requires publicly accessible URLs
- Make sure your site is deployed (not localhost)
- Check that file uploaded correctly to `/uploads`

## Next Steps

1. Deploy your site to Netlify/GitHub Pages
2. Enable Git Gateway
3. Create admin account
4. Upload your first presentation
5. Share `/presentations.html` with your team

## Support

- Decap CMS Docs: https://decapcms.org/docs/
- Netlify Identity: https://docs.netlify.com/visitor-access/identity/

---

**You're all set!** Your co-founder can now upload presentations without touching code.
