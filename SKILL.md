---
name: marp-academic-slides
description: Create or revise clean academic Marp Markdown slide decks in a restrained research/teaching style. Use when Codex needs to turn an outline, lecture plan, paper abstract, research notes, or existing Markdown into Marp slides; apply a 16:9 white-background academic theme with assertion titles, compact tables, callout boxes, section dividers, prompt boxes, and speaker-friendly slide text.
---

# Marp Academic Slides

## Workflow

1. Clarify the deck purpose, audience, duration, source material, and output format. If the user only provides raw material, first create a slide outline before writing Marp.
2. Use `assets/marp-template.md` as the starting point for new decks. Copy its frontmatter, CSS theme, and representative slide patterns, then replace the sample content.
3. Read `references/style-guide.md` when adjusting the theme, choosing layouts, converting research content into slides, or checking whether a deck matches this style.
4. Keep each slide built around one assertion title. Use body text as speaking support, not a script.
5. Verify the deck manually or by rendering with Marp when available. Fix overflowing text, long URLs, dense bullets, unsupported claims, and repeated generic wording.

## Deck Structure

Prefer this structure for lecture or research decks:

1. Title slide using `_class: title`
2. Central message slide with `.big-message` and one supporting `.note-box`
3. Agenda or expected outcomes
4. Section divider slides using `_class: section`
5. Content slides with assertion titles, compact bullets, tables, or two-column comparisons
6. Exercise or workflow slides using `_class: ai-exercise` when relevant
7. Summary slide using `_class: summary`
8. References or source notes when the deck includes claims, tools, papers, or links

## Content Rules

- Write assertion titles, not topic labels. Prefer "Method X reduces false positives under noisy input" over "Method".
- Keep normal content slides to about 3 bullets or one compact table. Move detail into speaker notes or follow-up material.
- Use tables for comparisons, schedules, criteria, slide plans, and evaluation rubrics.
- Use `.note-box` for neutral guidance, `.good-box` for target state, `.warn-box` for risks, and `.prompt-box` for prompts or exact text users should run.
- Do not invent results, metrics, citations, tool capabilities, or paper details. Mark uncertain items as placeholders for user verification.
- Remove generic AI language such as "innovative", "important role", or "great potential" unless the source material substantiates it.

## Resource Use

- `assets/marp-template.md`: load or copy for a complete reusable Marp theme and representative slide snippets.
- `references/style-guide.md`: load for extracted design DNA, layout patterns, CSS conventions, and QA checks.
