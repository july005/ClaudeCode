# A working operating system for an independent AI enablement practice

This repo runs a consulting practice. It is not a portfolio of finished work and it is not a set of demos. It is the actual infrastructure: the skills that do the work, the frameworks that decide what work is worth doing, and the governance that keeps the whole thing from drifting.

The organizing idea is simple to state and hard to do. Every skill here earned its place by passing a diagnostic. Nothing is here because it was possible to build. Things are here because a specific workflow got examined and judged worth rebuilding. The restraint is the design.

## Why so few skills, on purpose

The scarce skill in this work is not production. Models collapsed production. The scarce skill is naming the right problem in a room full of people circling it, and knowing which workflows are worth touching before anyone builds anything.

So this system was built the way I would build one for a client. I ran the diagnostic on my own workflows first.

The fork: is this an ops problem or an AI problem. Does a process exist, is it followed, and if not, why not. Four failure modes decide it: no owner, wrong incentives, tools that do not match the workflow, people who do not know the thing exists. An AI skill stacked on a broken process fails the same way, faster. Only after the process holds does the AI question open, and it splits again. Acceleration is the same work faster, and it has a ceiling. Rebuild is when the work itself changes. I built skills for the rebuilds.

That is the whole logic. A skill in this repo means a workflow passed that test.

## What runs the practice

A few principles govern everything here.

Adoption is the keystone metric. A skill nobody uses returns nothing, so every skill is built to make the sanctioned path cheaper than the workaround.

Enablement is the human layer of governance. The job is not a technical perimeter. The job is making the approved path so easy that shadow tooling dies on its own.

Possession comes from infrastructure, not from claim. You own a capability because you built and versioned it, not because you said you had it. This repo is that principle applied to my own practice.

## How it is structured

Three layers, like an operating system.

→ Kernel. CLAUDE.md and this README. The logic that makes the rest a system instead of a folder. Live.

→ Applications. The skills, grouped by function under skills/.
- Content. The erin-voice skill and its exemplars. Live.
- Diagnostics. Two runnable skills: one that forks a workflow into ops versus AI and augment versus rebuild, and one that scores a backlog on impact, frequency, effort, and human-touch, then sequences it with adoption as the deciding factor. Frameworks you run, not frameworks that sit on a slide. Live.
- Operations. Client intake, proposal drafting, and clean-room research briefs I own outright. Roadmap.

The folders group these for a human reading the repo. Which skill fires is decided by each skill's own description, not its folder, so the same skills flatten cleanly when they deploy to a live environment.

→ Shell. Slash commands so the skills are one keystroke, a .gitignore so nothing leaks, and a review discipline where changes move through inspected diffs. Partially live.

## What is not here

Anything built during a prior engagement stays out. Design systems, brand assets, internal research, client work. That material belongs to the engagement that paid for it, and leaving does not change that. What you see here is built on material I own outright. What you do not see is the reason it is not here.

That boundary is not a limitation of the repo. It is the same judgment the work itself requires. The job is knowing where the line sits, and a public repo that respects it is the proof.

## How to read it

The commits matter more than any single file. This is real iteration over time. Clone it, read the log, watch the skills get built and revised, and read CLAUDE.md to see the rules any agent follows when it works in here. The system is the artifact. The individual files are just where it lives.
