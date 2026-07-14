---
name: workflow-diagnostic
description: Use this skill to diagnose whether a slow or painful workflow is an operations problem or an AI problem, and if AI, whether it calls for acceleration or rebuild. Trigger when someone describes a workflow that is slow, painful, or a candidate for automation, or asks "should we build AI for this," "can we automate this," or "why is this so slow." Produces a structured verdict with reasoning and a recommended next action. Do NOT use for prioritizing across many use cases at once; use the usecase-prioritization skill for that.
---

# Workflow Diagnostic

The most common mistake in AI enablement is answering the wrong question. Someone says a workflow is slow, and the reflex is to build AI for it. In a fast-growing organization everything is slow, so "slow" is not a signal. The real question is what is actually constraining growth, and whether the constraint is even the kind of thing AI touches.

This skill runs the fork. Do not skip steps. The value is in refusing to reach for AI before the earlier questions are answered.

## What you need before you start

A described workflow. Who does it, what triggers it, what the steps are, what the output is, and why someone thinks it needs attention. If any of that is missing, ask for it before diagnosing. A diagnosis on a vague workflow is guessing.

## Step zero: audit the constraint

Before diagnosing the workflow, confirm the workflow is the thing worth diagnosing. This is the step everyone skips, and skipping it is how a rigorous process ships the wrong thing.

Ask: what outcome is this workflow supposed to move, and is this workflow actually the binding constraint on that outcome? Not a constraint. The binding one.

The failure looks like this. Say content is not landing, and the diagnosis is that it gets written too slowly. So every AI tool gets scored on how much faster it makes the writing, the best one wins, and now drafts take half the time. Flawless. Except writing speed was never the problem. The content was not landing because the topics were wrong, or the pieces were too long. The one thing that was already working got faster, and the thing that was actually stuck never got touched.

That is the trap. You can rank an initiative perfectly against the wrong binding constraint and ship the wrong thing, on time and fully justified. Good prioritization scores constraint-fit. It rarely audits the constraint itself. The upstream call of which constraint is actually holding the outcome back is the one that decides whether any of the downstream rigor matters.

So before the fork:
- Name the outcome the workflow is meant to serve.
- Name what is actually holding that outcome back. If it is not this workflow, stop and point at the real constraint. Diagnosing this one will produce a correct answer to a question that does not matter.
- Ask constrained toward what. Efficiency, agility, and long-term position are different targets, and a workflow can be the binding constraint on one and irrelevant to another. Say which target you are optimizing for.

Only once the workflow survives this gate does the ops/AI fork below apply.

One caution to carry forward: constraints shift over time. The binding constraint today may not be the binding constraint next quarter, and usually nobody is assigned to watch for the shift. If this diagnosis is going to inform an ongoing build, name who re-checks the constraint and when.

## The first fork: ops problem or AI problem

Before anything else, determine which kind of problem this is. They look identical from the outside and have completely different fixes.

Ask: if this workflow ran on well-designed software with no AI at all, would it be fine?

If yes, this is an ops problem. Go to the ops branch. Do not build AI. AI layered on a broken process inherits the break and runs it faster.

If no, and the work genuinely requires judgment, synthesis, language, or pattern-matching that ordinary software cannot do, this is an AI problem. Go to the AI branch.

If unsure, treat it as an ops problem first. Ops problems are cheaper to rule out, and most "AI problems" are ops problems wearing a costume.

## Ops branch

Walk these in order. Stop at the first one that answers.

1. Does a process exist at all? If no, the fix is to design one. AI is premature.

2. If a process exists, is it followed? If it is followed and still painful, the process itself is wrong. Redesign the process. If it is not followed, go to question 3.

3. Why is the process not followed? There are four failure modes. Name which one.
   - No owner. Nobody is accountable for the process, so it decays.
   - Wrong incentives. Following the process costs the individual more than ignoring it.
   - Tools do not match the workflow. The process assumes a tool or step that does not fit how the work actually happens.
   - People do not know it exists. A discovery and communication problem, not a process problem.

Each failure mode has a different fix, and none of them is "build AI." State the failure mode and the corresponding fix, and stop. If the org insists on AI here, note that it will fail the same way the process fails, only faster.

## AI branch

This is a real AI problem. Now split again, because the two branches lead to different kinds of work with different ceilings.

Acceleration. The same steps, done faster. The work itself does not change. A human still owns the workflow start to finish, AI just speeds the parts up. This has real value and a hard ceiling. You are optimizing an existing shape, not changing it.

Rebuild. The work itself changes. Ask: if AI could do part of this, would the division of labor change? Would a human stop owning something they only owned because someone had to? Rebuild means AI absorbs the work no human needed to own, and people are freed to do the work only they can do. Rebuild contains acceleration as an ingredient, but it does not stop there. It changes how the whole thing scales.

To tell them apart, ask the scaling question: if headcount doubled, does this workflow get twice as heavy? Acceleration makes each instance faster but the load still scales with volume. Rebuild changes who does the work, so the load stops scaling the same way. If the honest answer is that the work still scales linearly with volume, you have an acceleration, not a rebuild. Say so.

## Output

Produce a short structured verdict:

- Classification: ops problem or AI problem. If AI, acceleration or rebuild.
- The reasoning, in two or three sentences, naming the specific fork answers that got you there.
- The recommended next action, concrete. For ops problems, the failure mode and its fix. For accelerations, what to speed up and where the ceiling is. For rebuilds, what division of labor changes and why that changes scaling.
- One caution: the way this diagnosis could be wrong, and what to check to confirm it.

Do not inflate an acceleration into a rebuild to make it sound more impressive. The discipline of calling an acceleration an acceleration is the whole point of the skill.
