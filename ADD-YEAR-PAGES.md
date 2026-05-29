# Add a results page for every year (instructions for Claude Code)

Goal: create one page per tournament year — `results-2012.html` through
`results-2024.html` — all matching the existing `results-2025.html` template
(header → intro → group photo → results image → year nav). 2025 already exists.

## Paste this to Claude Code

> Using `results-2025.html` as the template, create a results page for every other
> year of the tournament: `results-2012.html` through `results-2024.html`. For each
> page, clone the template and update only the content (keep all classes, styles,
> structure, the nav, and the footer identical):
>
> 1. **`<title>`** → `[YEAR] · Dirty Birdie Summer Classic`
> 2. **Header eyebrow** → `[Nth] Annual · The Summer Classic` (see the “Edition”
>    column below).
> 3. **Header `<h1>`** → the year.
> 4. **Header meta row** → Location and Champion from the table. Keep “Dates” as
>    `Summer [YEAR]` unless I give you exact dates.
> 5. **Intro paragraph** → rewrite for that year, e.g. “The [Nth] Dirty Birdie
>    Summer Classic was held in [Location]. Congratulations to [Champion], the
>    [YEAR] overall champion.” Bold the champion’s name.
> 6. **Champion callout** → champion name + location.
> 7. **Group photo** → point the `<img>` at `images/group-[YEAR].jpg` and update the
>    caption to `// The [YEAR] field · [Location]`.
> 8. **Results section** → if a results image exists, point it at
>    `images/results-[YEAR].jpg` and caption it. **If there’s no results image for
>    that year, delete the entire “FINAL RESULTS” `<section>`.**
> 9. **Year nav** → on every page, mark the current year’s link with `class="active"`
>    (remove `active` from 2025 on the other pages).
>
> The archive links already point to `results-[YEAR].html`, so the new pages link up
> automatically. Then update the “2025 Champion” area is fine to leave as-is.

## Tournament data

| Year | Edition | Champion | Location |
|------|---------|----------|----------|
| 2025 | 14th | Alim Walji | Whistler, BC |
| 2024 | 13th | Ally Bharmal | Victoria, BC |
| 2023 | 12th | Rahim Kabani | Whistler, BC |
| 2022 | 11th | Ray Jaffer | Whistler, BC |
| 2021 | 10th | Shafiq Kara | Predator Ridge, BC |
| 2020 | 9th | Rahim Dhanji | Whistler, BC |
| 2019 | 8th | Ray Jaffer | Whistler, BC |
| 2018 | 7th | Aleem Teja | Bellevue, WA |
| 2017 | 6th | Haneef Hameer | Whistler, BC |
| 2016 | 5th | Karim Walji | Whistler, BC |
| 2015 | 4th | Amyeen Hassanali | Whistler, BC |
| 2014 | 3rd | Riz Mitha | Whistler, BC |
| 2013 | 2nd | Shafiq Kara | Seattle, WA |
| 2012 | 1st | Ally Bharmal | Predator Ridge, BC *(inaugural)* |

*(Two-time champions, for reference: Ally Bharmal 2012 & 2024, Shafiq Kara 2013 &
2021, Ray Jaffer 2019 & 2022.)*

## Photos — reuse what already exists

The old WordPress site already has group shots and result screenshots. Grab them and
drop them into `images/`, renamed to match:

- Group photos → `images/group-[YEAR].jpg`
- Results screenshots → `images/results-[YEAR].jpg`

Many old group shots follow the pattern
`https://dirtybirdie.ca/wp-content/uploads/2022/05/DBGroupShot[YEAR].jpg`
(e.g. `DBGroupShot2013.jpg`). The exact filenames vary year to year, so:

> Claude Code: for each year, check the old page at
> `https://dirtybirdie.ca/dirty-birdie-[YEAR]/` for its group photo and results
> image, download them into `images/` as `group-[YEAR].jpg` / `results-[YEAR].jpg`,
> and wire them into that year’s page. If a year has no results image, omit the
> results section for that year.

## After it’s built
- Check a couple of pages locally (open them in a browser).
- `git add . && git commit -m "Add per-year results pages 2012–2024" && git push`
  — the live site updates automatically.
