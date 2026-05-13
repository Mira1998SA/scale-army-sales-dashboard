# Skill: Update Dashboard
**File:** `skills/skill-update-dashboard.md`  
**Use when:** New data arrives and the dashboard needs to be refreshed and redeployed.

---

## Weekly Update Checklist

- [ ] 1. Receive new data files from ops/leadership
- [ ] 2. Follow `skills/skill-load-data.md` to clean and validate
- [ ] 3. Replace files in `/data/`
- [ ] 4. Run `npm run dev` locally and check all charts render correctly
- [ ] 5. Check KPI cards show expected values (sanity check against source)
- [ ] 6. If a new feature was requested, follow `skills/skill-build-chart.md`
- [ ] 7. Update `PROJECT_PLAN.md` feature checklist if anything new was built
- [ ] 8. Commit and push to GitHub
- [ ] 9. Verify Vercel auto-deploys successfully
- [ ] 10. Share updated Vercel link with team on Slack

---

## Prompting Claude for Updates

When asking Claude to help with a weekly update, always start with:

> "I'm updating the Scale Army sales dashboard. Please follow the skill files in /skills/ for this project. Here is what I need: [describe change]."

This ensures Claude follows the established patterns rather than inventing new approaches.

---

## If Something Breaks
1. Check browser console for errors
2. Most common issue: column name mismatch in new CSV → re-check `skill-load-data.md` step 2
3. Run `git diff data/` to see what changed in the data
4. Roll back with `git checkout data/deals.csv` if needed
