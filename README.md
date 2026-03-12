# Case Files — GitHub Pages Site

A private, self-contained website to share call recordings, transcripts, and images via a URL.

---

## 📁 Folder Structure

```
evidence-site/
├── index.html          ← The main website
├── audio/
│   └── EoinCallApril16th.m4a    ← Call recording
├── images/             ← Place image files here
│   └── (add your images here)
└── README.md
```

---

## 🚀 How to Deploy to GitHub Pages

### Step 1 — Create a GitHub Repository
1. Go to [github.com](https://github.com) and log in
2. Click **New repository** (green button, top right)
3. Name it something like `case-files` (keep it private if you want — though GitHub Pages on free accounts requires public)
4. Click **Create repository**

### Step 2 — Upload your files
1. On the repository page, click **Add file → Upload files**
2. Drag and drop the entire `evidence-site/` folder contents:
   - `index.html`
   - The `audio/` folder (with the .m4a files)
   - The `images/` folder (with any images)
3. Click **Commit changes**

> ⚠️ **Important:** GitHub has a 100MB per-file limit. Audio files under 100MB will work fine. For larger files, see the "Large Files" section below.

### Step 3 — Enable GitHub Pages
1. In your repository, go to **Settings** (top tab)
2. Scroll down to **Pages** in the left sidebar
3. Under **Source**, select **Deploy from a branch**
4. Set Branch to **main** and folder to **/ (root)**
5. Click **Save**
6. Wait ~60 seconds, then your site will be live at:
   ```
   https://YOUR-USERNAME.github.io/REPO-NAME/
   ```

### Step 4 — Share the URL
Send the URL to the recipient. They can:
- **Listen** to recordings directly in their browser
- **Download** audio files with the download button
- **View** and download images
- **Read** transcripts alongside audio

---

## ➕ Adding More Recordings

1. Add the audio file to the `audio/` folder
2. In `index.html`, copy the `<div class="recording-card">` block and update:
   - The title and date
   - The `<source src="audio/FILENAME.m4a">` path
   - The `href` on the download button
   - The transcript dialogue lines

---

## 🖼 Adding Images

1. Place image files (JPG, PNG, etc.) in the `images/` folder
2. Open `index.html` and find the `imageManifest` array near the bottom
3. Add entries like:
   ```javascript
   const imageManifest = [
     { src: "images/photo1.jpg", label: "Description of image" },
     { src: "images/photo2.png", label: "Another image" },
   ];
   ```
4. Save and re-upload to GitHub

---

## ⚠️ Large Audio Files (over 100MB)

If any audio file is over 100MB, use [Git LFS](https://git-lfs.github.com/) or host the audio on a free service like [archive.org](https://archive.org) and update the `<source src="...">` URL in the HTML.

---

## 🔒 Privacy Note

GitHub Pages repositories must be **public** on free accounts for the site to be accessible. If you need the site to be private, consider:
- GitHub Pro ($4/mo) — allows private repos with Pages
- [Netlify](https://netlify.com) — free private site hosting with password protection
