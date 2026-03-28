---
name: star-exec-brief
description: Generate a concise project brief in Chinese using the STAR framework from workspace specification documents and the latest code change history. Use when Codex needs to read Spec, PRD, design, requirements, or other project docs plus recent git changes, then explain the project in language that is easy for non-technical readers to understand while preserving clear business value, high-level technical actions, and measurable or decision-relevant outcomes.
---

# Star Exec Brief

## Overview

Read the current workspace, extract the project intent from specification documents and the newest implementation signals, then synthesize a Chinese project brief that is easy for non-technical readers to understand.

Prefer business language over engineering jargon. Stay precise, concise, and evidence-based.

## Gather Source Material

Inspect the workspace before drafting.

Prioritize these sources:

- Spec or design docs such as files or folders containing `spec`, `prd`, `requirement`, `design`, `proposal`, `docs`, or Chinese equivalents.
- The latest code-change evidence such as recent commits, PR patches, changelogs, or the newest modified implementation files.
- Supporting context that helps quantify impact, such as metrics docs, issue notes, benchmarks, release notes, or acceptance criteria.

When a git repository is available, prefer recent commits and diffs over raw file timestamps. Use the latest meaningful change window rather than a single file if the project spans several commits.

When git history is unavailable, fall back to the most recently modified relevant files and explicitly note that limitation in your reasoning.

## Derive The STAR Narrative

Build the document around four sections only:

- `Situation`: Explain the business or technical pain that justified the project. Translate technical symptoms into management-relevant impact such as scale limits, delivery bottlenecks, quality risk, cost, coordination friction, or slow iteration.
- `Task`: State the core project objective in one or two sentences. Focus on the strategic goal, not the implementation backlog.
- `Action`: Summarize the major actions at a coarse grain. Use phrases such as "refactored the layered architecture", "tightened context boundaries", "introduced a new retrieval/ranking approach", or "standardized key workflows and constraints". Skip low-level code details, class names, and file-by-file narration.
- `Result`: Report measurable gains when the sources support them. If the evidence is qualitative only, describe resolved blockers, reduced risk, improved maintainability, or faster delivery in cautious language without inventing numbers.

## Writing Rules

Write for non-technical readers.

- Use Chinese in the final document.
- Keep the tone professional, concise, and business-oriented.
- Lead with impact, not implementation trivia.
- Prefer short paragraphs or short bullets only when they improve scanability.
- Avoid acronyms or code terms unless they are necessary; if used, explain them in plain language.
- Do not fabricate facts, numbers, or outcomes.
- If the sources are incomplete, make conservative inferences and label them as judgment rather than fact.

## Output Shape

Default to this structure:

```markdown
Project brief in Chinese

Situation (include the Chinese label 情景)
<1 short paragraph on the pain point and why it mattered>

Task (include the Chinese label 任务)
<1 short paragraph on the target state or core objective>

Action (include the Chinese label 行动)
- <high-level action 1>
- <high-level action 2>
- <high-level action 3>

Result (include the Chinese label 结果)
<1 short paragraph with quantified gains if supported, otherwise concrete business or delivery outcomes>
```

## Quality Bar

- Ensure each STAR section is materially different; do not repeat the same sentence four ways.
- Ensure `Action` stays high-level and understandable to an executive audience.
- Ensure `Result` answers "so what" for the business, organization, or delivery flow.
- Ensure the final document can be read standalone without the original Spec or commit log.

## Fallback Behavior

If the workspace lacks either specs or code history:

- Use the best available project documents and implementation signals.
- State the missing evidence briefly.
- Still produce the STAR brief, but soften certainty and avoid pseudo-precision.
