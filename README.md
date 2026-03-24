# image_repo — Public Image CDN / Brand Asset Repository

This repository serves as the **publicly accessible image host** for the OPC platform. It is deployed via **GitHub Pages** and used as a CDN to serve the OPC logo and other brand assets across all services — emails, the public website, admin panels, and any external integrations.

---

## 📁 Contents

| File | Description |
|------|-------------|
| `logo.png` | OPC brand logo — raster format (PNG, ~76KB) |
| `logo.svg` | OPC brand logo — vector format (SVG, ~220KB, scalable at any resolution) |
| `index.html` | Minimal HTML index page (placeholder for the GitHub Pages root) |

---

## 🌐 Public URLs

Once deployed via GitHub Pages, assets are accessible at:

```
https://code-hamster-rohit1008.github.io/image_repo/logo.png
https://code-hamster-rohit1008.github.io/image_repo/logo.svg
```

These URLs are embedded directly inside:
- **OPC_Admin_Meet_Controls** → `email_service.py` (email header logo)
- **OPC_Backend** → `util/emails_template_.py` (all outgoing email HTML templates)
- **OPC_New** → local `assets/images/logo.png` copy (also referenced from image_repo in emails)

---

## 🔗 Why a Separate Repo?

Email clients cannot load images from local paths or private servers. By hosting the logo on GitHub Pages (a permanent, public, reliable URL), it is guaranteed to render correctly inside all HTML emails sent by the OPC platform — regardless of the email client or recipient's network.

---

## ➕ Adding New Assets

1. Add the image file (PNG, SVG, WebP, etc.) to this folder
2. Push to the `main` branch
3. GitHub Pages will automatically serve it at:
   `https://code-hamster-rohit1008.github.io/image_repo/<filename>`
4. Use that URL in any service that needs to reference the asset externally

---

## 📌 Notes

- Keep file names lowercase with hyphens (e.g., `logo-dark.png`, `banner.webp`)
- Prefer SVG for logos and icons (resolution-independent)
- Prefer WebP for photos (better compression than JPG/PNG)
