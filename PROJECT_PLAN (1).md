# Scale Army — Sales Dashboard Project Plan

## Dashboard Goal
Build an interactive React sales dashboard for the Business Development team at Scale Army.
The dashboard surfaces pipeline health, conversion performance, revenue tracking, and rep
activity so BD leads can make faster decisions and report upward with confidence.

## Role Context
**Role:** Sales / Business Development  
**Key decisions this dashboard supports:**
- Where are deals stalling in the pipeline?
- Which reps are hitting targets and who needs coaching?
- What is our month-over-month revenue trend?
- Which lead sources convert best?

---

## Data Sources Used
| Sheet / Source | Key Columns Used |
|---|---|
| `deals.csv` | deal_id, rep_name, stage, value, close_date, lead_source |
| `reps.csv` | rep_name, target, region |
| `activities.csv` | rep_name, activity_type, date, count |

> **Note:** Dummy data is generated inside the app. When real data arrives, follow `skills/skill-load-data.md`.

---

## Markdown Skills (Reusable Guides)

These skill files live in `/skills/` and must be followed every time new data is added or a new feature is built.

| Skill File | Purpose |
|---|---|
| `skills/skill-load-data.md` | How to import, clean, and validate new weekly CSV data |
| `skills/skill-build-chart.md` | How to create a new chart component consistently |
| `skills/skill-update-dashboard.md` | End-to-end steps when new data arrives each week |

---

## Build Order

1. ✅ Set up project structure and skill files
2. ✅ Generate dummy sales data layer
3. ✅ Build KPI summary cards (revenue, deals closed, conversion rate, avg deal size)
4. ✅ Build pipeline stage funnel chart
5. ✅ Build monthly revenue trend line chart
6. ✅ Build rep leaderboard table
7. ✅ Build lead source breakdown (pie/donut chart)
8. ✅ Add date range filter (this month / last 30 days / this quarter)
9. ✅ Polish UI, animations, and responsive layout
10. ⬜ Deploy to Vercel
11. ⬜ Push to GitHub

---

## Interactive Feature Checklist

- [x] KPI cards with trend indicators (up/down vs last period)
- [x] Pipeline funnel — deals by stage with drop-off %
- [x] Revenue trend — line chart by month
- [x] Rep leaderboard — sortable by revenue, deals closed, conversion
- [x] Lead source breakdown — donut chart
- [x] Global date range filter
- [ ] Deal detail modal (click a deal to expand)
- [ ] Export to CSV button
- [ ] Rep drill-down view
- [ ] Email digest summary generator

---

## Deployment
- **Framework:** React (Vite or Create React App)
- **Charts:** Recharts
- **Hosting:** Vercel
- **Repo:** GitHub
