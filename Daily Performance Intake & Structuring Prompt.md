# Daily Performance Intake & Structuring Prompt
Author: Scott M
Version: 1.1
Last Updated: 2026-02-11

## Goal
Transform semi-structured daily activity notes into a standardized, queryable Markdown performance log entry suitable for:

- Long-term performance tracking
- Quarterly and annual review preparation
- Promotion readiness analysis
- Personal performance dashboard analytics
- Burnout and sustainability monitoring

Output must be structured, evidence-based, non-exaggerated, and safe for executive visibility.

---

## Changelog

### v1.1
- Added Burnout Signal Hooks
- Added refined metric tracking logic
- Added formal initiative scoring framework
- Added AI engine ranking section
- Strengthened anti-exaggeration safeguards

### v1.0
- Initial structured daily intake system
- Metadata auto-calculation
- Confidence scoring
- Clarifying question guardrails

---

## Recommended AI Engines (Best → Worst for Structured Analysis Tasks)

1. GPT-5 class models (strongest structured reasoning + consistency)
2. Claude 3.x class models (excellent long-context synthesis)
3. Gemini Advanced class models (good aggregation, occasional over-inference)
4. Smaller / mini models (acceptable for formatting, weaker at inference control)

For quarterly aggregation and promotion analysis, highest-tier reasoning models are strongly recommended.

---

## Intake Format (User Provides Below This Line)

Date:
Energy (1–10):

Major Work:
- 

Incidents / Alerts:
- 

Engineering / Automation:
- 

Meetings / Collaboration:
- 

Compliance / Risk:
- 

Other Notes:
- 

---

## AI Responsibilities

### 1. Validation Pass

Before generating final output:

- If Date is missing → Ask for it.
- If metrics are vague (e.g., "worked alerts") → Ask for counts.
- If automation is mentioned → Ask:
    - Is it reusable?
    - Estimated time saved per use?
- If incidents are mentioned → Ask for severity if available.
- If impact is unclear → Ask up to 3 targeted clarifying questions.
- Do NOT exceed 3 follow-up questions.
- If sufficient information is present, proceed without questions.

Never fabricate missing data.
Never inflate business impact.

---

### 2. Initiative Scoring Logic

Infer initiative_level based on evidence:

reactive:
- Responding to assigned alerts/tickets
- Primarily execution-based tasks
- No systemic improvement

proactive:
- Improving processes
- Writing reusable scripts
- Tuning detections
- Suggesting enhancements
- Cross-team assistance beyond assignment

strategic:
- Designing controls
- Reducing systemic risk
- Influencing cross-team direction
- Creating long-term automation
- Driving measurable operational change

Base classification strictly on documented evidence.

---

### 3. Burnout Signal Hooks

Extract and preserve signals relevant for long-term sustainability analysis:

- Energy score trend flag
- High meeting volume indicator
- % reactive workload (estimate if reasonable)
- Overtime/weekend mention
- Frustration language
- Sustained alert-heavy days

Do NOT diagnose burnout.
Only record signals for later analysis.

---

### 4. Metric Tracking Refinement

When metrics are present:

- Separate confirmed vs estimated metrics.
- Clearly label estimated values.
- Do not assume time savings unless stated.
- Avoid cumulative projections unless user provides basis.
- Track:
    - Alerts investigated
    - Scripts created
    - Detection rules modified
    - Meetings attended
    - Estimated hours saved
    - Risk-reduction actions
    - Cross-team engagements

Only include metrics supported by intake data.

---

## Output Format (Strict)

---
date: YYYY-MM-DD
week: ##
month: Month
quarter: Q#
year: YYYY
energy: #
initiative_level: reactive | proactive | strategic
reactive_load_estimate: low | medium | high
tags: [tag1, tag2, tag3]
impact_score: #/10
confidence: low | medium | high
burnout_flags:
  sustained_low_energy: yes | no
  high_meeting_load: yes | no
  high_reactive_load: yes | no
  frustration_signal: yes | no
---

# Daily Performance Log – YYYY-MM-DD

## Key Contributions

### Incident Response
- 

### Engineering / Automation
- 

### Risk / Compliance
- 

### Collaboration
- 

(Include only applicable sections.)

---

## Quantified Metrics
- Alerts investigated:
- Scripts created:
- Detection rules modified:
- Meetings attended:
- Estimated hours saved:
- Other measurable outputs:

(Label estimates clearly.)

---

## Impact Summary
Concise, evidence-based summary of demonstrated value.
No exaggeration.

---

## Skill Signals
List technical and behavioral competencies demonstrated.

---

## Trend Signals
Observations useful for:
- Quarterly aggregation
- Promotion analysis
- Burnout detection

---

## Confidence Explanation
Explain rationale for assigned confidence level.
