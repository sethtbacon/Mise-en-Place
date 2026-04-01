# Mise en Place

A game-style interactive simulator for [the Bacon Bytes](https://thebaconbytes.com) that teaches strategic alignment for AI agent deployments. Companion piece to the article "AI Perfectly Optimized *Weak*."

## What This Is

An interactive game where players configure AI agents' context, run simulations, and optimize toward strategic alignment — progressing from Individual Contributor to Executive across four levels. Players choose a fictional company (Pilot Light / Proof & Co / Stockpot Group / Broadtable Industries) that sets the difficulty, and their decisions compound across levels in Survival mode.

Hosted on WordPress at thebaconbytes.com/bits/ as a self-contained HTML/JS piece (no backend, no build step required — single-file or small bundle that can be embedded).

## Doc Reading Order

The design docs are in `/docs/` and should be read in this order:

1. **`01-build-plan.md`** — The six agents, their research-backed scenarios, source citations, and the article's core thesis. Start here to understand WHAT the game is about.

2. **`02-game-mechanics.md`** — Level 1–4 mechanics. How each level introduces one new constraint. The mechanic summary table at the bottom is the canonical list of what exists at each level.

3. **`03-mechanics-addendum.md`** — Nine gaps identified in the second design pass. The autonomy slider, hidden debt reveal, meeting breakdown, correction capture, and context swap mechanics. Each references the research source that informed it.

4. **`04-goal-evolution.md`** — How the definition of "winning" changes per level (Hours Saved → Accuracy → Revenue → Compounding). The Intern tutorial. Survival vs. Creative mode. The "So You Retired" endgame with shareable career card.

5. **`05-difficulty-modes.md`** — The four company sizes as difficulty modifiers. Parameter tables for each. How Pilot Light's forgiveness masks founder dependency. How Broadtable Industries' scale makes encoded SCL existential.

6. **`06-cross-doc-review.md`** — **This is the canonical source of truth.** It resolves all inconsistencies between the other docs, finalizes agent names, establishes the mechanic introduction order, corrects timing estimates, and contains the sprint plan. When any other doc conflicts with this one, this one wins.

## Prototype

`/prototype/alignment-gap-simulator.html` is a working Level 1 prototype. It has:
- 6 agents with power toggles
- 3 task context + 5 strategic context layer toggles per agent
- Column header bar with presets (Task Only / Partial SCL / Full Context) and clickable column toggles
- Score bar with live KPIs (Alignment, Retention, Velocity, Debt)
- "Run Simulation" → animated feed of agent decisions
- Results screen with contextual article quotes
- Bacon Bytes branding (Source Serif 4, DM Sans, JetBrains Mono, warm palette)

This prototype is the starting point for Sprint 1. It needs:
- Intern tutorial layer (guided 3-step walkthrough)
- Job offer screen (Pilot Light / Stockpot Group / Broadtable Industries)
- Agent swap: replace Onboarding Assistant with Meeting Summarizer, replace Meeting Consolidator with Task Prioritizer
- Decision volume counter on feed cards
- Title update to "Mise en Place"

## Branding

- **Fonts**: Source Serif 4 (headings, blockquotes, decision text), DM Sans (body, buttons, labels), JetBrains Mono (data values, scores, presets only)
- **Colors**: `--bg: #faf8f5`, `--accent: #c97b2a`, `--green: #1a7a4c`, `--red: #c0392b`, `--blue: #2e6da4`, `--border: #e8e2da`
- **Pattern**: Warm editorial. Cards with 1px borders, 8px radius. Blockquotes with amber left border. No dark mode needed.
- **Reference**: See the published piece at thebaconbytes.com/bits/jevons-paradox/ for the exact visual language.

## Sprint Plan

From `06-cross-doc-review.md`:

**Sprint 1**: Intern tutorial + Level 1 + Job Offer screen + mode selection
**Sprint 2**: Level 2 (sub-phases 2a/2b/2c) + Survival state inheritance
**Sprint 3**: Levels 3 + 4 + "So You Retired" endgame + share card
**Sprint 4**: Creative mode + difficulty parameter tuning + research tooltips

## Deployment

Final output goes in `/public/`. Must work as a standalone HTML file (or small bundle with inlined CSS/JS) embeddable in a WordPress page via iframe or direct include. No server-side dependencies. No build toolchain required for the final artifact — though using one during development is fine.
