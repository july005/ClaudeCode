# Fork criteria: ops problem or AI problem

Every step that survives the load-bearing filter gets tested against the outcome, and only then forked. The fork is the whole point of the diagnostic. Getting it wrong is the most expensive mistake in AI enablement, because an AI intervention on an ops problem produces a faster broken process and a constituency invested in keeping it.

## Before the test: does the step serve the outcome

Run this first. It overrides the fork.

A step that does not serve the outcome is a delete, even when it has every marker of a clean AI problem. Automating it produces a faster route to something nobody wanted.

The failure is easy to miss because the local logic holds. Each step is a reasonable response to the step before it. The sequence is internally coherent and pointed at the wrong thing.

Signals that a step serves a local outcome rather than the real one:
→ The step reduces the interviewee's effort and changes nothing downstream
→ Removing the step would embarrass someone but cost nothing
→ The step exists to make a decision faster, and the decision is one that should be made less often rather than faster
→ The person describes the benefit in terms of their own time

That last one is the most common and the most expensive. Faster is not an outcome. It is a property of an outcome, and it is worth nothing when it is attached to the wrong one.

## The test

Ask: if this step ran instantly and perfectly, would the outcome change?

If yes, it is an AI problem. The step is a bottleneck and the bottleneck is throughput.

If no, it is an ops problem. The step is a symptom. Something upstream is generating the need for it, and speeding it up leaves the generator intact.

## Signals of an ops problem

→ The step exists to compensate for something someone else did not do
→ The step is a check on a prior step's output, and the check usually finds errors
→ The person describes waiting, chasing, or following up
→ The person describes frustration with another team or person, not with a system
→ Removing the step would be fine if a policy changed
→ The step reconciles two systems that should be one system
→ The output is a document that exists to prove work happened
→ Multiple people do the same step differently and nobody has decided which is right

The recurring shape: an ops problem is work created by an absent decision. Somebody did not decide something, and the step exists to absorb the ambiguity.

## Signals of an AI problem

→ Information exists but is not where it needs to be
→ The same judgment gets reapplied to inputs that do not meaningfully vary
→ The step is translation: same content, different format, different audience
→ The step is retrieval: the answer exists in a document nobody has time to read
→ The step is synthesis of sources that are all available and all trusted
→ The person can articulate the rule they follow, and the rule holds
→ Volume is the constraint, not correctness
→ Nobody would object if this were done by a machine, because nobody wanted to own it

The recurring shape: an AI problem is work that no human needed to own. It requires no judgment that has not already been made, and it is only being done by a person because there was nobody else to do it.

## The hard cases

**A step that is both.** Common. The rule is: fix the ops problem first, then reassess. If you build the AI intervention first, the ops problem becomes permanent, because now there is a tool that depends on it.

**A step where the rule exists but nobody follows it.** Ops problem. Compliance is not a retrieval failure.

**A step that is slow because the person is overloaded.** Look at what else they own. Frequently the answer is that the work is misallocated, not that this particular step needs a tool.

**A step nobody complains about.** Usually leave it. Volunteered pain is the most reliable signal you have. A step that nobody mentioned as painful is a step where the diagnostic has no data.

**A step the person is proud of.** Slow down. Pride is often a marker of a load-bearing step. Go back to the load-bearing filter.

**An ops problem with no owner.** The startup default. The verdict is orphaned, not ops problem, because an ops problem implies someone can fix it. Do not let the absence of an owner convert the step into your step. The finding is the absence. Escalate it as one.

## What to write

For each step, one line of verdict and one line of reason. The reason must reference something the person actually said. If you cannot cite the transcript, you are inferring, and inference is what puts the wrong verdict on the wrong step.
