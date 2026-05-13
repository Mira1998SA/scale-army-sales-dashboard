# Scale Army Sales Dashboard

Interactive sales dashboard for the Business Development team at Scale Army.

## Features
- KPI cards: Revenue, Deals Closed, Conversion Rate, Avg Deal Size
- Monthly revenue trend vs target (line chart)
- Lead source breakdown (donut chart)
- Pipeline funnel with drop-off percentages
- Win rate by source (horizontal bar)
- Sortable rep leaderboard with vs-target progress
- Recent activity feed

## Skill Files
See `/skills/` for reusable guides:
- `skill-load-data.md` — how to import new weekly CSV data
- `skill-build-chart.md` — how to add a new chart component
- `skill-update-dashboard.md` — end-to-end weekly update workflow

## Deploy to Vercel

### Option A: Vercel CLI
```bash
npm i -g vercel
vercel
```

### Option B: Vercel Dashboard
1. Push this folder to a GitHub repo
2. Go to vercel.com → New Project → Import from GitHub
3. Select the repo — Vercel auto-detects `vercel.json` and deploys as static
4. No environment variables needed (all data is currently in-app)

## Deploy to GitHub
```bash
git init
git add .
git commit -m "feat: initial sales dashboard"
git remote add origin https://github.com/YOUR_USERNAME/scale-army-sales-dashboard.git
git push -u origin main
```

## Adding Real Data
When you receive real CSV data from Scale Army ops, follow `skills/skill-load-data.md`.
Then update the data constants at the top of `index.html` (search for `// ── DATA`).
