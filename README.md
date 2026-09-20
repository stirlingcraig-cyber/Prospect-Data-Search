# Decision-Maker Ledger — Sustainability & Procurement OSINT

A free, single-file, GDPR-aware working ledger for identifying **publicly accessible** Sustainability/ESG and Procurement/Supply Chain decision-makers at UK companies. Built for structured B2B outreach research under a UK GDPR Legitimate Interest basis.

**Live site:** `https://REPLACE-WITH-YOUR-USERNAME.github.io/REPLACE-WITH-YOUR-REPO/` *(fill in once Pages is enabled — see below)*

## What it does

A seven-step public-source research workflow per company, run entirely in your browser:

1. **Reports** — annual/sustainability report search
2. **Leadership pages** — executive team / board search
3. **LinkedIn** — sustainability & procurement role search (from your own logged-in account)
4. **Companies House** — officer records, with a direct link when you've logged the company's CH number
5. **Payment practices** — the UK's twice-yearly large-business invoice payment reporting duty, a useful dated confirmation of a current board-level contact
6. **News & press releases** — recent appointment announcements
7. **Ongoing monitoring** — Google Alerts, Wayback Machine, conference/award mentions

Plus: bulk CSV/TSV import (three auto-detected formats), LinkedIn contact paste-and-preview, a formatted export (`.txt`/`.csv`), and manual JSON export/import for persistence between sessions.

## Architecture

- **Single self-contained HTML file** (`index.html`) — no backend, no build step, no external runtime dependencies.
- **No browser storage** — all ledger state lives in memory for the tab. Use the Export/Load JSON panel in the app to carry data between sessions; nothing is written to `localStorage`, cookies, or any server.
- **No data leaves your browser** except the external research links you choose to open (Google, LinkedIn, Companies House, gov.uk) — the app itself never calls out anywhere or stores what you find.

## Deploying this yourself (GitHub Pages)

1. Create a new **public** GitHub repository and push these files to its `main` branch (a private repo needs GitHub Pro/Team/Enterprise to publish Pages).
2. In the repo, go to **Settings → Pages** and set **Source** to **GitHub Actions** (the included workflow at `.github/workflows/deploy.yml` handles the rest — it redeploys automatically on every push to `main`).
3. Your site will be live at `https://<your-username>.github.io/<your-repo>/` within a minute or two of the first successful run (check the **Actions** tab for progress).
4. Once you know that URL, replace every `REPLACE-WITH-YOUR-USERNAME.github.io/REPLACE-WITH-YOUR-REPO/` placeholder in `index.html`, `robots.txt`, and `sitemap.xml` with it, commit, and push again.

### Getting it indexed by search engines

Being publicly hosted doesn't make a new site appear in search results immediately — indexing normally takes anywhere from a few days to a few weeks. To speed it up:

- Submit `sitemap.xml` in [Google Search Console](https://search.google.com/search-console) and [Bing Webmaster Tools](https://www.bing.com/webmasters) for the property `https://<your-username>.github.io/<your-repo>/`.
- Link to the live URL from somewhere else already indexed (a LinkedIn post, a GitHub profile README, another site) — inbound links help crawlers find and trust a new page faster.
- The `robots.txt`, `sitemap.xml`, meta description, Open Graph tags, and JSON-LD structured data in `index.html` are already in place to help search engines understand and preview the page once they do crawl it.

## Compliance reminders (built into the app's footer too)

- Record only information published without login, paywall, or bypassing access controls.
- Run LinkedIn lookups from your own logged-in account, per LinkedIn's terms — this tool never queries LinkedIn on your behalf.
- Suggested UK GDPR lawful basis: Legitimate Interest (Art. 6(1)(f)) — confirm it fits your specific use case, disclose it on first contact, honour opt-outs, and set your own retention period.

This ledger provides structure and reminders; it does not enforce compliance. You remain responsible for lawful, proportionate, and transparent use of any data you record.

## License

MIT — see [LICENSE](./LICENSE). Update the copyright holder name before publishing if you want attribution to be accurate.
