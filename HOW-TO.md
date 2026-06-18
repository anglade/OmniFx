# OmniGroup case-study system — how to build a chapter

You have a reusable shell (`template.html`) and one finished chapter (`index.html` = OmniFx). Every new venture is now a fill-in job, not a rebuild. Here's the whole process.

## The idea in one line

Four ventures, four subdomains, one continuous story. Each chapter looks and moves identically, walks through the same 7-act spine, and hands off to the next — so the set reads as one body of work by one builder. `philipanglade.com` is the hub; each venture is a chapter.

## Build a new chapter in 4 steps

1. **Copy** `template.html` → rename to `index.html`.
2. **Set the 3 knobs** (top of the file):
   - Accent color — `:root` `--accent` and `--accent-light` (pairs below).
   - Venture name — search `[VENTURE]`.
   - Chapter number — search `[NN]`.
3. **Fill the brackets.** Search `EDIT:` to jump between fields, `[ ]` for the copy. The 7 acts are already in order — you're swapping words, not structure.
4. **Swap images.** Search `SWAP` — one portrait/photo + up to six testimonial thumbnails. (No images? The page still looks finished; just delete the proof section.)

Then deploy exactly like OmniFx: new GitHub repo → new Vercel project → add the subdomain → add the CNAME in GoDaddy.

## The 7-act spine — what each act is for

| Act | Job | OmniFx example |
|---|---|---|
| 01 The gap | The problem you saw | Signal-dependency kept traders stuck |
| 02 The bet | The contrarian insight (pull-quote) | #YouAreTheIndicator |
| 03 The build | How it got made, by hand | Self-taught Premiere, Photoshop, Teachable |
| 04 The machine | The system (the diagram that assembles) | Ads → webinar → course → SMS → community |
| 05 The peak | The numbers (count up) | $1.2M, 30K, 1M+ impressions |
| 06 The turn | What changed / the pivot | iOS 14.5 → wind down the ads |
| 07 What it became | The takeaway + handoff | Became OmniVentures → |

If a venture genuinely doesn't have one act (e.g. no "machine"), keep the section but reframe it — don't delete it. The repeated rhythm is what makes the set feel like a system. The rail labels can be renamed to fit.

## Accent pairs (starting points)

Set both in `:root`. First value = `--accent`, second = `--accent-light`.

- **OmniFx** — `#d62b22` / `#ff7a6e`  (done)
- **OmniVentures** — `#0e7c6b` / `#4fd1bb`  (deep teal — travel / premium)
- **OmniPool** — `#3a5a8c` / `#86a9e0`  (restrained slate-blue — keep it dignified)
- **OmniGiving** — `#3f7d3a` / `#84c97a`  (green — growth / giving)

## Count-up number formats

In the hero and peak grid, `.countup` elements animate from 0. Set `data-num` to the raw number and `data-fmt`:

- `money-m` → `$1.2M`  (use `data-num="1.2"`)
- `money-k-mo` → `$60K`  (use `data-num="60"`)
- `comma-plus` → `30,000+`  (use `data-num="30000"`)
- `compact-plus` → `1M+`  (use `data-num="1000000"`)

For non-numeric values (`<10`, `8:1`, `1`), just type them into `.n` and remove the `countup` class + data attributes.

## The handoff (coming-soon → live)

Each chapter ends pointing at the next. The template ships in **coming-soon** state (muted, non-clickable) so nothing 404s. When the next chapter goes live:

- Change `<div class="nextchap soon rv">` → `<a class="nextchap rv" href="https://[next].philipanglade.com">`
- Delete ` · Coming soon` from the eyebrow.
- Close with `</a>` instead of `</div>`.

OmniFx is already set to coming-soon for OmniVentures — flip it once OmniVentures is live.

## Suggested chapter order & subdomains

1. `omnifx.philipanglade.com` — OmniFx (live)
2. `omniventures.philipanglade.com` — OmniVentures
3. `omnipool.philipanglade.com` — OmniPool
4. `omnigiving.philipanglade.com` — OmniGiving

A note on OmniPool: that chapter's "turn" act carries the broker fraud and wind-down. The honest, victim-of-fraud framing you already use verbally is the right call here — the template's "be honest and specific" turn section is built for exactly that. Worth drafting that copy carefully and separately before it goes public.

## Optional later: a hub index

Once two or more chapters exist, a small landing grid at `philipanglade.com/work` (or the hub itself) linking all four chapters turns the set into a true portfolio. Same design language, four cards. Easy to add when you're ready.
