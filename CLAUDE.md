# CLAUDE.md

Operating instructions for any agent working in this repository.

This repo is the working infrastructure for an independent AI enablement and operations practice. It is not a demo and not a portfolio of finished artifacts. It is the live system that runs the practice: the skills, the frameworks encoded as skills, and the governance around them. Treat it that way. When you work here, you are maintaining an operating system, not decorating a folder.

## How this system is organized

Every skill in this repo earned its place by passing a diagnostic. Skills are not added because they are possible. They are added because a specific workflow was examined and judged worth rebuilding. That selection logic is the point of the system. Preserve it. When asked to add something, first ask whether it passes the diagnostic below. If it does not, say so.

## The diagnostic that governs what gets built

Before building or accelerating any workflow, run the fork.

First fork: is this an ops problem or an AI problem. They are not the same.

Ops path. Does a process exist. Is it followed. If not, why not. Four failure modes: no owner, wrong incentives, tools do not match the workflow, people do not know it exists. An AI skill built on top of a process that fails for one of these reasons will fail the same way, faster. Fix the process first.

AI path. Two branches. Acceleration means the same work done faster, and it has a ceiling. Rebuild means the work itself changes, which changes how the practice scales. Build skills for rebuilds. Note accelerations, but do not mistake them for transformation.

## The frameworks that run the practice

These are the operating principles. They apply to the practice itself and to any client engagement the practice takes on.

Adoption is the keystone metric. A skill nobody uses returns nothing. Every skill here is built to lower the cost of the approved path until it is easier than the workaround. The measure of a skill is not its cleverness. It is whether it gets used.

Enablement is the human layer of governance. The job is not to build a technical perimeter. The job is to make the sanctioned path so easy that shadow tooling dies on its own. Design for that.

The line of sight has to be real. Adoption to operational savings to margin. A skill that cannot trace to a business outcome is a hobby. State the line of sight when you build.

Possession is established through infrastructure, not through claim. Ownership of a capability comes from what is built and versioned, not from what is asserted. This repo is the proof of that principle applied to the practice itself.

## How to work in this repo

Read before writing. When editing a skill, read its SKILL.md and any supporting files first. When editing content, read the erin-voice skill first.

Voice is governed by the erin-voice skill. All written content produced as Erin follows that skill's SKILL.md and voice-exemplars.md. Do not override those rules. If you draft content and it violates them, fix it before showing it.

Never leak. This repo is public. Before committing anything, scan for credentials, tokens, client data, or material owned by a prior engagement. Anything from a prior employer or client engagement stays out, regardless of who built it. When in doubt, flag it and stop.

Changes move through review. Skills and their tests live together. When you change a skill, expect the change to be inspected as a diff before it is trusted. Write changes that read clearly in a diff.

## Repository structure

The system has three layers.

Kernel. This file and the top-level README. The organizing logic that makes the rest a system.

Applications. The skills, grouped by function under skills/.
- skills/content. Voice and content. The erin-voice skill and its exemplars. Live.
- skills/diagnostics. The workflow-diagnostic skill (the ops-vs-AI fork) and the usecase-prioritization skill (the IFE model), both runnable. Live.
- skills/operations. Practice operations. Intake, proposal drafting, clean-room research briefs owned outright. Roadmap.

The folders group skills for human readers. Triggering is governed by each skill's description field, not its folder. When these deploy to a live .claude/skills/ directory they flatten; the grouping is a property of this source repo only.

Shell. Slash commands, .gitignore, and the review discipline that governs the system. Partially live.

When a roadmap item gets built, move it to live in both this file and the README, and update the structure map so the two never drift.
