# Prateek Kumar Yadav: Portfolio

A single-file portfolio site. Everything (layout, styles, animation and content) lives in `index.html`. No build step, no framework, no dependencies besides Google Fonts.

## Preview locally

Double-click `index.html`, or serve the folder:

```bash
# Python
python3 -m http.server 8080
# or Node
npx serve .
```

Then open http://localhost:8080.

## Edit your content

Open `index.html` and find the block marked `EDIT YOUR CONTENT HERE`. It is plain JSON:

| Key | What it controls |
|---|---|
| `hero` | Name, the two intro lines, and the green "open to" badge |
| `journey` | The animated "How I got here" card in the hero: `steps` (`t` title, `s` tools, `d` one-line detail) and the dashed `next` step |
| `work` | The "how I work" strip under the hero: `note` caption, and `items` (`k` = function name without brackets, `d` = one-line description) |
| `about` | About paragraph |
| `jobs` | Experience timeline (`title` as "Role, Company", `meta`, `bullets`) |
| `projects` | Project cards (`title`, `desc`, `tags`, `link`) |
| `skills` | Skill groups (`g` = group name, `items` = comma-separated list) |
| `research` | Research card |
| `certs`, `edu` | Certification and education cards |
| `resume` | Resume section: `heading`, `text`, `meta` chips, and `link` to the PDF. Empty `link` hides the section and the hero button |
| `contact` | Heading, text, email, LinkedIn and GitHub links |

Tips:
- Fill a card's `link` field with a URL to show a **View** button on it. Leave it as `""` to hide the button.
- **Resume file:** `resume.link` can be a web link (Google Drive and so on, opens in a new tab) or a file next to `index.html`. To host the PDF yourself, put `Prateek_Yadav_Resume.pdf` beside `index.html` and set `"link":"Prateek_Yadav_Resume.pdf"`; the button then downloads the file directly.
- Numbers like `100K+` or `20%` inside experience bullets are highlighted automatically.
- Keep the JSON valid: double quotes, commas between items, no trailing comma. If the page goes blank after an edit, paste the JSON into https://jsonlint.com to find the mistake.

## Deploy

### GitHub Pages (free)
1. Create a repo, for example `yadavprateek-here.github.io` (this name gives you `https://yadavprateek-here.github.io`).
2. Upload `index.html` (and this README) to the repo root.
3. Go to **Settings > Pages**, set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`, and save.
4. The site goes live in a minute or two.

### Netlify (free)
Go to https://app.netlify.com/drop and drag this folder onto the page. You get a live URL instantly; rename it under **Site settings**.

### Vercel (free)
```bash
npm i -g vercel
vercel        # run inside this folder, accept the defaults
```

### Any other host
Upload `index.html` to the web root of any static host (Cloudflare Pages, Firebase Hosting, S3, cPanel). Nothing else is needed.

## Custom domain (optional)
Buy a domain (for example `prateekyadav.dev`), then add it in your host's domain settings (GitHub Pages: **Settings > Pages > Custom domain**; Netlify and Vercel: **Domains**) and follow the DNS records they show.
