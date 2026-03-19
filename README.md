# Ninjai — Netlify Deployment

## File Structure

```
ninjai-netlify/
├── index.html          ← Main campaign site
├── ninjai-film.html    ← Animated product film placeholder
├── images/
│   ├── ninjai-hero.jpeg    ← Main product photo (hero + film)
│   ├── ninjai-detail.jpeg  ← Detail / top-down shot
│   └── ninjai-real.jpeg    ← Real-world shelf photo
└── README.md
```

## Deploy to Netlify (30 seconds)

1. Go to **netlify.com** and sign up free (GitHub login works great)
2. From the dashboard click **"Add new site"** → **"Deploy manually"**
3. Drag the entire **ninjai-netlify** folder onto the upload zone
4. Netlify gives you a live URL instantly — e.g. ninjai-abc123.netlify.app
5. Optionally rename it under Site Settings → Site name

## Replacing the Product Film

When your real video is ready, open index.html and find the section-video block.
Replace the iframe with a standard video tag:

  <video
    src="your-video.mp4"
    poster="images/ninjai-hero.jpeg"
    controls
    playsinline
    style="width:100%; display:block;"
  ></video>

Upload the .mp4 into the same folder before redeploying.

## Custom Domain

Netlify supports custom domains on the free plan:
Site Settings > Domain Management > Add custom domain

## Notes

- The brand bar shows "MM" as a logo placeholder — replace with your actual logo SVG
- Pricing is indicative — update in index.html before going live
- The film runs entirely in-browser with no external dependencies
