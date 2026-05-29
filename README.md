# 🎂 Divya's Birthday Live Slideshow

A live-synced slideshow — you control slides from your phone, friends watch in real-time.

## 🚀 Setup (2 minutes)

### Step 1: Create free Firebase project
1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Click **"Create a project"** → name it anything (e.g. `divya-bday`)
3. Skip Google Analytics → Click **Create**
4. In the left sidebar, click **Build → Realtime Database**
5. Click **Create Database** → Choose any location → Start in **Test Mode** → Enable
6. Copy the URL shown at the top (looks like: `https://divya-bday-default-rtdb.firebaseio.com`)

### Step 2: Deploy
**Option A: GitHub Pages (free)**
1. Create a new GitHub repo
2. Upload `index.html` to the repo
3. Go to Settings → Pages → Source: main branch → Save
4. Your site will be live at `https://yourusername.github.io/reponame/`

**Option B: Netlify (free, faster)**
1. Go to [netlify.com](https://app.netlify.com/drop)
2. Drag & drop the `index.html` file
3. Done! You get a URL instantly

**Option C: Just open locally**
- Double-click `index.html` in your browser — works for testing

### Step 3: Use it

**You (Admin/Presenter):**
```
https://your-site.com/index.html?mode=admin
```
- Open this URL on your phone
- Paste the Firebase URL when prompted (one-time)
- Use the dropdown or ← → buttons to control slides
- Keyboard arrows also work on laptop

**Friends (Viewers):**
```
https://your-site.com/index.html
```
- Share this link with everyone
- They paste the same Firebase URL once
- Slides auto-sync to whatever you show — they can't move slides themselves

## 📱 How it works
- Admin writes current slide number to Firebase
- Viewers poll every 1.2 seconds and display whatever slide Admin set
- All images are embedded in the HTML — no external dependencies
- Single file, no build step, no npm, no frameworks

## ⚠️ Firebase Test Mode
Test mode rules expire after 30 days. For a one-day birthday party this is perfect. If you want it to last longer, update the Realtime Database rules to:
```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```
