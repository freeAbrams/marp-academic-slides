# Academic Marp Style Guide

## Design DNA

This style is a calm academic teaching/research deck. It should feel precise, readable, and easy to edit in Markdown, not like a marketing deck.

Core traits:

- White slide background with restrained gray surfaces.
- Dark neutral body text and a small set of semantic accents.
- Strong information hierarchy through assertion titles, section dividers, callout boxes, and tables.
- Compact but readable density: enough content for a class or research talk, without full paragraphs.
- CSS utility classes that make repeated slide patterns fast to compose.

## Theme Tokens

Use these colors unless the user provides a brand system:

| Token | Hex | Role |
|---|---:|---|
| `--color-text` | `#333333` | Main text and headings |
| `--color-accent` | `#0097A7` | Primary teal accent |
| `--color-accent2` | `#4285F4` | Secondary blue tags |
| `--color-green` | `#02BD35` | Positive status and footer |
| `--color-red` | `#D32F2F` | Warnings and weak examples |
| `--color-purple` | `#5E35B1` | Exercise or AI-specific sections |
| `--color-orange` | `#FF8F00` | Optional emphasis |
| `--color-bg-light` | `#F5F5F5` | Neutral callout background |
| `--color-bg-code` | `#F8F9FA` | Prompt and code background |
| `--color-line` | `#D9EAD3` | Soft divider line |

Typography:

- Use `Noto Sans JP` first, then local Japanese sans-serif fallbacks, then generic sans-serif.
- Use `IBM Plex Mono` for prompts, code, and flow diagrams.
- Use a base slide font size around `26px` for 16:9 Marp.
- Keep headings bold, compact, and free of decorative effects.

## Layout System

Base slide:

- `size: 16:9`
- `paginate: true`
- Section padding around `36px 60px 72px 60px`
- Footer at bottom-left, small, green, bold
- Hide Marp's default page counter pseudo-element with `section::after { content: ''; font-size: 0; }`

Slide classes:

- `title`: centered title slide with large H1, subtitle, date/author lines, and a thin bottom border.
- `section`: centered chapter divider with light gray gradient and teal section title.
- `ai-exercise`: normal content slide whose H2 and badges use purple.
- `summary`: final summary slide with green H2 divider.

Utility classes:

- `.two-col`: two equal columns with a 28px gap.
- `.three-col`: three equal columns for cards or compact comparisons.
- `.flow`: monospaced process flow with arrows or line breaks.
- `.note-box`: neutral callout with teal border.
- `.warn-box`: risk callout with red border.
- `.good-box`: target-state callout with green border.
- `.prompt-box`: monospaced prompt text; use for exact AI prompts or commands.
- `.card`: light bordered card for repeated items only.
- `.slide-mini`: mini slide mockup used for weak/good comparisons.
- `.tag`: small blue label for metadata or categories.
- `.highlight`: text highlight using a yellow underline effect.
- `.small` and `.smaller`: compact source notes or disclaimers.

## Writing Patterns

Assertion title pattern:

```markdown
## Sensor changes make static safety explanations hard to maintain

- Operating conditions change after deployment
- Static evidence becomes stale
- The system needs an update path for assurance
```

Weak/good comparison:

```markdown
<div class="two-col">
<div class="slide-mini">
<div class="slide-mini-title red">Weak</div>

### Background

- Autonomous driving is important
- Safety is necessary
- There are challenges

</div>
<div class="slide-mini">
<div class="slide-mini-title green">Better</div>

### Operational changes make safety arguments stale

- Sensors and environments change
- Design-time evidence can stop matching reality
- Updates need to be explainable

</div>
</div>
```

Prompt box:

```markdown
<div class="prompt-box">
Create a 5-minute, 6-slide research talk from the abstract below.<br>
Use assertion titles, no unsupported metrics, and at most 3 bullets per slide.<br><br>
[paste abstract]
</div>
```

Flow:

```markdown
<div class="flow">
Collect source material<br>
-> Generate outline<br>
-> Check facts<br>
-> Write Marp draft<br>
-> Rehearse and revise
</div>
```

## Research Deck Method

When converting an abstract, paper, or research notes:

1. Extract background, gap, objective, method, result or expected evaluation, contribution, and limitations.
2. Map those elements to 5-8 slides for a short talk or 10-14 slides for a 10-minute talk.
3. Turn every slide title into a claim the presenter can defend.
4. Use the paper body for concrete method details, experiment conditions, figures, metrics, and sources.
5. Do not add results, citations, diagrams, or interpretations absent from the source.
6. Create speaker notes or oral supplement bullets for details that do not fit on the slide.
7. Add likely audience questions and revise slides where the presenter cannot answer.

## QA Checklist

Before delivering:

- Each slide has one main message.
- Titles form a readable story when skimmed in order.
- Body text is short enough to fit at the base font size.
- Tables are compact and have clear columns.
- Long URLs are moved to small source notes or references slides.
- Callout colors match meaning: teal neutral, green target, red risk, purple exercise/AI.
- No generated claims appear without source support.
- Marp frontmatter remains valid YAML and CSS braces are balanced.
