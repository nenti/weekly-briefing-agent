# Weekly Briefing Agent

Your first AI agent. It reads a week of email and calendar, decides what actually needs
you, and writes the replies that matter — as one clean page.

You configure it in plain English. **No code.**

> Built live at **Hands-On with Claude Code** — a Co-Work & session with Vidushi Malhan
> and Tobias Nentwig. Friday 31 July 2026, CIC Berlin.

---

## Doing this on your own?

**[`workshop/guide.html`](workshop/guide.html)** is the full walkthrough — nine steps at your
own pace, from empty machine to an agent that runs without you. Download it, open it in a
browser. Starting a *different* agent from scratch?
**[`workshop/start-your-own-agent.md`](workshop/start-your-own-agent.md)**.

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

1. Clone this project and open the folder in Claude Code. Best as your own copy — ask it to
   create a private repo named `yourname-briefing-agent` on your GitHub and push there; that
   keeps your agent versioned and ready for cloud runs later.
2. **Drop in your About me.** Paste the profile Claude wrote for you into `me.md`.
3. **Build your agent.** Paste the prompt from
   [`workshop/build-your-agent-prompt.md`](workshop/build-your-agent-prompt.md). It asks
   you six questions — what your agent should do, how strict it should be, whether it may
   ever send anything — and writes **`IDENTITY.md`** from your answers.
   **That file is your agent, and you wrote it.**
4. **Set your rules** in `rubric.md`: what must always reach you, what's safe to skip.
5. Say:

   > Read my inbox and calendar, apply my rubric, and build my weekly briefing.

6. Open `briefing.html`. That's your agent's work.
7. Not happy with a call it made? Change your rubric, run it again. That's iterating.

*Short on time or stuck? `workshop/IDENTITY.example.md` is a finished version — copy it to
`IDENTITY.md` and carry on.*

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
| `IDENTITY.md` | Your agent, in plain English — **you write this** at step 3. Portable: it works in any coding tool. |
| `CLAUDE.md` | Three lines that point Claude Code at the files above. |
| `example/briefing-example.html` | What a good result looks like. Your agent aims at this. |
| `.claude/skills/briefing-page/SKILL.md` | How the briefing page gets built. |
| `workshop/` | Prep page, slides, the prompts, the async guide, and a finished `IDENTITY.example.md`. |

The agent **drafts, it never sends.** Everything it produces is yours to check first.
