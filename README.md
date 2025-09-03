# Boston.com Speed Reader (GitHub Pages + Actions)

**What this is**  
A static site that shows **3–4 bullet summaries** of Boston.com stories with “Read more →” links.

**How it works**  
GitHub Actions runs a Node builder that reads the RSS feed, fetches article text, asks OpenAI for summaries, and publishes a static site to **GitHub Pages** (no server, your API key stays in **Secrets**).

---

## 🚀 One-time setup
1. Create a new GitHub repo and upload these files (drag & drop in GitHub web UI).
2. In **Settings → Secrets and variables → Actions**, add:
   - Name: `OPENAI_API_KEY`
   - Value: your OpenAI key
3. In **Settings → Pages**, set **Branch: `gh-pages`** (root).
4. Workflow runs on push and every 30 minutes.

---

## 🔧 Customize
- `MODEL` (default `gpt-4o-mini`)
- `RSS_URL` (default Boston.com feed)
- `MAX_ITEMS` (default 12)
- `SUMMARY_PROMPT` (controls bullet style)
- `SITE_TITLE`, `SITE_TAGLINE`

---

## 🖥 Local preview
```bash
npm i
cp .env.example .env # add your key
npm run dev
# open http://localhost:5173
```

---

## 📂 Output
- `dist/index.html` → site
- `dist/styles.css` → CSS
- `dist/data.json` → structured summaries

---

## 📜 License
MIT
