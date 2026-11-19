# University Application Deadlines – Fall 2027 (student view)

A view-only calendar of 111 Fall 2027 application deadlines (USA, UK, Europe, Hong Kong, Singapore, Canada, Japan).
Students can browse, search and filter it, but there are no add, edit, delete or import controls.

## What students can do
- Month view and List view, with countdowns ("in 12d", red when ≤ 7 days)
- "Coming up" panel with the next 8 deadlines
- Search, filter by country and type, "Hide past deadlines"
- Click any deadline or day to see details and notes (including "verify" notes)
- Keyboard: ← / → change month, `T` jumps to today

## Updating the deadlines (you, not students)
The list lives in two places, which must match:
1. `deadlines.json`
2. the built-in copy (`EMBEDDED_DEFAULTS`) inside `index.html` — used if `deadlines.json` can't load

Simplest workflow: send the changes to Claude to regenerate both, then redeploy:
```bash
cd shared-deadlines-calendar
npx vercel --prod
```
Students see the update the next time they open or refresh the page.

## Deploy (first time)
```bash
cd shared-deadlines-calendar      # the folder containing index.html
npx vercel --prod
```
- Link to existing project? → **N** (make it a new project)
- Framework → **Other**; leave build command and output directory empty

## Note
This version has no server or database: students cannot change anything, and every student always sees exactly
the list you deployed.
