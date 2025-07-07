# EnneadTab Wiki

This repo is created and maintained by EnneadTab-OS

## Debugging CSS Issues

If the site doesn't look right on GitHub Pages, here are some debugging steps:

1. **Open Browser Developer Tools** (F12)
2. **Check the Console** for any error messages
3. **Look for these debug messages:**
   - "CSS loaded: true/false"
   - "Page URL: [current URL]"
   - "CSS file path: [path to style.css]"
   - "Video loaded successfully" or "Video failed to load"

### Common Issues and Solutions:

1. **CSS not loading**: Check if the `style.css` file exists in the root directory
2. **Video not loading**: The video file was renamed from `background video.mp4` to `background-video.mp4` to fix URL encoding issues
3. **Font loading issues**: The site uses Google Fonts (Inter, Cormorant Garamond, Roboto)

### Local Testing:

To test locally before pushing to GitHub:
```bash
# Using Python (if available)
python -m http.server 8000

# Using Node.js (if available)
npx http-server

# Using PHP (if available)
php -S localhost:8000
```

Then visit `http://localhost:8000` in your browser.

### GitHub Pages Configuration:

- The `.nojekyll` file ensures GitHub Pages doesn't process the site with Jekyll
- The GitHub Actions workflow automatically tests and deploys the site
- All HTML files include debugging scripts to help identify loading issues