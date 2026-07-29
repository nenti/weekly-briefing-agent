# Weekly Briefing Agent

Your first AI agent. It reads a week of email and calendar, decides what actually needs
you, and writes the replies that matter — as one clean page.

You configure it in plain English. **No code.**

> Built live at **Hands-On with Claude Code** — a Co-Work & session with Vidushi Malhan
> and Tobias Nentwig. Friday 31 July 2026, CIC Berlin.

---

## Before the workshop

Open **[`workshop/prep.html`](workshop/prep.html)** in your browser (download it, then
double-click). It has the checklist — Claude subscription, Claude Code, GitHub, laptop —
plus the [**About me prompt**](workshop/about-me-prompt.md): paste it into Claude, it
interviews you and writes a short profile of how you work. Bring that with you. It's the
first thing your agent reads, and it stays useful in any AI tool afterwards.

## What it does

```
data/inbox.md  +  data/calendar.md          your week (sample data to start)
                    |
                    v
        reads it, judges it against
        rubric.md  (what matters to YOU)
                    |
                    v
        briefing.html                        replies to send - decisions - week ahead
```

The pattern under every agent you'll ever build: **read a source → judge it against your
rubric → write where you already look.**

## Build it

1. Clone this project and open the folder in Claude Code.
2. Make it yours: edit `me.md` (who you are) and `rubric.md` (what matters to you).
   Plain sentences — this is where your About me goes.
3. Say:

   > Read my inbox and calendar, apply my rubric, and build my weekly briefing.

4. Open `briefing.html`. That's your agent's work.
5. Not happy with a call it made? Change your rubric, run it again. That's iterating.

## Make it real

- **Your own inbox.** Connect the Gmail + Google Calendar connector at
  claude.ai → Settings → Connectors (one click, needs Claude Pro/Max). Then in
  `CLAUDE.md`, swap the sample-file line for *"my last 7 days of Gmail and this week's
  calendar."* Re-run. Same briefing, your real week.
  *Tip: point it at a throwaway account first, not your main one, until you trust it.*
- **On a schedule.** Ask Claude Code to `/schedule` a run every Monday at 08:00.
  (A local schedule runs while your computer is on.)

## Files

| File | What it's for |
|---|---|
| `me.md` | Who you are — the agent writes *for* you. |
| `rubric.md` | What matters to you — the agent judges *by* this. |
| `data/inbox.md` | Sample emails. Later: your real inbox. |
| `data/calendar.md` | Sample calendar. Later: your real calendar. |
| `CLAUDE.md` | The agent's standing instructions. Read it — it's plain English. |
| `.claude/skills/briefing-page/SKILL.md` | How the briefing page gets built. |
| `workshop/` | Prep page, slides, and the About me prompt. |

The agent **drafts, it never sends.** Everything it produces is yours to check first.
