---
name: interview-synthesizer
description: Use this skill when analyzing a stakeholder discovery interview, workflow walkthrough, or process transcript to produce a workflow map and determine whether the problems surfaced are ops problems or AI problems. Triggers on requests like "synthesize this discovery call," "map this workflow," "what should we automate here," "run the diagnostic on this," or when a transcript of someone describing how their work gets done is provided. Do NOT use for general meeting notes, hiring interviews, or user research on a product.
---

# Interview Synthesizer

Turn a raw discovery transcript into a workflow map with a diagnostic verdict on each step.

The output is not a list of automation opportunities. Most steps in most workflows should not be touched. The job is to find the few that should, and to say clearly which of those are AI problems and which are ops problems that AI would only entrench.

## Inputs

A transcript, notes, or recording summary of someone describing how a piece of work actually gets done. Fidelity matters more than polish. Raw is fine.

If the input is a job description, a process document, or an org chart rather than someone describing their own work, stop and say so. Those describe how work is supposed to happen. This skill operates on how it does happen.

## Process

### 0. Check what the process is attached to

Before mapping, ask what this process exists to serve.

→ Attached to something structural (a contract, a regulatory requirement, the core revenue motion): the current form will change, the process will not. Full depth.
→ Attached to a workaround, a single customer, or one person's preference: it may not survive the quarter. Sequence and seams only.

Age is not the discriminator. New processes bolted to structural commitments outlive their current shape. Old processes bolted to nothing disappear the week the person who ran them leaves.

### 1. Extract the sequence

List every step the person describes, in order, as they described it. Do not clean it up. Do not merge steps. Do not infer steps they did not mention.

For each step capture:
→ Who does it
→ What triggers it
→ What it produces
→ Where the output goes next

### 2. Mark the seams

A seam is any point where work changes hands, changes systems, or waits.

Seams are where the cost lives. They are also invisible to the person inside the workflow, because from inside, a handoff feels like the end of your part rather than the middle of the process.

Mark every seam explicitly. Note what is lost at each one: context, time, fidelity, accountability.

### 3. Identify load-bearing steps

Read `references/load-bearing.md`.

A load-bearing step is one where removing it breaks something downstream that nobody would predict. These are the steps where the judgment lives, or where an undocumented check happens, or where one person's knowledge is silently doing the work of a system.

Load-bearing steps are the ones people most want to automate and the ones most likely to fail when automated. Flag them and do not recommend touching them in the first pass.

### 4. Fork each remaining step

Read `references/fork-criteria.md`.

Every step that is not load-bearing gets one of five verdicts:

→ **Ops problem.** The step exists because a process is broken. Automating it makes the broken process faster and harder to fix. Name what would have to change upstream.
→ **AI problem.** The step is work no human needed to own. Information is stuck, or the same judgment is being reapplied to inputs that do not vary. This is where AI absorbs the work.
→ **Delete.** The step produces something nobody uses. Say who you would have to ask to confirm this.
→ **Leave it.** It works. Not everything is a problem.
→ **Orphaned.** The step is an ops problem and nobody owns the process it belongs to. Do not automate it and do not absorb it. The deliverable is the escalation: name the missing owner and who decides that.

### 5. Sequence

Of the AI problems, apply Impact, Frequency, Effort. Rank them.

Report the top three and say what you would do first. Say what you would not do, and why.

## Output format

```
WORKFLOW: [name]
SOURCE: [who was interviewed, when]

SEQUENCE
1. [step] → [owner] → [output]
...

SEAMS
→ [step N to step N+1]: [what is lost]
...

LOAD-BEARING
→ [step]: [what breaks if this goes away]
...

DIAGNOSTIC
| Step | Verdict | Why |

WHAT I WOULD DO FIRST
[one paragraph]

WHAT I WOULD NOT TOUCH
[one paragraph]

WHAT I STILL NEED TO KNOW
[the questions the transcript did not answer]
```

## Rules

Do not invent steps the transcript does not contain. If the sequence has a gap, name the gap and put it under WHAT I STILL NEED TO KNOW.

Do not recommend an AI intervention for a step where the person described frustration with another person. That is an ops problem wearing a costume.

Do not produce more than three recommendations. A list of twelve is a way of avoiding the decision.

If the whole workflow is an ops problem, say that. The correct output is sometimes that there is nothing here to build.

If the fork says ops problem and there is no ops function, the fix is capped at minimum viable: standardize the input, write the one-page SOP, name an owner out loud. Then leave. Clearing the runway is in scope. Paving it is not.
