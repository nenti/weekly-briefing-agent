# The "build your agent" prompt

This is the one you paste at the workshop, after you've opened the project in Claude Code.
It interviews you and writes your agent's instructions — the `CLAUDE.md` file — from your
answers. No code. You're briefing an assistant, not programming one.

---

```
You're going to help me build my own AI agent, step by step. I'm in a workshop, I'm not a
developer, so keep it simple and ask me one question at a time.

The agent will live in this project. What's already here:
- data/inbox.md and data/calendar.md - a week of my emails and meetings
- me.md - who I am
- rubric.md - what matters to me
- a skill called briefing-page that renders a polished HTML page

Interview me. One question at a time, wait for my answer before the next:

1. In one sentence: what should this agent do for you every week?
2. When it has gone through your week, what should it hand you? For example: the replies
   that actually need you, decisions waiting on you, what's coming up, what it ignored.
3. How strict should it be - a few things that genuinely need you, or everything that might?
4. Should it ever send anything on your behalf, or only prepare drafts for you to check?
5. When it's unsure whether something matters, what should it do?
6. Anything it should never do?

Then write the file CLAUDE.md in this project, based on my answers. It must:
- open by telling the agent who it is and who it works for, in my words
- send it to me.md for who I am, and rubric.md for what matters to me
- point it at data/inbox.md and data/calendar.md, and note that later it can read my real
  Gmail and Google Calendar instead, with everything else unchanged
- lay out the output I asked for, in the order I want it
- tell it to use the briefing-page skill to write briefing.html
- carry my rules, especially the one about sending

Write it in plain English - no code, no jargon. It should read like instructions to a
sharp new assistant on their first day. Show me the file when it's done, and tell me in
one line what to say next to make it run.
```

---

**If you get stuck or run short on time:** `workshop/CLAUDE.example.md` is a finished
version. Copy it to `CLAUDE.md` in the main folder and carry on — you can always come back
and build your own.
