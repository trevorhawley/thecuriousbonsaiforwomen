# The Curious Bonsai for Women

A women-focused coaching and editorial static website exploring confidence, voice, self-trust, career transition, and meaningful personal growth. A topic-focused initiative within the broader work of [The Curious Bonsai](https://thecuriousbonsai.com).

---

## File Structure

```
/
├── index.html          Homepage
├── blog.html           Articles archive
├── post.html           Single post template (sample article)
├── about.html          About this resource
├── contact.html        Contact form (static)
├── assets/
│   ├── css/
│   │   └── styles.css  All site styles
│   ├── js/
│   │   └── main.js     Minimal JS (nav toggle, scroll reveal, filter)
│   └── img/
│       └── placeholder.txt   Image notes and guidance
└── README.md
```

---

## Deployment

This is a fully static site. No build step required.

### Netlify (drag and drop)
1. Go to [netlify.com](https://netlify.com) and log in
2. From the dashboard, click **"Add new site" → "Deploy manually"**
3. Unzip the downloaded file
4. Drag the **entire unzipped folder** into the Netlify drop zone
5. Done — Netlify will assign a URL and your site will be live

### Cloudflare Pages
1. Log in to [pages.cloudflare.com](https://pages.cloudflare.com)
2. Create a new project → "Direct Upload"
3. Upload all files (maintaining the folder structure)
4. Deploy

### Surge
```bash
npm install -g surge
cd /path/to/your-site-folder
surge
```
Follow the prompts to assign a `.surge.sh` domain.

### Any static host
Upload all files preserving the folder structure. The `index.html` must be at the root level.

---

## After Deployment

### Replace placeholder images
Open `assets/img/placeholder.txt` for full image guidance. Files to replace:
- `assets/img/hero.jpg` — hero section portrait
- `assets/img/founder.jpg` — Michelle Mah portrait
- `assets/img/post-1.jpg` through `post-6.jpg` — article thumbnails

Update the `<img>` tags in each HTML file where placeholder divs currently appear (search for `<!-- Replace with:`).

### Connect the contact form
The form is currently static (no backend). To make it functional:
- **Netlify Forms**: Add `netlify` attribute to `<form id="contactForm">` — Netlify handles submission automatically
- **Formspree**: Sign up at formspree.io, add `action="https://formspree.io/f/YOUR_ID"` to the form tag
- **EmailJS**: Use the EmailJS SDK if you prefer client-side submission

### Update placeholder links
Several resource hub and social links use `href="#"`. Update these as the resource grows.

### Custom domain
Set your custom domain through your host's dashboard (e.g. `women.thecuriousbonsai.com`).

---

## Content Notes

- `post.html` contains one full sample article: *Finding Your Voice After Years of Playing Small*
- All other article links point to `post.html` as a template — duplicate and populate for each new article
- The category filter on `blog.html` uses the `data-category` attribute on each `.article-card` element

---

## Forms Note

The contact form (`contact.html`) has a JavaScript handler that prevents default submission and shows a confirmation message. This is for UI purposes only — no data is sent until you connect a form backend.

---

Built with plain HTML, CSS (custom properties, no framework), and minimal vanilla JavaScript.
No dependencies. No build tools. No node_modules.
