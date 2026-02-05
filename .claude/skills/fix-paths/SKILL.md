---
name: fix-paths
description: Fix absolute URLs in scraped HTML files to relative paths for static hosting
argument-hint: [domain-to-fix]
---

# Fix Asset Paths in HTML

Convert absolute URLs to relative paths for static site hosting:

1. **Find all HTML files and replace absolute URLs:**
```bash
find . -name "*.html" -exec sed -i 's|https://$ARGUMENTS/wp-content/|../../wp-content/|g' {} \;
```

2. **Common path patterns to fix:**
   - `https://domain.com/wp-content/` -> `../../wp-content/`
   - `https://domain.com/wp-includes/` -> `../../wp-includes/`
   - Adjust `../../` depth based on file location

3. **For nested pages (page/2/, page/3/):**
   - Use `../../../../wp-content/` (4 levels up)

4. **Verify paths are correct:**
```bash
grep -o 'src="[^"]*wp-content[^"]*"' index.html | head -5
```

Arguments: $ARGUMENTS (the domain to replace, e.g., "example.com")
