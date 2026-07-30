# Start your own agent, from an empty folder

You built the briefing agent from a project that already existed. This is the version where
nothing exists yet — the five minutes between an idea and a working agent.

Same three moves every time: **read a source → judge it against a rubric you wrote → write
where you already look.**

---

## 1 · Make a folder and open it

One folder per agent. Keep them apart — an agent with one job does it well.

```
~/agents/lead-screener/
```

Open that folder in Claude Code. Empty is fine; that's the point.

## 2 · Let it set the project up

You don't need to know git. Ask:

> Set this up as a project: make it a git repository, add a README that says what this agent
> is for, and create a private repo on my GitHub called lead-screener.

A repo isn't bureaucracy here. It's what lets you **change your agent's mind and take it
back** — every version of your instructions is kept, so you can experiment without fear.
It's also what makes the agent runnable in the cloud later.

## 3 · Write the purpose — before anything else

This is the step people skip, and it's the one that decides whether the agent is any good.
Don't write a task list. Write **who it is and what it's for**, in plain English.

> Interview me and write `IDENTITY.md` for this agent. Ask me one question at a time:
>
> 1. What is this agent for — in one sentence, as if you were describing a new hire's job?
> 2. What does it read? Files in this folder, a connected tool, a website?
> 3. How should it judge what it finds — what's important to me, what's noise?
> 4. What does it produce, and where does that land?
> 5. What may it never do? Anything it must ask me before doing?
> 6. When it's unsure, what's the safe move?
>
> Then write IDENTITY.md in plain English, no code, no jargon — like a briefing for a sharp
> new assistant. Also write a three-line CLAUDE.md that just points at IDENTITY.md.

**Why `IDENTITY.md` and not `CLAUDE.md`.** The identity is portable: no tool is named in it,
so it works in Cursor, Codex, or whatever you move to next. `CLAUDE.md` is only the door
Claude Code walks through. One idea, two files, and the valuable one isn't locked to a vendor.

## 4 · Give it something real to read

An agent with no source is a chatbot. Pick one:

| Source | How |
|---|---|
| Files | Drop them in a `data/` folder. Simplest, nothing to connect, nothing at risk. |
| Gmail, Calendar, Notion, Drive | Connect once at [claude.ai → Connectors](https://claude.ai/customize/connectors). One click, no API key. |
| A public API | Just name it: *"use openholidaysapi.org for the next public holidays."* |
| A website | Give it the URL and say what to pull out. |

Start with files even when you intend to use the real thing. It gets you to a working agent
in minutes, and the swap to live data is a one-line change afterwards.

## 5 · Show it what "good" looks like

The one move that lifts output the most, and almost nobody does it: **give it a target.**

Put an example of the finished thing in the project — a page you like, a report in the right
shape, even a rough sketch — and tell `IDENTITY.md` to open it first and match that standard.
Without a target the agent invents its own, and its own is average by construction.

## 6 · Optional, but the compounding part: give it a vault

The workshop agent starts fresh every run. The strongest agents don't — they keep a
**vault**: a folder of markdown notes that grows with every run.

```
vault/
  runs/2026-08-04.md        what it did, what you corrected, why
  people/marta-kern.md      what it has learned about the people it deals with
```

Two lines in `IDENTITY.md` make it real:

> Before you start, read the vault — it's what you know beyond this week's data.
> When you're done, write down what you learned and what I corrected.

That's the difference between a tool and a colleague: *"last time you said this draft
was too formal"* only happens if somewhere, a note says so.

Practical notes:

- It's just markdown files. Point [Obsidian](https://obsidian.md) (free) at the folder
  and you can read your agent's memory like a wiki — link notes with `[[wikilinks]]`
  and the graph view shows how they connect.
- Skip it on day one if you like. From week two it's the biggest lever there is: an
  agent with a vault gets better at **your** work every run; one without starts from
  zero every time.

## 7 · Run it, then fix the instructions — not the output

> Do your job. Read what you're supposed to read, apply my rubric, produce the result.

When something's wrong, resist correcting the output by hand. Change `IDENTITY.md` or your
rubric and run it again. Editing output fixes today; editing instructions fixes every run
after that.

Two or three rounds of this and it starts feeling like yours.

## 8 · Only then, let it off the leash

In this order — each step earns the next:

1. **You run it, it drafts.** You check everything. Stay here until you'd bet on its output.
2. **Scheduled on your laptop.** `/schedule` a run. Same agent, you just stop asking.
3. **A cloud routine.** Runs on Anthropic's infrastructure, laptop shut. Needs the project
   pushed to GitHub, and only sees the connectors set up at claude.ai — what you connected
   locally does not travel with it.
4. **It acts.** Sends, files, updates another system. Only for the cases you've watched
   often enough to trust, and never for the ones that are expensive to get wrong.

Make it say which data it actually used in every run. An agent that quietly falls back to
sample data and reports it as your real week is worse than no agent at all.

---

## The short version

```
folder  →  git repo  →  IDENTITY.md (who it is)  →  a source  →  an example of good
        →  a vault that grows  →  run  →  fix the instructions  →  schedule  →  trust it with more
```

Skipping straight to step 8 is how people end up with an agent nobody believes.
