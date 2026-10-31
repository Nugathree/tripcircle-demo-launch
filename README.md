# TripCircle Interactive Demo Prototype

Open this folder over http for live Rive, not just as a file, because browsers block wasm from a file path. From this folder, run:

python3 -m http.server 8321

Then open http://127.0.0.1:8321/index.html

If you open index.html directly as a file, the page still works, but JourneyGenie Rive falls back to a static image, and a note on screen says so. That fallback is deliberate, not a silent fail.

## What it is

A single clickable HTML prototype, no build step. Clicks change screens, typing appears slowly, toggles change state, votes move, check-ins change to checked in. Sample data only, labeled MVP sample data only not a live app on every screen, in the top banner and on the close screen.

Brand: Keppel #3AB7A5, ink #0E6B5E, Soft Black #1C1C1C, Sora headings, DM Sans body, full borders or tints only, no side stripes, no em or en dashes, buttons 44px or taller, light and dark toggle in the header.

Rules kept: no live booking claim, no live visa claim, expense tracking only, no money moves through TripCircle, organization side only on camera, never the Loumi name, JourneyGenie always in full, one JourneyGenie at a time, no double lamp.

## Click path for recording, in order

1. Wrong airport hook text: read the hook, tap "See how it goes right".
2. Moodboard: type a trip idea (the share card updates as you type), tap "Copy share link", tap "Send one link, watch the group join" and watch members appear one by one.
3. JourneyGenie chat: tap "Ask about dates", "Ask about budgets", "Ask about preferences", watch JourneyGenie type slowly, letter by letter. Type a reply and tap "Send reply". On the same screen, tap "Make JourneyGenie celebrate" for FullForm Celebrating, then "Switch to LampWorld Meal", then "Back to FullForm". Only one Rive canvas is shown at a time.
4. Vote: tap "Vote for Option A" (or B or C), watch that vote count move up by one and the card highlight.
5. Confirm: tap "Confirm Member B" and "Confirm Member C", watch amber Pending turn green Confirmed.
6. Expense split: tap "Send reminder to Member B" and to Member C, watch the reminder state change to "Reminder sent, sample only".
7. Wallet check-in toggle: tap "Mark flight checked in" and "Mark hotel checked in", watch the pills change to checked in, manual. This is adapted from the wallet design preview, not a screenshot.
8. Party view filter: tick "Show unchecked only", tick "Show visas not approved yet", untick them, then tap "Demo: mark all sample members checked in" and watch the "All checked in" banner appear.
9. Organization dashboard: tap "Youth trips", then "Adult trips", read the caption change, tap "Open roster".
10. Roster: tick and untick the eligibility boxes, watch the missing count change.
11. Gated check-in: tick all 3 required items, watch "Check in, locked" change to "Check in now", tap it.
12. Announcement: edit the announcement text, tap "Send announcement", watch it appear as a sent announcement card.
13. Adult board: tap "Mark flight checked in" and "Mark hotel checked in", watch states change. States only, no files, no visa details, no booking refs.
14. Trip day payoff: tap "8am: Bus leaves", "11am: Game and group photo", "6pm: Bus home", each detail opens right under that stop.
15. Close MVP: read the MVP close, tap "Replay from the hook" if a second take is needed.

The top "Next step" and "Back" buttons walk the same 1 to 15 order, and the numbered jump menu jumps to any step for a retake.

## What is interactive, and what is still a static image, honestly

Interactive, not screenshots:
- Trip home, moodboard, share link, member join
- JourneyGenie chat typing, questions, reply, Rive FullForm Idle and Celebrating, Rive LampWorld Meal
- Vote cards and counts, confirm view, expense split reminders
- Wallet check-in toggles, party view filters and all-checked-in banner
- Organization tabs, eligibility checklist count, gated check-in lock and unlock, announcement composer and sent card, adult board state buttons, trip day stop expanders
- Light and dark toggle, Next, Back, and jump navigation

Still static images, with interactive controls around them:
- Organization dashboard, roster, wallet list, wallet detail, announcement, adult board, and trip day payoff frames, in loumi/frame-01-dashboard.png through frame-07-payoff.png. The images do not change when you click inside them. The tabs, checklists, gate, composer, board buttons, and stop expanders below and around them are interactive, and the Next and Back buttons move you through them in order.
- JourneyGenie Popcorn, Social, and Clean: original whole images only, in assets/JG_fresh_popcorn.png, JG_fresh_offduty_social.png, and JG_fresh_offduty_clean.png. Their Rive runtime shots are deliberately not used, because those runtime captures showed a black bar in Chromium. FullForm and Meal use live Rive, not screenshots.
- JourneyGenie on the close screen: a static full form image, so the close screen does not show two JourneyGenies at once with the Rive canvas.

## Files in this folder

- index.html, the whole prototype
- assets/rive.js, assets/rive.wasm, assets/journeygeniefullform.riv, local copies of the verified Rive file
- assets/JG_fresh_fullform.png, JG_fresh_meal.png, JG_fresh_popcorn.png, JG_fresh_offduty_social.png, JG_fresh_offduty_clean.png
- loumi/frame-01-dashboard.png through frame-07-payoff.png
- README.md, this file

## Checks done

- HTML served over local http, index.html returned 200, 36,038 bytes
- JavaScript syntax checked with node --check, passed
- No em or en dashes in index.html
- No Loumi name in index.html, organization side only
- Every local asset referenced by the page exists in this folder
- Rive live rendering was not re-verified in a browser in this build, because this subagent cannot operate a live browser. The Rive pattern, runtime files, and .riv are the verified 2026-10-31 set, and the page falls back to a static image with an on-screen note if Rive cannot load from a file path. Record over http, and check the Rive canvas on screen before filming step 3.
