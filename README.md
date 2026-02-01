# BibleChat Legal Documents

Privacy Policy and Terms of Service for the BibleChat iOS app.

## 📁 Files

- **index.html** - Landing page with links to both documents
- **privacy.html** - Comprehensive privacy policy
- **terms.html** - Complete terms of service

## 🚀 Setup Instructions

### 1. Create GitHub Repository

```bash
# Initialize git repo
cd /Users/derekisensee/Documents/biblechat-legal
git init
git add .
git commit -m "Initial commit: Privacy Policy and Terms of Service"

# Create new public repo on GitHub (via web browser):
# Go to https://github.com/new
# Name: biblechat-legal
# Description: Legal documents for BibleChat iOS app
# **Make it PUBLIC** (required for GitHub Pages)
# Don't add README, .gitignore, or license (we have our own)

# Link and push
git remote add origin https://github.com/YOUR_USERNAME/biblechat-legal.git
git branch -M main
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to your repo: `https://github.com/YOUR_USERNAME/biblechat-legal`
2. Click **Settings** (top right)
3. Click **Pages** (left sidebar)
4. Under "Source", select: **Deploy from a branch**
5. Under "Branch", select: **main** and **/ (root)**
6. Click **Save**
7. Wait 2-5 minutes for deployment

### 3. Get Your URLs

Once deployed, your URLs will be:

```
Landing Page:    https://YOUR_USERNAME.github.io/biblechat-legal/
Privacy Policy:  https://YOUR_USERNAME.github.io/biblechat-legal/privacy.html
Terms of Service: https://YOUR_USERNAME.github.io/biblechat-legal/terms.html
```

## 📝 Next Steps

### Update iOS App

Replace placeholder URLs in these files:

**1. SubscriptionPaywallView.swift** (lines 229-236)

```swift
// OLD:
Button("Terms") {
    // TODO: Show terms
}

Button("Privacy") {
    // TODO: Show privacy policy
}

// NEW:
Button("Terms") {
    if let url = URL(string: "https://YOUR_USERNAME.github.io/biblechat-legal/terms.html") {
        UIApplication.shared.open(url)
    }
}

Button("Privacy") {
    if let url = URL(string: "https://YOUR_USERNAME.github.io/biblechat-legal/privacy.html") {
        UIApplication.shared.open(url)
    }
}
```

**2. SettingsView.swift** (lines 257-263)

```swift
// OLD:
Link(destination: URL(string: "https://example.com/privacy")!) {
    Label("Privacy Policy", systemImage: "hand.raised.fill")
}

Link(destination: URL(string: "https://example.com/terms")!) {
    Label("Terms of Service", systemImage: "doc.text.fill")
}

// NEW:
Link(destination: URL(string: "https://YOUR_USERNAME.github.io/biblechat-legal/privacy.html")!) {
    Label("Privacy Policy", systemImage: "hand.raised.fill")
}

Link(destination: URL(string: "https://YOUR_USERNAME.github.io/biblechat-legal/terms.html")!) {
    Label("Terms of Service", systemImage: "doc.text.fill")
}
```

### Update App Store Connect

1. Go to [App Store Connect](https://appstoreconnect.apple.com/)
2. Select your app
3. Go to **App Information**
4. Under **Privacy Policy URL**, enter:
   ```
   https://YOUR_USERNAME.github.io/biblechat-legal/privacy.html
   ```
5. Click **Save**

## ⚠️ Important Notes

### Before Publishing

1. **Replace placeholders** in the HTML files:
   - `[Your State]` in terms.html (line in Governing Law section)
   - `[Your website URL]` in both files (Contact Us sections)
   - `support@biblechat.app` email address (if different)

2. **Review for accuracy**:
   - Ensure all features described match your actual app
   - Verify third-party service URLs are current
   - Update "Last Updated" date if you make changes

3. **Legal review** (recommended):
   - These templates are based on your app's actual features
   - Consider having a lawyer review before launch
   - Especially important for GDPR compliance if you have EU users

### Updating Documents

When you need to update the privacy policy or terms:

```bash
# Edit the HTML files
# Then commit and push
git add .
git commit -m "Update privacy policy - [describe changes]"
git push

# GitHub Pages will automatically rebuild (takes 2-5 minutes)
```

### Custom Domain (Optional)

If you want to use a custom domain like `legal.biblechat.app`:

1. Buy a domain
2. Add a CNAME file to this repo with your domain
3. Configure DNS with your domain provider
4. Enable HTTPS in GitHub Pages settings
5. Update URLs in app accordingly

## 📋 Checklist

Before App Store submission:

- [ ] GitHub repo is public
- [ ] GitHub Pages is enabled and deployed
- [ ] URLs are working (test in browser)
- [ ] Placeholders replaced in HTML files
- [ ] iOS app updated with correct URLs
- [ ] App Store Connect privacy policy URL set
- [ ] Legal review completed (if doing one)

## 🔒 Privacy & Security

These legal documents are intentionally hosted in a **separate public repository** from your main app code because:

1. ✅ **Privacy policy must be publicly accessible** (App Store requirement)
2. ✅ **Your main app repo is private** (contains Firebase configs, API keys, etc.)
3. ✅ **Clean separation** of legal docs from code
4. ✅ **Easy updates** without touching app code

## 📧 Questions?

If you need to make changes to these documents after reviewing with a lawyer, just edit the HTML files and push to GitHub. The changes will go live automatically.

---

**Generated**: January 31, 2026
**Based on**: BibleChat codebase audit
**Compliance**: App Store Review Guidelines, GDPR, COPPA
