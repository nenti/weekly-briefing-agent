# The "build your agent" prompt

Paste this after you've opened the project in Claude Code. It interviews you and writes
your agent's identity from your answers. No code — you're briefing an assistant, not
programming one.

---

```
You're going to help me build my own AI agent, step by step. I'm in a workshop, I'm not a
developer, so keep it simple and ask me one question at a time.

The agent will live in this project. What's already here:
- data/inbox.md and data/calendar.md - a week of my emails and meetings
- me.md - who I am
- rubric.md - what matters to me
- example/briefing-example.html - what a good result looks like
- a skill called briefing-page that renders the finished page

Interview me. One question at a time, wait for my answer before the next:

1. In one sentence: what should this agent do for you every week?
2. When it has gone through your week, what should it hand you? For example: the replies
   that actually need you, decisions waiting on you, what's coming up, what it ignored.
3. How strict should it be - a few things that genuinely need you, or everything that might?
4. Should it ever send anything on your behalf, or only prepare drafts for you to check?
5. When it's unsure whether something matters, what should it do?
6. Anything it should never do?

Then write two files from my answers.

IDENTITY.md - this is the agent itself, in plain English:
- open by saying who it is and who it works for, in my words
- send it to me.md for who I am, and rubric.md for what matters to me
- point it at data/inbox.md and data/calendar.md, and note that later it can read my real
  Gmail and Google Calendar instead, with everything else unchanged
- lay out the output I asked for, in the order I want it
- tell it to open example/briefing-example.html first and match that standard, then use
  the briefing-page skill to write briefing.html
- carry my rules, especially the one about sending

CLAUDE.md - three lines only: read IDENTITY.md, then me.md and rubric.md.

Write both in plain English, no code, no jargon - like instructions to a sharp new
assistant on their first day. Show me IDENTITY.md when it's done, and tell me in one line
what to say next to make it run.
```

---

**Why two files.** `IDENTITY.md` is the portable part — plain English, no tool anywhere in
it. Take that file to Cursor or any other coding agent and it still describes your agent.
`CLAUDE.md` is only the door Claude Code walks through.

**If you get stuck or run short on time:** `workshop/IDENTITY.example.md` is a finished
version. Copy it to `IDENTITY.md` in the main folder and carry on.
