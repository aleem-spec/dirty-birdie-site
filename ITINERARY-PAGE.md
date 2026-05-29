# Itinerary / 2026 host showcase page (instructions for Claude Code)

A new page — `itinerary.html` — showcases the upcoming tournament and shows off the
host course. For 2026 that's **Gamble Sands** in Brewster, Washington. It's already
built and linked; this doc explains the structure and how to refresh it each year.

## What's on the page (top to bottom)
1. **Hero** — full-bleed course photo, "Gamble Sands", location chips (Brewster WA · Columbia River · David McLay Kidd).
2. **Intro** — short pitch for the 2026 destination.
3. **The Courses** — four cards: Gamble Sands, Scarecrow, Quicksands, The Cascades (dark green section).
4. **The Inn** — where the group stays.
5. **Food & Drink** — Danny Boy + The Barn.
6. **Tournament Itinerary** — a 3-day Fri/Sat/Sun timeline (sample times — confirm before the event).
7. **CTA** — links to the Champions Wall and out to gamblesands.com.

## It's already wired
- Nav "Itinerary" link and footer "2026 Host" link point to `itinerary.html` on every page.
- The homepage hero/host CTAs lead here too.

## Add the real photos
Drop these into `images/` (the page already references them):

| Slot | Filename | What to use |
|------|----------|-------------|
| Hero | `images/gs-hero.png` | A wide, dramatic Gamble Sands course shot |
| Course 1 | `images/gs-gamble.png` | The original Gamble Sands course |
| Course 2 | `images/gs-scarecrow.png` | Scarecrow |
| Course 3 | `images/gs-quicksands.png` | Quicksands short course |
| Course 4 | `images/gs-cascades.png` | The Cascades putting course |
| The Inn | `images/gs-inn.png` | The Inn / lodging |
| Dining | `images/gs-dine.png` | Danny Boy or The Barn |

> Claude Code: photos can be sourced from gamblesands.com's media or the resort's
> press kit. Save them into `images/` with the exact filenames above (keep them
> web-sized — long edge ~1600px, JPG). If you change a filename, update the matching
> `<img src>` in `itinerary.html`.

## Confirm the schedule + dates
Edit the **Tournament Itinerary** section with the real dates and tee times once
set. Update the hero eyebrow ("The 15th Annual · Summer 2026") and the intro copy if
anything changes.

## Each new year (changing the host course)
When the tournament moves to a new course, either:
- **Reuse this page:** swap the hero, course cards, stay/dine sections, copy, and
  photos for the new venue — and rename nothing (keep `itinerary.html`), **or**
- Tell Claude Code: *"Update itinerary.html for the [YEAR] host, [Course Name] in
  [Location]. Here are the courses/amenities: … and here are the photos in images/."*

Keep all the classes, section structure, nav, and footer identical — only the
content changes.

## After edits
`git add . && git commit -m "Update 2026 itinerary / Gamble Sands showcase" && git push`
— the live site updates automatically.
