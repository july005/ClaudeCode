# Load-bearing steps

A load-bearing step holds something up. Remove it and something you were not looking at falls down.

These are the steps that make automation projects fail six months in, when the thing that was quietly being caught stops being caught and nobody remembers who was catching it.

Find them before you recommend anything.

## How to find them

Ask what breaks. Not what slows down. What breaks.

If the answer is "nothing, it would just take longer," the step is not load-bearing. If the answer is "well, that's where we'd catch it if the coding was wrong," you have found one.

## Markers

→ **One person does it and nobody else knows how.** The step is a system with a human inside it.
→ **The person cannot fully articulate the rule.** They know it when they see it. That is judgment, and judgment does not survive being written down badly.
→ **The step is where an exception gets caught.** The exception rate is low, which is exactly why the step looks removable.
→ **The step is where a relationship gets maintained.** A call that is nominally about status and actually about trust.
→ **The output is thrown away but the process of making it changed a decision.** The deck nobody read, made by someone who understood the problem while building it.
→ **The step is the only place two functions talk to each other.** Automate it and the two functions stop talking.
→ **Removing it would require someone to be accountable who currently is not.** The step is absorbing accountability nobody has claimed.
→ **The person was there first.** At a startup, load-bearing steps concentrate in whoever arrived earliest. Tenure does not exempt a step from the test. It raises the bar for clearing it. Ask the week-five question and require a specific answer, not a shrug.

## What to do with them

Flag them. Do not recommend touching them in the first pass.

This is not permanent. A load-bearing step can be redesigned. But it has to be redesigned deliberately, with the thing it was holding up made explicit and given somewhere else to go. That is a different project from the one you are scoping, and it is slower.

The failure mode is treating a load-bearing step as an efficiency target because it looks like one from the outside. It always looks like one from the outside. That is what load-bearing means.

## The question to ask the person

"If you were out for a month and nobody did this, what would we find out in week five?"

Week five, not week one. Week one surfaces the obvious. Week five surfaces what the step was actually for.
