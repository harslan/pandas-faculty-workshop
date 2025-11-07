# 🌐 GitHub Pages Setup Guide

## Quick Setup Instructions for Publishing Your Workshop Website

---

## 📋 Prerequisites

- GitHub account (free at github.com)
- Your workshop materials downloaded
- 10 minutes of time

---

## 🚀 Step-by-Step Setup

### Step 1: Create a New GitHub Repository

1. Go to https://github.com
2. Click the **"+"** icon in the top right
3. Select **"New repository"**
4. Name it: `pandas-faculty-workshop` (or your preferred name)
5. Add description: "Pandas workshop for business school faculty"
6. Choose **Public** (required for free GitHub Pages)
7. ✅ Check "Add a README file"
8. Click **"Create repository"**

---

### Step 2: Upload Your Files

#### Option A: Web Upload (Easiest)

1. In your repository, click **"Add file"** → **"Upload files"**
2. Drag and drop ALL your workshop files:
   - `index.html` ⭐ (most important!)
   - All `.md` files
   - All `.ipynb` files
   - The `.zip` file
3. Add commit message: "Initial workshop materials upload"
4. Click **"Commit changes"**

#### Option B: Git Command Line

```bash
# Clone your repository
git clone https://github.com/YOUR-USERNAME/pandas-faculty-workshop.git
cd pandas-faculty-workshop

# Copy all your workshop files here
# Then:
git add .
git commit -m "Initial workshop materials upload"
git push origin main
```

---

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **"Settings"** (top menu)
3. Scroll down to **"Pages"** (left sidebar)
4. Under **"Source"**:
   - Branch: Select **"main"**
   - Folder: Select **"/ (root)"**
5. Click **"Save"**
6. Wait 1-2 minutes for deployment

---

### Step 4: Get Your Website URL

After a few minutes, refresh the Settings → Pages section.

You'll see a message:
> ✅ Your site is live at https://YOUR-USERNAME.github.io/pandas-faculty-workshop/

**That's your workshop website URL!** 🎉

---

## 🎨 Customization Tips

### Update the HTML File

Open `index.html` and customize:

```html
<!-- Change email contact -->
<a href="mailto:afirat@suffolk.edu">afirat@suffolk.edu</a>
<!-- Replace with YOUR email -->

<!-- Update university name -->
<p>Suffolk University Sawyer Business School</p>
<!-- Replace with YOUR institution -->

<!-- Update GitHub links -->
https://YOUR-USERNAME.github.io/pandas-faculty-workshop/
<!-- Replace YOUR-USERNAME with your actual GitHub username -->
```

### Update README_GITHUB.md

Rename `README_GITHUB.md` to `README.md` to replace the default:

```bash
# In your repository folder:
rm README.md
mv README_GITHUB.md README.md
git add .
git commit -m "Update README"
git push
```

---

## 🔗 Linking to Google Colab Notebooks

### Option 1: Direct Colab Upload

1. Go to https://colab.research.google.com
2. File → Upload notebook
3. Upload each `.ipynb` file
4. File → Share
5. Set to "Anyone with the link can view"
6. Copy the link
7. Update links in `index.html`:

```html
<a href="YOUR-COLAB-LINK-HERE" target="_blank">
  Open in Colab →
</a>
```

### Option 2: Colab Badge (Recommended)

Add this to your HTML or README for direct Colab opening:

```html
<a href="https://colab.research.google.com/github/YOUR-USERNAME/pandas-faculty-workshop/blob/main/01_Teaching_Demonstration_Notebook.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>
```

Replace `YOUR-USERNAME` with your actual GitHub username.

---

## 📱 Testing Your Website

### Check Everything Works:

✅ Website loads: https://YOUR-USERNAME.github.io/pandas-faculty-workshop/  
✅ All navigation links work  
✅ Downloads work (zip file)  
✅ External links open (Pandas docs, Colab, etc.)  
✅ Looks good on mobile (test on your phone!)  

### Common Issues:

**404 Error?**
- Wait 5 minutes after enabling Pages
- Check that `index.html` is in root folder
- Verify branch is set to "main" in Settings

**Styles not loading?**
- Clear your browser cache
- Check that CSS is embedded in HTML (it is!)

**Links not working?**
- Update all YOUR-USERNAME placeholders
- Make sure files are actually uploaded

---

## 🎯 Recommended File Structure

```
pandas-faculty-workshop/
│
├── index.html                        ⭐ Main website (GitHub Pages)
├── README.md                         ⭐ Repository description
│
├── 00_Quick_Start_Guide.md
├── Pandas_Faculty_Development_Lecture_Plan.md
├── ONE_PAGE_SUMMARY.md
│
├── 01_Teaching_Demonstration_Notebook.ipynb
├── 02_Practice_Exercises_Notebook.ipynb
├── 03_Solutions_with_Explanations.ipynb
│
└── Pandas_Faculty_Workshop_Complete.zip
```

---

## 🎨 Branding Customization

### Change Colors

In `index.html`, find the `:root` CSS variables:

```css
:root {
    --primary-color: #0066cc;      /* Main brand color */
    --secondary-color: #00a86b;    /* Accent color */
    --accent-color: #ff6b35;       /* Highlight color */
}
```

Update these to match your institution's colors!

### Add Logo

Add your institution logo:

```html
<!-- In the hero section -->
<div class="hero-content">
    <img src="your-logo.png" alt="Logo" style="max-width: 200px; margin-bottom: 20px;">
    <h1>🐼 Pandas for Business Faculty</h1>
    ...
</div>
```

Upload `your-logo.png` to your repository first!

---

## 📊 Analytics (Optional)

### Add Google Analytics

1. Create Google Analytics account
2. Get your tracking ID
3. Add before `</head>` in `index.html`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=YOUR-GA-ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'YOUR-GA-ID');
</script>
```

Now you can track:
- How many faculty visit
- Which pages they view
- Which resources they download

---

## 🔄 Updating Content

### When You Make Changes:

```bash
# Make your edits to files
# Then:
git add .
git commit -m "Describe your changes"
git push origin main
```

GitHub Pages will automatically update within 1-2 minutes!

---

## 📧 Custom Domain (Optional)

Want to use your own domain like `pandas-workshop.youruniversity.edu`?

1. Buy/configure domain
2. Add `CNAME` file to repository with your domain
3. In GitHub Settings → Pages → Custom domain
4. Enter your domain
5. Wait for DNS propagation

---

## 🎉 Launch Checklist

Before sharing with faculty:

- [ ] All files uploaded to GitHub
- [ ] GitHub Pages enabled and working
- [ ] Website URL tested and loads correctly
- [ ] All download links work
- [ ] External links tested (Colab, docs, etc.)
- [ ] Contact information updated
- [ ] Institution name updated
- [ ] Colors match your branding (optional)
- [ ] Mobile-friendly (test on phone)
- [ ] Tested in multiple browsers

---

## 🆘 Troubleshooting

### "Page Not Found" Error

**Solution:**
- Wait 5-10 minutes after enabling Pages
- Check Settings → Pages to confirm it's enabled
- Verify `index.html` is in the root directory
- Try accessing: `https://YOUR-USERNAME.github.io/pandas-faculty-workshop/index.html`

### Website Looks Broken

**Solution:**
- Clear browser cache (Ctrl+Shift+R or Cmd+Shift+R)
- Check browser console for errors (F12)
- Verify all CSS is in the `<style>` section
- Test in incognito/private window

### Downloads Don't Work

**Solution:**
- Verify files are actually in repository
- Check file names match exactly (case-sensitive!)
- Try right-click → "Save link as..."

### Links to Notebooks Don't Work

**Solution:**
- Update YOUR-USERNAME placeholders
- Upload notebooks to Colab first
- Get shareable links and update HTML

---

## 💡 Pro Tips

### Tip 1: Use GitHub's Built-in Editor
Edit files directly on GitHub.com without cloning:
1. Navigate to file
2. Click pencil icon (edit)
3. Make changes
4. Commit directly

### Tip 2: Preview Before Publishing
Test locally by opening `index.html` in your browser before pushing to GitHub.

### Tip 3: Version Control is Your Friend
Don't be afraid to experiment! You can always revert:
```bash
git log  # See commit history
git revert COMMIT_HASH  # Undo specific commit
```

### Tip 4: Keep It Simple
Start with the basic setup. Add customizations incrementally.

---

## 📚 Resources

### GitHub Docs
- [GitHub Pages Basics](https://docs.github.com/pages)
- [Managing Custom Domain](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site)

### Tutorials
- [GitHub Pages for Beginners](https://www.youtube.com/results?search_query=github+pages+tutorial)
- [Git Basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)

---

## ✅ Success!

Once everything is set up, share this URL with faculty:

**https://YOUR-USERNAME.github.io/pandas-faculty-workshop/**

They can:
- ✅ View the beautiful website
- ✅ Download all materials
- ✅ Access notebooks directly
- ✅ See FAQs and resources
- ✅ Bookmark for future reference

---

## 🎊 You Did It!

Your workshop now has a professional web presence! Faculty can easily:
- Find materials anytime
- Share with colleagues
- Access from any device
- No confusion about "which file to download"

**Welcome to the world of open educational resources! 🌟**

---

**Questions?** Open an issue on GitHub or contact your IT support team!

**Happy Teaching! 🎓**
