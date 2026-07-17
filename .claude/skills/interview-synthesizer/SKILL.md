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

### 0. Establish the outcome

Before mapping anything, ask what this workflow is supposed to produce and how anyone would know it worked. Record the answer as the stated outcome.

Then treat that answer as a hypothesis, not a fact. The person inside a workflow optimizes their local pain, which is the correct thing for them to do and the wrong thing to design from. The actual outcome lives with whoever owns the money the workflow spends, or with the structural commitment it serves: a contract, a regulatory requirement, the revenue motion.

→ What a workflow is attached to is what it is for. Trace it to the contract, the regulatory requirement, or the revenue motion it serves. If it is attached to nothing structural, ask whether it should exist at all.
→ Ask who owns that. Ask when they last said what good looks like.
→ If the stated outcome is about speed, effort, or the person's own frustration, it is almost certainly local. Name what it might be serving instead.
→ If nobody can say who decided the outcome, that is the finding. Report it before you report anything else.

Do not stop the diagnostic when the outcome is unclear. Map the workflow anyway. An unclear outcome is a result, not a blocker.

### 1. Extract the sequence

List every step the person describes, in order, as they described it. Do not clean it up. Do not merge steps. Do not infer steps they did not mention.

For each step capture:
→ Who does it
→ What triggers it
→ What it produces
→ Where the output goes next

Name the supplier. For each step, ask where the input comes from and who controls its quality. The supplier is often outside the workflow and outside the org, and the interviewee usually cannot change it, which is why they have stopped mentioning it.

→ If a step exists to compensate for poor input quality, the step is not the problem. Say so, and name the supplier.
→ If the interviewee chose the supplier, ask why, and listen for a defense. A defended supplier is a decision nobody has revisited.
→ Bad input manifests downstream as steps that look automatable. They are compensating, and automating them makes the bad input permanent.

Record supplier quality as a finding, not a step verdict. A supplier is not something you fork.

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

Every step gets tested against the outcome before it gets forked. If a step does not serve the outcome, the verdict is delete, regardless of whether it looks like a clean AI candidate. A step can be perfectly automatable and still be in service of nothing.

Every workflow failure is one of three things: a broken process, a task the tech should absorb, or a missing alignment. Name which before you fork.

Every step that is not load-bearing gets one of six verdicts:

→ **Ops problem.** The step exists because a process is broken. Automating it makes the broken process faster and harder to fix. Name what would have to change upstream.
→ **AI problem.** The step is work no human needed to own. Information is stuck, or the same judgment is being reapplied to inputs that do not vary. This is where AI absorbs the work.
→ **Delete.** The step does not serve the outcome. It may produce nothing anybody uses, or it may produce something several people consume that changes no decision anyone owns. Say who you would have to ask to confirm this.
→ **Leave it.** It works. Not everything is a problem.
→ **Alignment problem (orphaned).** The process works and the tech is not the issue. What is missing is a person or an agreement: nobody owns the decision, or the people who share it have never aligned on it. Do not automate it and do not absorb it. The deliverable is the escalation: name who must own it and who decides that. Automating around an alignment gap hard-codes the disagreement.
→ **Ops first, then AI.** The step contains a real AI slice that only becomes available once an upstream ops fix lands. Name the ops fix, name what the AI absorbs afterward, and say plainly that building the second before the first produces a tool that depends on the broken thing. Do not sequence the AI work until the ops fix is owned.

### 5. Sequence

Of the AI problems, apply Impact, Frequency, Effort. Rank them.

Report the top three and say what you would do first. Say what you would not do, and why.

## Output format

```
WORKFLOW: [name]
SOURCE: [who was interviewed, when]

STATED OUTCOME
[what the interviewee says the workflow is for]

OUTCOME I WOULD CHECK
[what it may actually be for, who would know, and what would change if the second is right]

SEQUENCE
1. [step] → [owner] → [output]
...

SEAMS
→ [step N to step N+1]: [what is lost]
...

SUPPLIERS
→ [input]: [who controls its quality] [what it costs downstream when poor] [whether the interviewee chose them and how they defend it]
...

LOAD-BEARING
→ [step]: [what breaks if this goes away]
...

DIAGNOSTIC
| Step | Verdict | Why |

Steps flagged load-bearing appear in the LOAD-BEARING section and are excluded from
the DIAGNOSTIC table. They are not forked.

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
