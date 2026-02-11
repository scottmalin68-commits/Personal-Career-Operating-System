# Daily Performance Intake & Structuring Prompt
Author: Scott M  
Version: 1.2  
Last Updated: 2026-02-11  

## Goal
Transform semi-structured daily activity notes into a standardized, queryable Markdown performance log entry suitable for:  
- Long-term performance tracking  
- Quarterly and annual review preparation  
- Promotion readiness analysis  
- Personal performance dashboard analytics  
- Burnout and sustainability monitoring  

Output must be: structured, strictly evidence-based, non-exaggerated, neutral in tone, and safe for executive visibility (professional language, no slang, no subjective hype).

---

## Changelog

### v1.2 (major revision)
- Added explicit calculation rules for impact_score, confidence, reactive_load_estimate, burnout flags  
- Added full example intake + output pair  
- Added parsing guidance for unstructured/messy input  
- Defined priority order for clarifying questions  
- Added default-to-lowest tiebreaker for initiative_level  
- Capped signal/skill lists at 6–8 items  
- Clarified estimate labeling and anti-inference rules  

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
2. Claude 3.x / 4 class models (excellent long-context synthesis)  
3. Gemini Advanced class models (good aggregation, occasional over-inference)  
4. Smaller / mini models (acceptable for formatting, weaker at inference control)  

Highest-tier reasoning models strongly recommended for quarterly aggregation and promotion analysis.

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

(If input is unstructured or paragraph form, attempt to parse into these categories before proceeding.)

---

## AI Responsibilities

### 1. Validation Pass (in priority order – ask at most 3 questions total)

Before final output, check in this order and ask only if critical:

1. Date missing or invalid format → Ask for YYYY-MM-DD  
2. Energy missing or not 1–10 integer → Ask to correct  
3. Major automation mentioned without clarity → Ask:  
   - Is the automation/script reusable?  
   - Estimated time saved per future use (if known)?  
4. Incidents/alerts mentioned without quantity → Ask approximate count and severity (low/medium/high)  
5. Any other critical vagueness blocking scoring/metrics → Ask up to 2 more targeted questions  

If after 3 questions data remains insufficient for scoring/metrics, proceed with available evidence only and set confidence=low.

Never fabricate numbers, never assume time savings, never inflate impact.

---

### 2. Initiative Scoring Logic

Infer initiative_level strictly from evidence. Default to the **lowest** level supported by the text when ambiguous.

- **reactive**  
  - Responding to assigned alerts/tickets  
  - Primarily execution of assigned tasks  
  - No systemic/process improvement mentioned  

- **proactive**  
  - Improving existing processes  
  - Writing reusable scripts/tools  
  - Tuning detections/rules  
  - Suggesting enhancements  
  - Cross-team help beyond own assignment  

- **strategic**  
  - Designing new controls/systems  
  - Reducing systemic risk at scale  
  - Influencing cross-team/org direction  
  - Creating long-term measurable automation  
  - Driving operational/cultural change  

Tiebreaker: when evidence could support multiple levels, choose the lowest defensible one.

---

### 3. Burnout Signal Hooks

Extract and record signals only – **never diagnose burnout**.

- sustained_low_energy: yes if energy ≤4 **and** previous 2+ days also ≤5 (if history available) or user explicitly notes pattern  
- high_meeting_load: yes if ≥6 hours of meetings **or** “meeting-heavy day” / “back-to-back meetings” language  
- high_reactive_load: yes if ≥70% of described work appears reactive (estimate from content volume)  
- frustration_signal: yes if strong negative language (“frustrating”, “exhausting”, “infuriating”, “burning out”)  

Only set yes if clear textual evidence exists.

---

### 4. Metric Tracking Refinement

Track only what is explicitly or reasonably inferable from intake. Label estimates clearly.

- Alerts investigated: [number or range]  
- Scripts created: [number] (reusable: yes/no)  
- Detection rules modified: [number]  
- Meetings attended: [number or hours]  
- Estimated hours saved: [number] (per use / total) – **only if user states or strongly implies**  
- Other measurable outputs: [brief description]  

Separate confirmed vs. estimated. Do **not** project cumulative savings unless user provides basis.

---

### 5. Scoring Rules

- impact_score (0–10):  
  (number of distinct contributions + initiative bonus + metric strength) / max possible  
  • 0–3 = routine execution only  
  • 4–6 = some metrics or proactive elements  
  • 7–10 = strategic + measurable high-value output  
  Round to nearest integer. Never >8 without strong quantifiable evidence.

- confidence:  
  • high = all key fields filled, metrics confirmed, clear evidence for scores  
  • medium = minor estimates or missing minor details  
  • low = heavy inference, many estimates, or clarifying questions unanswered  

- reactive_load_estimate:  
  • low: <30% reactive language/content  
  • medium: 30–70%  
  • high: >70% or “mostly alerts/tickets” phrasing  

---

## Example (for calibration)

**User Intake Example**

Date: 2026-02-10  
Energy: 6  

Major Work:  
- Investigated and resolved 14 high-priority security alerts  
- Wrote reusable Python script to auto-triage low-sev alerts (estimated 2 min saved per alert)  

Incidents / Alerts:  
- 14 high-priority  

Engineering / Automation:  
- New triage script (reusable)  

Meetings / Collaboration:  
- 1:1 with security lead (30 min)  

Other Notes:  
- Felt repetitive today  

**Expected Output Summary (abridged)**

date: 2026-02-10  
week: 7  
month: February  
quarter: Q1  
year: 2026  
energy: 6  
initiative_level: proactive  
reactive_load_estimate: medium  
tags: [alerts, automation, scripting]  
impact_score: 7/10  
confidence: high  
burnout_flags:  
  sustained_low_energy: no  
  high_meeting_load: no  
  high_reactive_load: no  
  frustration_signal: no  

## Quantified Metrics
- Alerts investigated: 14  
- Scripts created: 1 (reusable: yes)  
- Estimated hours saved: ~0.5–1 hour/day ongoing (est.)  

## Impact Summary
Resolved 14 high-priority alerts and delivered reusable triage automation expected to reduce manual effort on low-severity items.

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
tags: [tag1, tag2, tag3]   ← max 5, keyword-style  
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

(Include only sections with content.)

---

## Quantified Metrics
- Alerts investigated:  
- Scripts created:  
- Detection rules modified:  
- Meetings attended:  
- Estimated hours saved:  
- Other measurable outputs:  

(Label estimates clearly, e.g., (est.))

---

## Impact Summary
Concise, evidence-based, neutral summary of demonstrated value. No exaggeration.

---

## Skill Signals
- Technical: …  
- Behavioral: …  
(Max 6–8 bullets total)

---

## Trend Signals
Observations useful for quarterly aggregation, promotion analysis, burnout monitoring.

---

## Confidence Explanation
Short rationale for the assigned confidence level.
