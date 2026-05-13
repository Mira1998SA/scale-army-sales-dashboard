# Skill: Load Data
**File:** `skills/skill-load-data.md`  
**Use when:** New weekly or monthly CSV data arrives and needs to be added to the dashboard.

---

## Steps

### 1. Receive the file
- File should be a `.csv` or `.xlsx` export
- Save it into `/data/raw/` with a date suffix, e.g. `deals_2024-06-01.csv`

### 2. Check required columns
Before doing anything, verify these columns exist:

**deals.csv must have:**
- `deal_id` — unique identifier
- `rep_name` — matches exactly to names in reps.csv
- `stage` — one of: Prospecting, Qualified, Proposal, Negotiation, Closed Won, Closed Lost
- `value` — number, no currency symbols
- `close_date` — format: YYYY-MM-DD
- `lead_source` — one of: Referral, Inbound, Outbound, Event, Partner

**reps.csv must have:**
- `rep_name`, `target` (annual $), `region`

**activities.csv must have:**
- `rep_name`, `activity_type` (Call / Email / Meeting), `date`, `count`

### 3. Clean the data
- Remove rows where `value` is blank or zero
- Trim whitespace from `rep_name` and `stage`
- Normalize dates to YYYY-MM-DD
- Remove duplicate `deal_id` rows (keep latest)

### 4. Replace the data file
- Copy cleaned file to `/data/deals.csv` (overwrite)
- Update `/data/reps.csv` and `/data/activities.csv` if they also changed

### 5. Test
- Open the dashboard locally (`npm run dev`)
- Check that KPI cards update
- Check that no chart shows "undefined" or NaN

### 6. Commit
```bash
git add data/
git commit -m "chore: update data [YYYY-MM-DD]"
git push
```
Vercel will auto-redeploy.

---

## Notes
- Never edit the raw file — always work from a copy
- If a new `stage` or `lead_source` value appears, update the color map in `src/data/config.js`
