# MBB Consultant Distiller

A WorkBuddy skill that transforms raw materials into McKinsey-style structured reports. Think of it as a senior consultant sitting next to you — feed it messy notes, and it outputs boardroom-ready deliverables.

## When to Use

| Scenario | What You Have | What You Get |
|----------|--------------|--------------|
| Meeting notes → Report | Scattered notes from client meetings | Structured analysis with key insights |
| Research dump → Insight brief | 10+ articles, data points, interview transcripts | Executive summary + framework-driven analysis |
| Industry deep-dive from scratch | Just a topic ("analyze China's EV market") | Full report with real data from web research |
| Internal memo → Client-facing deck outline | Rough internal write-up | PPT storyline with conclusion-driven slide titles |
| Data → Narrative | Raw numbers and charts | McKinsey-style "so what" interpretation |

### Typical Users

- Strategy/consulting teams preparing client deliverables
- Product managers writing industry analysis for leadership
- Investors summarizing due diligence materials
- Anyone who thinks in bullet points but needs to present in paragraphs

## How It Works: The Distillation Process

```
                    ┌─────────────────────────────┐
                    │       RAW MATERIALS          │
                    │  notes / articles / data /   │
                    │  transcripts / random docs   │
                    └──────────────┬──────────────┘
                                   │
                    ┌──────────────▼──────────────┐
                    │   1. SMART TRIAGE            │
                    │   Auto-detect input volume:  │
                    │   >500 chars → just write    │
                    │   <200 chars → clarify first │
                    │   Topic only → guided mode   │
                    └──────────────┬──────────────┘
                                   │
                    ┌──────────────▼──────────────┐
                    │   2. FRAMEWORK MATCHING      │
                    │   Auto-select from:          │
                    │   • Porter's Five Forces     │
                    │   • Market sizing            │
                    │   • Market entry             │
                    │   • Turn-around strategy     │
                    │   • TMT/new-tech analysis    │
                    │   • Comprehensive industry   │
                    └──────────────┬──────────────┘
                                   │
                    ┌──────────────▼──────────────┐
                    │   3. HYPOTHESIS-DRIVEN       │
                    │      WRITING                 │
                    │   Conclusion first →         │
                    │   Support with data →        │
                    │   MECE structure             │
                    └──────────────┬──────────────┘
                                   │
                    ┌──────────────▼──────────────┐
                    │   4. OUTPUT + SELF-CHECK     │
                    │   Structured report +        │
                    │   Optional PPT storyline +   │
                    │   Automated quality audit    │
                    └─────────────────────────────┘
```

### The Core Idea

Most people write reports **bottom-up**: gather everything, then struggle to find a narrative.

This skill works **top-down** (the McKinsey way):

1. **Start with the answer** — form a hypothesis about what the conclusion should be
2. **Structure the argument** — use MECE frameworks to organize supporting evidence
3. **Fill with data** — each section gets exactly the data it needs, nothing more
4. **Validate or pivot** — if data contradicts the hypothesis, flip the narrative

This is why a 2-page output from this skill often communicates more than a 20-page unfocused report.

## Core Highlights

### Two Modes of Operation

| | Mode A: Distill | Mode B: Generate |
|---|---|---|
| Input | Your raw materials (docs, notes, data) | Just a topic or question |
| Process | Restructure + enhance | Research + synthesize from scratch |
| Data source | Your materials | Web search (3-8 queries) |
| Turns to complete | 1 conversation turn | 2-3 turns (clarify → skeleton → full report) |

### Smart Clarification Engine

The skill doesn't waste your time with unnecessary questions:

- **Plenty of input (>500 chars)** → writes immediately, no questions asked
- **Some input (200-500 chars)** → asks exactly 1 clarifying question
- **Minimal input (<200 chars)** → asks 2-3 questions in one batch
- **Topic only** → guided mode with skeleton confirmation

Anti-patterns it explicitly avoids: serial questioning, asking when it already has enough, confirmation-seeking ("are you sure?"), treating you like a survey respondent.

### Framework Auto-Matching

Instead of you choosing a framework, it decides based on your focus:

```
"How big is this market?"     → Penetration decomposition + category sizing
"Who are the competitors?"    → Porter's Five Forces + competitor matrix
"Should we enter?"            → Market entry framework (external + internal)
"How to turn this around?"    → Turn-around strategy framework
"New tech opportunity?"       → Scenario → Scale → Value chain → Business model
"Give me the full picture"    → Comprehensive: Macro → Competition → KSF → Recommendations
```

### McKinsey Writing DNA

Every output follows these non-negotiable rules:

| Rule | What It Means |
|------|---------------|
| Conclusion first | First sentence of every section IS the takeaway |
| Data talks | "grew 14%" not "grew significantly" |
| Concise sentences | 15-25 characters per sentence |
| Active voice | "We found" not "It was found" |
| Titles = conclusions | "Consumer confidence stabilized" not "Trend analysis" |
| MECE structure | Mutually exclusive, collectively exhaustive |

### Graceful Degradation

When data isn't available, it doesn't halt — it degrades gracefully:

| Situation | Behavior |
|-----------|----------|
| Exact data found | Cite with source |
| Similar data found | Use with noted differences |
| No data at all | Logic-based inference, marked `[to be supplemented]` |
| Outdated data (>2yr) | Use with year noted, suggest refresh |

## File Structure

```
mbb-consultant-distiller/
├── SKILL.md                    # Core skill instructions (534 lines)
├── _skillhub_meta.json         # Metadata (version, slug)
├── references/
│   └── frameworks.md           # Analysis framework library
└── README.md                   # You are here
```

## Installation

### For WorkBuddy Users

Place the skill folder under your WorkBuddy skills directory:

```bash
# User-level (available across all projects)
cp -r mbb-consultant-distiller ~/.workbuddy/skills/

# Or project-level (shared with team)
cp -r mbb-consultant-distiller ./.workbuddy/skills/
```

### Usage

Just talk naturally:

```
"整理这份文档"
"帮我写行业分析"
"把这段内容改成咨询风格"
"analyze the China EV market for me"
"write a report on..."
```

## Version History

| Version | Changes |
|---------|---------|
| 2.1.0 | Added Mode B (topic generation), framework auto-matching, hypothesis-driven writing, web search with degradation strategy |
| 2.0.0 | Added smart clarification engine, anti-pattern rules, special case handling |
| 1.1.0 | Original version by community (document rewrite only) |

## License

MIT
