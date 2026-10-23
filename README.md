# curbalert 🛋️

**your block is throwing out good stuff and you never find out in time.**

that's the whole app. someone puts a nightstand on the curb at 10pm, the truck takes it at 7am, and the person who would've loved that nightstand slept through it. curbalert is a little board where neighbors post what's going out, for how long, and roughly where — and anyone can call dibs before the window closes.

built in a day for **Neighborhood Hacks**. no pitch deck energy, just a board that works.

---

## run it

```bash
npm install
npm run dev      # → http://127.0.0.1:5173
```

production build:

```bash
npm run build    # → dist/
npm run preview
```

that's it. no API keys, no accounts, no `.env`.

---

## what it actually does

- **put something out** — title, an honest condition note, a cross-street-level location (never a full address — see `ComposePanel.jsx`, we ask for "the block" on purpose), a category, and a pickup window (1h → 2 days). New cards land on top with a blinking **just posted** tag for the first 30 minutes.
- **countdowns, live** — every card ticks every second. Green if you've got time, amber under 3 hours, red under 30 minutes, grey when the truck already came. Any card nobody has claimed yet can get its window pushed out **+3h** with one click.
- **call dibs → picked it up** — claiming is one click and pulls the card off the open list; when the taker has actually carried it home they hit **picked it up**, which is what counts as rescued. No username; it just says "claimed by you."
- **stats strip** — on the curb / waiting for pickup / rescued total / and a fluffy-but-fun **≈ lbs kept out of the truck** (category-based estimates, it's a vibe check, not a weigh-in).
- **filters + sort** — free text (item names *and* cross-streets), category, and state (grabbable / claimed / past window / everything), plus sort by newest first or ending soonest.
- **trash-day strip** — shows the next bulk pickup (Thursdays, 6am) so nobody puts things out a week early. Dismissable.
- **storage panel** — download a `.json`, reload the sample block, or clear the street entirely.

data lives in `localStorage` under `curb-alert/board-v1`. clear your browser data and it's gone — hence the export button.

## how it's laid out

```
index.html            vite entry
src/main.jsx          react root
src/App.jsx           state, stats, filtering, claim/pickup/extend, toasts
src/components/
  Header.jsx          masthead
  Toolbar.jsx         stats + filters
  AlertCard.jsx       the card, countdown logic lives here
  ComposePanel.jsx    the "put something out" form + validation
  StoragePanel.jsx    export / restore / clear
src/lib/
  categories.js       7 categories + their est-lbs guesses
  time.js             countdown, relative time, next-bulk-pickup helpers
  storage.js          localStorage + json download
src/data/seed.js      5 sample alerts (times relative to first paint)
src/styles.css        the whole look, warm paper + porch orange
```

stack: **React 18 + Vite**, plain CSS, zero runtime dependencies beyond React. no router, no state library, no Tailwind — it's a board, not a platform.

## known honest limitations

- claims aren't real claims — anyone can grab anything, there's no identity. fine for a demo, obviously not for a real street.
- the lbs number is a per-category guess, not a scale.
- cross-streets are free text, so yes, someone can write "asdf". welcome to the neighborhood.
- "waiting for pickup" only counts claims made today — yesterday's un-picked-up claim stops showing there (it still counts as claimed on the board).

---

**demo people:** there's a timed recording rundown in [DEMO-SCRIPT.md](DEMO-SCRIPT.md).
