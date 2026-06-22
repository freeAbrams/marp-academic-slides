---
marp: true
theme: default
paginate: true
size: 16:9
style: |
  @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400;500;700&family=IBM+Plex+Mono&display=swap');

  :root {
    --color-text: #333333;
    --color-accent: #0097A7;
    --color-accent2: #4285F4;
    --color-green: #02BD35;
    --color-red: #D32F2F;
    --color-purple: #5E35B1;
    --color-orange: #FF8F00;
    --color-bg-light: #F5F5F5;
    --color-bg-code: #F8F9FA;
    --color-line: #D9EAD3;
  }

  section {
    font-family: 'Noto Sans JP', 'Hiragino Sans', 'Hiragino Kaku Gothic ProN', sans-serif;
    color: var(--color-text);
    background: #FFFFFF;
    padding: 36px 60px 72px 60px;
    overflow: hidden;
    font-size: 26px;
  }

  section::after { content: ''; font-size: 0; }
  section p, section ul, section ol { margin: 0.5em 0; }
  section li { margin: 0.15em 0; }

  footer {
    font-family: 'Noto Sans JP', sans-serif;
    color: var(--color-green) !important;
    font-weight: 700;
    font-size: 14px !important;
    left: 40px !important;
    bottom: 20px !important;
    letter-spacing: 1px;
  }

  h1 { color: var(--color-text); font-weight: 700; font-size: 1.68em; margin: 0 0 0.4em 0; border-bottom: none; }
  h2 { color: var(--color-text); font-weight: 700; font-size: 1.22em; margin: 0.5em 0 0.3em 0; border-bottom: 3px solid var(--color-line); padding-bottom: 6px; }
  h3 { color: var(--color-accent); font-weight: 500; font-size: 1.05em; margin: 0.5em 0 0.2em 0; }

  code { font-family: 'IBM Plex Mono', 'Menlo', monospace; background: var(--color-bg-code); padding: 2px 6px; border-radius: 3px; font-size: 0.85em; }
  pre { background: var(--color-bg-code); border-left: 4px solid var(--color-accent); border-radius: 4px; padding: 14px; }
  pre code { background: none; padding: 0; }

  table { font-size: 0.82em; width: 100%; }
  th { background: var(--color-text); color: white; font-weight: 500; }
  tr:nth-child(even) { background: #F0F4FF; }

  blockquote { border-left: 4px solid var(--color-accent); background: var(--color-bg-light); padding: 12px 20px; margin: 12px 0; font-size: 0.95em; }

  section.title { text-align: center; display: flex; flex-direction: column; justify-content: center; border-bottom: 3px solid var(--color-line); }
  section.title h1 { font-size: 2.55em; margin-bottom: 0; }
  section.title h2 { font-size: 1.14em; font-weight: 400; color: var(--color-text); border: none; padding: 0; }
  section.title p { color: #999; font-size: 0.85em; }

  section.section { display: flex; flex-direction: column; justify-content: center; background: linear-gradient(135deg, #FAFAFA 0%, #F0F0F0 100%); }
  section.section h1 { font-size: 2.15em; color: var(--color-accent); text-align: center; }
  section.section p { text-align: center; color: #777; font-size: 1.1em; }

  section.ai-exercise h2 { color: var(--color-purple); border-bottom-color: #D1C4E9; }
  .ai-badge { display: inline-block; background: var(--color-purple); color: white; padding: 2px 12px; border-radius: 4px; font-size: 0.8em; font-weight: 500; margin-right: 8px; }
  .prompt-box { background: var(--color-bg-code); border: 1px solid #DDD; border-left: 4px solid var(--color-purple); border-radius: 4px; padding: 14px 18px; font-family: 'IBM Plex Mono', monospace; font-size: 0.74em; line-height: 1.5; margin: 10px 0; }

  .two-col { display: grid; grid-template-columns: 1fr 1fr; gap: 28px; align-items: start; }
  .three-col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 18px; align-items: stretch; }
  .flow { font-family: 'IBM Plex Mono', 'Menlo', monospace; background: var(--color-bg-code); border-left: 4px solid var(--color-accent); border-radius: 4px; padding: 14px 18px; line-height: 1.55; }
  .note-box { background: var(--color-bg-light); border-left: 4px solid var(--color-accent); border-radius: 4px; padding: 12px 16px; }
  .warn-box { background: #FFF4F4; border-left: 4px solid var(--color-red); border-radius: 4px; padding: 12px 16px; }
  .good-box { background: #F1FBF3; border-left: 4px solid var(--color-green); border-radius: 4px; padding: 12px 16px; }
  .card { border: 1px solid #DDE7EA; border-radius: 6px; padding: 14px 16px; background: #FFFFFF; box-shadow: 0 4px 12px rgba(0,0,0,0.04); }
  .card h3 { margin-top: 0; }
  .big-message { font-size: 1.45em; line-height: 1.45; font-weight: 700; color: var(--color-text); }
  .slide-mini { border: 2px solid #D8E8EA; border-radius: 6px; background: #FFFFFF; padding: 14px 16px; min-height: 245px; box-shadow: 0 8px 20px rgba(0, 151, 167, 0.08); }
  .slide-mini-title { font-size: 1.05em; font-weight: 700; color: var(--color-accent); border-bottom: 2px solid #D8E8EA; padding-bottom: 6px; margin-bottom: 10px; }
  .slide-mini ul { font-size: 0.82em; padding-left: 1.2em; }
  .tag { display: inline-block; background: #E9F4FF; color: var(--color-accent2); border: 1px solid #C9E0FF; border-radius: 4px; padding: 2px 8px; font-size: 0.76em; margin-right: 6px; }

  section.summary h2 { border-bottom-color: var(--color-green); }
  .highlight { background: linear-gradient(transparent 60%, #FFF9C4 60%); font-weight: 500; }
  .red { color: var(--color-red); }
  .blue { color: var(--color-accent2); }
  .teal { color: var(--color-accent); }
  .purple { color: var(--color-purple); }
  .green { color: var(--color-green); }
  .orange { color: var(--color-orange); }
  .small { font-size: 0.82em; }
  .smaller { font-size: 0.72em; }

footer: "COURSE OR EVENT | ORGANIZATION"
---

<!-- _class: title -->

# Deck Title
## Clear subtitle or session label

Presenter | Affiliation  
YYYY-MM-DD

---

## Central message written as a claim

<div class="big-message">
The goal is not to make slides look polished.<br>
The goal is to make a deck the presenter can <span class="highlight">explain and defend</span>.
</div>

<div class="note-box">
Use this supporting box for the source material, scope, or audience expectation.
</div>

---

## Agenda

| Time | Topic |
|---:|---|
| 5 min | Context and objective |
| 10 min | Method or workflow |
| 10 min | Examples and discussion |
| 5 min | Summary and next steps |

---

<!-- _class: section -->

# 1. Section Title

Short phrase that frames the next group of slides

---

## Assertion title that states the slide's point

- Keep each bullet short enough to support speaking
- Put details in oral notes or backup material
- Use concrete nouns, metrics, and sources where available

<div class="note-box">
Use a neutral callout to add one important constraint, reminder, or source note.
</div>

---

## Compare weak and stronger versions side by side

<div class="two-col">
<div class="slide-mini">
<div class="slide-mini-title red">Weak</div>

### Topic label

- Important area
- Many challenges
- Useful method

</div>
<div class="slide-mini">
<div class="slide-mini-title green">Better</div>

### Claim title with concrete meaning

- State the condition or audience
- Name the specific gap
- Show what must change

</div>
</div>

---

## Process slides should show the decision path

<div class="flow">
Collect source material<br>
-> Generate outline<br>
-> Check unsupported claims<br>
-> Draft Marp slides<br>
-> Rehearse and revise
</div>

---

<!-- _class: ai-exercise -->

## <span class="ai-badge">Exercise</span> Turn material into slides

1. Extract background, gap, objective, method, and contribution
2. Create 5-8 assertion-title slides
3. Remove claims that are not in the source
4. Rehearse the first 2-3 slides and record questions

<div class="good-box">
The deliverable is the final PDF deck, not the intermediate draft.
</div>

---

<!-- _class: summary -->

## Summary

- One assertion title per slide makes the story easier to follow
- Short slide text leaves room for oral explanation
- Callout boxes should encode meaning, not decoration
- The final deck must be accurate enough for questions

---

## References

| Topic | Source |
|---|---|
| Presentation design | Add source here |
| Research material | Add source here |

<span class="smaller">
Move long URLs and source details to this slide or to speaker notes.
</span>
