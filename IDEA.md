# CurbAlert — Neighborhood Curbside Giveaway Board

> Idea for Project #1 of 5–6 new Neighborhood Hacks builds. Spec only — not yet built.

## One-liner
Neighbors post "free stuff going out on the curb" with a pickup window; others claim it before trash day. Keeps usable goods out of the landfill.

## Why it's original (vs. the 5 existing projects)
- **AccessLens** = accessibility directory. **FixSpot** = report broken things. **LostLoop** = lost & found (misplaced items, owner reunion). **StudyPair** = peer study help. **Starter** = generic listings hub.
- None of them cover *intentional curbside giveaways with a time window* — the "someone put a perfectly good couch on the curb at 9pm" phenomenon. Distinct from LostLoop: the item was never lost, the owner wants it gone.

## Core features (keep it small)
1. **Post an alert**: item title, one-line condition note, approximate location (block/cross-street text field, NO maps), pickup window end time, category.
2. **Board**: card grid, newest first, live countdown chip on each card ("Ends in 2h 14m", turns amber/red near expiry).
3. **Claim / Unclaim toggle** — one click, no accounts. Claimed cards dim but stay visible until expiry, then auto-hide from the active board (archive toggle to show expired).
4. **Search + category filter + status filter** (same pattern as StudyPair's filter bar — proven, cheap).
5. **Metrics strip**: Active Alerts, Claimed Today, Items Rescued (count), plus one fun stat like "≈ lbs kept out of landfill" estimated from a per-category weight hint.
6. **Demo data**: 4–5 seed records (e.g. working desk lamp, moving boxes, kid's bike w/ flat tire, houseplants, bookshelf).
7. **💾 Data modal**: export JSON / restore demo dataset — reuse StudyPair's exact pattern.

## Deliberately NOT building (token budget)
- No accounts, no maps/geolocation, no images/photos, no push notifications, no routing.
- No test-runner.js unless you ask — plain single `index.html` + short README, per your "skip the md rules" note.

## Est. size
~1200–1500 lines single file, smaller than StudyPair (2253) since no role switcher / hint ladder state machine — just CRUD + countdown timer + filters.

## Visual
Same late-night palette family as the other projects but flipped: warm amber/orange accent ("porch light" feel) on dark slate, to feel distinct in a demo reel.
