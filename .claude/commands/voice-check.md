---
description: Draft a LinkedIn post in Erin's voice, score it adversarially against the rules, and revise until it passes clean.
argument-hint: <topic>
---

You are drafting and hardening a LinkedIn post in **Erin's voice** on the topic: **$ARGUMENTS**

## Setup

1. Read `erin-voice/SKILL.md` and `erin-voice/voice-exemplars.md` in full before writing anything. These are the authority. The SKILL.md rules are downstream of the exemplars — when a line feels off, judge it against the exemplars, not just the rule list.
2. If `$ARGUMENTS` is empty, ask the user for a topic before proceeding.

## Loop: draft → adversarial score → revise → repeat until clean

### Step 1 — Draft
Write a first-draft post on the topic in Erin's voice. Drop into a scene or specific detail, let one detail breathe, let the turn arrive unannounced, land flat on a line that feels discovered. 150–300 words, one mobile scroll.

### Step 2 — Score adversarially
Score the current draft against **every rule in SKILL.md, one by one** — not a summary, the actual checklist. Be a hostile reviewer trying to fail the draft, not a friendly one looking for reasons to pass. Go section by section:

- **Core instinct** (thinks out loud, lands sharp, sharp line discovered not constructed, never announces the insight)
- **Sentence mechanics** (short varied with long; shorthand/fragments; And/But/So openers; parentheticals; insider language untranslated; arrow bullets only when list-shaped; one reader-question max)
- **Words/phrases she NEVER uses** — check each ban explicitly: "here's the thing"/"here's what I've learned", "key insight"/"key takeaway", "let me break this down", **"not X — it's Y" reframe (anywhere)**, "at the end of the day", **"genuinely"/"straightforward"**, "I really think", **em dashes**, hashtags, emojis, TED/keynote phrasing, "the key is"/"the secret is", questions as closers, **signposted epiphanies** ("that's when I realized", "the part that stuck", and any AI-cadence tell), preachy/moral closers, **symmetrical parallel structure 3x in a row**
- **Formatting** (no italics, no bold-for-emphasis, no emojis, no hashtags, arrow bullets not dashes/dots)
- **Structure** (opens on scene not "I've been thinking about X"; detail breathes; turn unannounced; landing 1–2 lines, inevitable-in-hindsight)
- **Length / series tag**
- **What Erin is NOT** (not a support function; practitioner not thought leader; not teaching from above; slightly raw not polished; not falsely modest)
- **Voice-exemplar techniques** (numbers speak; verbatim quote; one sensory detail; let someone else land the ending; undercut drama lightly; observe without verdict)
- **Final test** — read it aloud: if any line could be read from a stage, it fails

For each rule give a verdict: ✅ PASS or ❌ FLAG with the exact offending text. Watch especially for AI tells — generic connective phrases ("the part that stuck was why", "what struck me", "the thing is"), over-constructed landings, and tidy symmetry. Default to FLAG when unsure; this is adversarial.

### Step 3 — Revise
Rewrite to fix every flag. State briefly what each fix changed.

### Step 4 — Re-score and repeat
Re-run Step 2 on the revision. If anything still flags, revise again (Step 3) and re-score. **Repeat until a full pass with zero flags.** Cap at 5 rounds; if it still can't pass after 5, stop and report exactly which rule(s) resist and why.

## Output
Show the user, in order: the initial draft, each round's scorecard, each revision, and the final clean version clearly labeled **FINAL — passes clean**. Do not print the final version until it has actually survived a zero-flag re-score.
