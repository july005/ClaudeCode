---
name: usecase-prioritization
description: Use this skill to prioritize across multiple candidate AI use cases and decide which to build first. Trigger when someone has a list or backlog of possible AI applications and asks "where do we start," "which of these is worth building," "how do we prioritize," or hands over several workflows at once. Scores each candidate on impact, frequency, effort, and human-touch sensitivity, then sequences them with adoption as the deciding factor. Do NOT use to diagnose a single workflow; use the workflow-diagnostic skill for that.
---

# Use-Case Prioritization

A backlog of AI ideas is not a plan. Most prioritization fails because it scores use cases on impact alone, builds the highest-impact thing, and then watches nobody use it. This skill scores on four dimensions, not one, and it treats adoption as the factor that decides sequencing, because a high-impact use case nobody adopts returns nothing.

Run this cell by cell. Each candidate gets scored on every dimension before anything is ranked. Do not rank on gut and backfill the scores.

## Before you score

Get the candidate list, and make sure each item is a real workflow, not a category. "Customer support" is a category. "Drafting the first response to an inbound billing question" is a workflow. Push vague items back until they are specific enough to score. You cannot score a category.

If a candidate has not passed the workflow diagnostic, flag it. Prioritizing a use case that is actually an ops problem wastes the whole exercise. This skill assumes the candidates are genuine AI problems.

## The four dimensions

Score each candidate on all four. Use a simple scale (high, medium, low, or 1 to 5) and stay consistent across candidates so the scores are comparable.

Impact. If this worked, how much does it matter? Tie this to a business outcome, not a feeling. Time saved, error reduced, cost avoided, revenue enabled. Vague impact scores high in the room and low in reality.

Frequency. How often does this workflow run? A modest improvement to something that happens fifty times a day beats a large improvement to something that happens twice a quarter. Frequency is where compounding lives.

Effort. What does it cost to build and maintain? Not just the initial build. A skill that needs constant tending has higher true effort than its build time suggests.

Human-touch sensitivity. How much does this workflow depend on human judgment, relationship, or trust, such that automating it would damage something? A use case can score high on the first three and still be wrong to build because it sits on a moment where a person needs to be present. Score this honestly. It is the dimension that protects you from building something technically impressive and organizationally corrosive.

## The keystone: adoption

After scoring, the deciding question is not "which scores highest" but "which will actually get used." Adoption is the keystone metric because every downstream return, efficiency, time saved, cost avoided, flows through it. A use case nobody adopts has an effective impact of zero regardless of its impact score.

So re-read the scores through adoption. High impact plus high frequency plus low human-touch sensitivity plus low effort is the ideal first build, because it is valuable, it recurs, it does not step on a human moment, and it is cheap enough to ship before enthusiasm fades. Frequency and low effort matter more than raw impact for the first build specifically, because the first build's job is to earn adoption and prove the path. Lead with something people will actually pick up.

## Sequencing

Produce an ordered list, not just scores. The sequence logic:

First, the adoption-earning build. High frequency, low effort, low human-touch sensitivity, real impact. Its job is to make the sanctioned path visibly easier than the workaround so shadow tooling starts dying on its own.

Then, the compounding builds. Higher effort or higher impact use cases that are worth it once the path is trusted and adoption is established.

Last or never, the high-sensitivity use cases. Anything that scores high on human-touch sensitivity gets deferred or dropped, and the reason gets stated. Sometimes the right call is to leave a workflow human on purpose.

## Line of sight

For the top few in the sequence, state the line of sight explicitly. Adoption to operational effect to business outcome. If you cannot draw that line for a use case, it does not belong near the top, regardless of its scores. A use case that cannot trace to a business outcome is a demo, not a priority.

## Output

- A table or clear list of every candidate with its four scores.
- The recommended build sequence, ordered, with one line of reasoning each.
- The line of sight for the top two or three.
- Anything deferred or dropped, with the reason, especially high human-touch items.

The measure of a good prioritization is not that it found the highest-impact use case. It is that the first thing built gets adopted, and the adoption makes the next build easier.
