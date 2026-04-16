# Mikal Nielsen Website Redesign — Implementation Notes

## File Structure

```
Mikal.nz/
├── comparison.html   ← Start here — shows all 3 options side-by-side
├── option-a/index.html  — "The Quiet Authority" (Navy + Gold + Off-white)
├── option-b/index.html  — "The Mental Fitness Coach" (Black + Teal)
├── option-c/index.html  — "The Wise Guide" (Forest Green + Beige + Terracotta)
└── NOTES.md
```

## How to Preview

Open `comparison.html` in a browser. It shows scaled previews of all 3 options plus full-open links.
Or open any `option-*/index.html` directly for full 1440px desktop view.

## What Needs Swapping In (search `<!-- SWAP` in any HTML file)

| Asset | Where | Notes |
|-------|--------|-------|
| Mikal's headshot | Hero, About sections | Replace `picsum.photos` placeholder img src |
| Book cover image | All 3 options — Book section | Get from Amazon product page for B0DJ311KH1 |
| Podcast cover art | Option B — Podcast hub | Upload to `/assets/podcast-cover.jpg` |
| Speaking photo | Option C — Speaking section | Replace picsum placeholder |
| Calendly link | All nav CTAs + CTA sections | Replace `href="#contact"` or `mailto:` |
| Anchor.fm podcast ID | All options — Podcast sections | Needed to auto-fetch episode list from RSS |
| Email form action | All options — Newsletter forms | Wire to ConvertKit / Mailchimp |
| GeniusU referral link | Option B — Assessment section | Mikal's Wealth Dynamics referral URL |
| Client photos | Testimonials | Only if client permission is given |
| Real episode data | Podcast episode cards | Once RSS feed URL is confirmed |

## Podcast RSS
- Spotify Show ID: `0J6Fym5smsiD4i4WIGUUTv`
- RSS URL pattern: `https://anchor.fm/s/[ANCHOR_ID]/podcast/rss`
- To auto-fetch episodes: use a lightweight JS fetch on page load, parse RSS XML, render latest 3

## Verified Links (all confirmed from brief)
- Spotify: https://open.spotify.com/show/0J6Fym5smsiD4i4WIGUUTv
- Apple Podcasts: https://apple.co/4keHyjf
- YouTube: https://www.youtube.com/watch?v=kMZ_c7WypzU
- Amazon Book: https://www.amazon.com/dp/B0DJ311KH1
- Email: coach@mikal.nz
- LinkedIn: https://www.linkedin.com/in/mikalnielsen/

## Tech Decisions
- All files are self-contained HTML (no build tools needed)
- Google Fonts loaded via CDN
- No JS frameworks — vanilla JS only (tab switcher in Option B)
- All responsive at mobile breakpoints (900px)
- Designed at 1440px desktop width

## Recommended Implementation Stack (after direction chosen)
- **Static**: Keep as HTML/CSS + Netlify or Vercel deploy
- **CMS option**: Eleventy or Astro (adds blog/podcast management)
- **Current host** (Squarespace): Could recreate chosen design in Squarespace, but HTML implementation gives more control

## Priority Feature List (post-direction)
1. Calendly embed for discovery call booking
2. Podcast RSS auto-feed (requires Anchor.fm ID)
3. Email capture form wired to ESP
4. Real photos replacing all placeholders
5. Book cover image from Amazon
6. SEO meta tags + Open Graph
