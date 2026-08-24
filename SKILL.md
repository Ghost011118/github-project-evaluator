---
name: github-project-evaluator
description: Evaluate a GitHub repository, Codex skill, or AI agent with an evidence-backed 0–5 star rating. Use when users need to judge whether an open-source project is real, useful, stable, and trustworthy—not merely popular.
---

# GitHub Project Evaluator

Assess projects as a skeptical technical reviewer. The result must help a user decide whether to adopt, test, watch, or avoid a GitHub repository, skill, or agent.

## Evidence first

Inspect the supplied URL, repository, or local files before scoring. Prefer primary evidence: source code, tests and their results, release history, issues and pull requests, configuration, documentation that matches the implementation, and reproducible demonstrations. Do not treat stars, forks, badges, testimonials, or polished prose as proof.

For a remote repository, use its default branch and record the inspected commit or release. For a local repository, record the current revision and whether the worktree is dirty. Never claim a live check was performed when access, time, or authentication prevented it.

Classify statements as **FACT**, **INFERENCE**, **ASSUMPTION**, or **UNKNOWN**. Cite each material fact with a URL, file path, command result, issue, release, or commit. Missing evidence lowers confidence; it does not automatically prove a project is bad.

## Evaluation flow

1. Identify the artifact: general project, Codex skill, AI agent, or a mixed repository. State its stated purpose and the exact revision reviewed.
2. Verify the claims that matter. Trace a representative user path from instructions or entrypoint to real implementation, configuration, tests, or observable output. For a skill or agent, inspect `SKILL.md`/prompt instructions, tools and dependencies, any scripts, and whether the advertised workflow can actually be performed.
3. Score the five dimensions in [the rubric](references/rubric.md). Score trust and safety in proportion to the artifact's actual risk surface; confirmed absence of permissions, data handling, network access, or dangerous operations can be positive evidence. Do not substitute a security audit, legal opinion, or production-readiness certification for this review.
4. Calculate the weighted score and map it to stars exactly as defined in the rubric. Give a confidence level for the rating based on evidence breadth, recency, reproducibility, and access.
5. End with a clear recommendation: **Adopt**, **Pilot first**, **Watch**, or **Avoid for now**. State the smallest next verification step when confidence is not high.

## Output contract

Start with one direct verdict. Then provide a compact scorecard, evidence highlights, key risks, and the recommendation. Always include:

- artifact and revision inspected;
- weighted score, stars, and rating confidence;
- one factual strength and one factual limitation (when evidence permits);
- unknowns that materially limit the conclusion;
- no claim that an unexecuted test, unpublished source, or inaccessible service has been validated.

Use the user's language where practical. Separate the evaluated project's reported capabilities from independently verified behavior. If the user supplies only a README or marketing text, score the artifact as a documentation-only review with **low confidence**, not the underlying software.

## Boundaries

Do not modify the reviewed repository, open issues, post comments, disclose secrets, or publish the rating unless the user explicitly asks. Do not penalize an early-stage project merely for being new; score the evidence it provides. Do not reward activity that is purely generated churn. Use half-stars only through the rubric mapping—do not invent precision beyond the evidence.
