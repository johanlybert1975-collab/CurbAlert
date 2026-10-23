# CurbAlert — demo recording script

**Length: about 2:25. Hard stop: 2:30.** One take, screen recording only. Do each step in order: first the **Do** actions (clicks and text — the text is written out exactly, copy it as-is), then the **Say** line (plain wording, say it however is comfortable, the written line is just there so you don't have to invent sentences while clicking).

---

## Before you record

1. In a terminal, run `npm run dev` and open **http://127.0.0.1:5173/** in your browser.
2. Size the window to about 1280×760, browser zoom at 100%. Close the devtools console.
3. Turn off notifications (one ping mid-take ruins it).
4. Click **storage** in the top bar, then click **load the sample block**. The board must show 5 sample alerts and the stats row must read: **3 on the curb / 0 waiting for pickup / 1 rescued total / ≈6 lbs**.
5. Check the filter row reads: search box empty, category **everything**, state **still grabbable**, sort **newest first**. If unsure, click **reset**.
6. Read through all 9 steps once before you hit record.

---

## The take

### Step 1 — 0:00 to 0:15 — show the board

**Do:** Nothing. Leave the mouse still in the middle of the page so all the cards are visible.

**Say:** "This is CurbAlert. Neighbors post the things they're putting out on the curb, with a deadline, and other neighbors can claim them before the truck comes."

### Step 2 — 0:15 to 0:30 — explain the countdown colors

**Do:** Move the mouse over the countdown text on the **Toaster oven** card (green, about 11h), then over the countdown on the **Moving boxes** card (amber, about 2h).

**Say:** "Every card has a live countdown. Green means you've got time. Amber means under three hours. Red means under thirty minutes — the truck's basically here. Grey means the window already closed."

### Step 3 — 0:30 to 0:42 — trash-day strip

**Do:** Point at the yellow strip above the stats row. Read the date on it. Then click the small **got it** button on the right of the strip to dismiss it.

**Say:** "There's also a strip up top that tells you when the next bulk pickup is, so nobody puts a couch out a week early. You can dismiss it."

### Step 4 — 0:42 to 1:10 — post a new alert

**Do:**

1. Click the orange **put something out** button in the top right.
2. In the box labeled **what is it?** type exactly: `Floor lamp, works, remote included`
3. In the box labeled **condition note** type exactly: `Bulb included. Shade has a small dent in the back.`
4. In the box labeled **where on the block?** type exactly: `curb at 1400 Juniper, next to the fire hydrant`
5. Leave **kind of stuff** on `🛋️ Furniture` and **pickup window** on `tonight (12h)`. Don't change them.
6. Click **ring the bell**.

**Say:** "Posting takes a few seconds. What it is, what condition it's in, roughly where — cross-street level, never a full address — and how long it'll stay out. No account, no phone number."

*(Tip: if typing live slows you down, have these three lines ready to paste, one per box.)*

### Step 5 — 1:10 to 1:27 — the new card, badge and +3h

**Do:**

1. Point at the new card at the top of the board. Point at the small blinking tag that says **just posted**.
2. On that same card, click the small **+3h** button (right of **call dibs**). The countdown jumps up by 3 hours — it goes from about `11h 59m left` to `14h 59m left`.

**Say:** "The new card lands at the top with a 'just posted' tag and its countdown starts immediately. Nobody has to make an account. And if nobody's claimed it yet, anyone can add three hours to the window with this button."

### Step 6 — 1:27 to 1:55 — claim it, then mark it picked up

**Do:**

1. Find the card titled **Toaster oven, heats fine, knob is finicky** (second card, right under the lamp). Click **call dibs** on it.
2. The card disappears from the list. That is correct — it's no longer grabbable.
3. Click the state dropdown that says **still grabbable** and choose **claimed**. Two cards now show: your toaster (it says "claimed by you") and the sample pothos.
4. On the toaster card, click **picked it up**.
5. Move the mouse along the stats row and stop on the last number.

**Say:** "Calling dibs is one click, and the card leaves the open list so it's obvious someone got it. Then when you've actually carried it home, you click 'picked it up' — and the counters update: waiting for pickup back to zero, two rescued total, about sixteen pounds kept out of the truck."

### Step 7 — 1:55 to 2:06 — sorting

**Do:**

1. Click the state dropdown and choose **show it all** (so all cards are visible).
2. Click the sort dropdown that says **newest first** and choose **ending soonest**. The cards reorder — the moving boxes with about 2 hours left jump to the top.
3. Leave it as is; a refresh resets it anyway.

**Say:** "You can also sort by whichever window ends soonest, so nothing slips past you."

### Step 8 — 2:06 to 2:18 — storage and refresh

**Do:**

1. Click **storage** in the top bar.
2. Point at the **download .json** line — don't click it. Then click **close**.
3. Press **F5** to refresh the page.
4. After the page reloads, point at the stats row: it still reads **2 rescued total** and **≈16 lbs**, and the toaster card is still there when you open the state dropdown to **claimed**.

**Say:** "Everything lives in this browser — there's a JSON export if you want a backup, and after a refresh everything's still here. No server, no tracking."

### Step 9 — 2:18 to 2:26 — close

**Do:** Set the state dropdown back to **still grabbable** if it isn't already, leave the full board on screen, and stop recording.

**Say:** "That's CurbAlert — React and Vite, no backend, no accounts. Built for Neighborhood Hacks."

**Total: about 2:25.**

---

## If you're running long

Cut **Step 3** (trash strip) and **Step 7** (sorting) completely. That brings you to about 2:00, and the story (post → claim → pick up → refresh) still holds together.

## If something goes wrong mid-take

- **The new card isn't at the top:** a filter or sort is set differently than you thought. Click **reset** in the filter row, redo Step 4.
- **Clicking "call dibs" did nothing:** you clicked a card that was already claimed (dimmed cards are taken). Click dibs on a bright card instead.
- **The card vanished after "call dibs" and you're confused:** that's expected — switch the state dropdown to **claimed** to see it again (Step 6, point 3).
- **Stats numbers don't match this script:** someone's earlier test data is on the board. Click **storage** → **load the sample block**, and start again from Step 1. The numbers in this script assume a fresh sample block.
- **You flubbed a sentence:** pause for a beat, say the sentence again, keep recording. You can cut it later.

## After the recording

Click **storage** → **load the sample block** so the app is left in the clean starting state for the next person.
