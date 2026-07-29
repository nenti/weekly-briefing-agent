---
name: briefing-page
description: Render a weekly briefing as one clean, calm HTML page. Fires when the Weekly Briefing Agent has worked through the inbox and calendar and needs to write briefing.html.
---

# Briefing page

**Look at `example/briefing-example.html` before you write anything.** That is the
standard to hit: a photo up top, a warm one-line greeting, a row of counts, then the
sections. Match that level of finish — don't settle for a plain list.


Turn the briefing into a single self-contained `briefing.html` in the repo root.
The reader skims it in two minutes with a coffee. It should feel calm and finished —
not a wall of text, not a dashboard.

## Structure (in this order)

1. **Header** — the person's name (from `me.md`) + the week range, e.g. "Alex's week ·
   28 Jul – 1 Aug". One line under it: how many things actually need them today.
2. **Reply today** — the strict list. Each item is a card: sender, a one-line *why it
   matters*, and a greyed **first-draft sentence** they could send. Most urgent first.
3. **Decisions waiting on you** — each: the decision in one line + the options.
4. **Your week ahead** — the calendar in order. Prep-needed, double-bookings and
   overloaded days get a small red flag. Call the Thursday 15:00 clash out explicitly.
5. **Safe to ignore** — one muted line with the count. Not a list. Proof the agent
   looked, then chose to skip.

## Rules

- Everything on the page traces to a real item in the inbox or calendar. Never invent.
- Tight copy. A reason is one line, not a paragraph.
- One accent colour, lots of white space, system font. It should look good on any
  screen without the reader touching anything.
- Self-contained: inline CSS, no external requests. Works opened straight from disk.

## Style baseline (start here, then make it yours)

```html
<!doctype html><html lang="en"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Weekly briefing</title>
<style>
  :root{--ink:#1a1a2e;--dim:#6b6b7b;--line:#ececf0;--accent:#4338ca;--flag:#dc2626;--bg:#fafafa}
  *{box-sizing:border-box;margin:0}
  body{font:16px/1.6 system-ui,-apple-system,sans-serif;color:var(--ink);background:var(--bg);
    max-width:720px;margin:0 auto;padding:48px 24px 80px}
  header{border-bottom:2px solid var(--ink);padding-bottom:20px;margin-bottom:8px}
  h1{font-size:30px;letter-spacing:-.02em}
  header p{color:var(--dim);margin-top:6px}
  h2{font-size:13px;letter-spacing:.08em;text-transform:uppercase;color:var(--accent);
    margin:40px 0 14px}
  .card{background:#fff;border:1px solid var(--line);border-radius:12px;padding:16px 18px;margin-bottom:12px}
  .card .who{font-weight:600}
  .card .why{color:var(--dim);font-size:14.5px;margin:2px 0 10px}
  .draft{background:#f4f4f8;border-radius:8px;padding:8px 12px;font-size:14px;color:#333;
    border-left:3px solid var(--accent)}
  .cal{list-style:none;padding:0}
  .cal li{display:flex;gap:12px;padding:8px 0;border-bottom:1px solid var(--line)}
  .cal .t{font-variant-numeric:tabular-nums;color:var(--dim);flex:0 0 96px}
  .flag{color:var(--flag);font-weight:600;font-size:13px}
  .ignore{color:var(--dim);font-size:14px;margin-top:14px}
</style></head><body>
  <!-- header, then the five sections as above -->
</body></html>
```

Adjust `--accent` to taste — the page is the person's, let it feel like theirs.
