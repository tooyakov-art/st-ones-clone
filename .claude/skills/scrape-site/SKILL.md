---
name: scrape-site
description: Scrape a website with wget, download all assets, fix paths for static hosting
argument-hint: [url]
---

# Scrape Website for Static Hosting

When the user wants to scrape/parse/clone a website, follow these steps:

1. **Download with wget:**
```bash
wget --recursive --page-requisites --adjust-extension --convert-links --span-hosts --domains=$DOMAIN $ARGUMENTS
```

2. **Fix relative paths** in HTML files for assets (CSS, JS, images)

3. **Handle AJAX/infinite scroll** - disable or implement static alternative

4. **Fix broken functionality:**
   - Remove server-dependent features
   - Fix image lazy loading
   - Show pagination instead of infinite scroll

5. **Create fix.js and fix.css** if needed to patch issues

Arguments: $ARGUMENTS (the URL to scrape)
