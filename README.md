## Parthian Contractors LTD — Static Site

- Minimal, fast-loading static website using plain HTML and Vue 3 via CDN (no build tools)
- Inline critical CSS, deferred scripts, WebP/AVIF placeholders via placehold.co
- Accessible, mobile-first, black and white luxury aesthetic

### Local preview

Use any static file server:

```bash
cd parthian-website
python3 -m http.server 8080
# then open http://localhost:8080/
```

### Structure
- `index.html` — Home
- `about.html` — About
- `gallery.html` — Project listing rendered by Vue from `assets/js/projects.data.js`
- `project.html` — Individual project page using query `?id=`
- `contact.html` — Contact with prominent tel link
- `assets/js/projects.data.js` — Project data only (global `window.PROJECTS`)
- `nginx.conf` — Static hosting example with HTTP/2 and gzip

### Performance notes
- Critical CSS inline; only one small JS data file and Vue CDN on dynamic pages
- All scripts `defer`
- Images use `<picture>` with AVIF/WebP
- Headers and caching tuned in `nginx.conf`

### Customize
- Replace placeholders with real images
- Update phone number in `contact.html`
- Add real domain and certificate paths in `nginx.conf` 