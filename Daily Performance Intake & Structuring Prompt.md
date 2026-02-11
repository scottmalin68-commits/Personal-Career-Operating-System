# Daily Performance Intake & Structuring Prompt
Author: Scott M
Version: 1.4
Last Updated: 2026-02-11
## Goal
Transform semi-structured daily activity notes into a standardized, queryable Markdown performance log entry suitable for:
- Long-term performance tracking
- Quarterly and annual review preparation
- Promotion readiness analysis
- Personal performance dashboard analytics
- Burnout and sustainability monitoring
Output must be: structured, strictly evidence-based, non-exaggerated, neutral in tone, safe for executive visibility (professional language, no slang, no subjective hype), and privacy-protected (redact or generalize sensitive, personal, or proprietary information).

---
## Changelog
### v1.4 (external feedback addition)
- Added optional "External Feedback / Notes" intake field for manager, peer, or cross-team comments
- Introduced Feedback Signal Hooks for neutral extraction and pattern flagging
- Extended Trend Signals and Skill Signals to include external feedback patterns
- Added external_feedback_present metadata flag
### v1.3 (privacy & sensitivity revision)
- Added Sensitivity Scan (pre-validation) with redaction/generalization rules
- Extended output flags with privacy_flags section
- Added user reminder guidance for anonymization in intake
- Strengthened narrative sections to use generalized language when needed
- Updated Goal to explicitly include privacy protection
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
External Feedback / Notes (optional):
- (brief notes from manager 1:1s, peers, cross-team members, etc. – e.g., "Manager: strong initiative on triage script", "Peer: helpful collab on detection rule", "Cross-team: appreciated quick response to alert")
(If input is unstructured or paragraph form, attempt to parse into these categories before proceeding.)

**User reminder**: For privacy, please anonymize any sensitive, personal, or proprietary information in your notes (e.g., use "Client A", "Project X", "a major customer", avoid real names, IP addresses, financial figures, health data, etc.). For External Feedback, generalize sources if needed (e.g., "a peer" instead of names) and keep notes concise/factual.

---
## AI Responsibilities
### 0. Sensitivity Scan (runs before Validation Pass)
Scan the entire input for potential sensitive, personal, or proprietary information, including but not limited to:
- Real names of individuals or clients
- Specific company names (when not public/generic)
- IP addresses, internal system IDs, credentials
- Financial amounts, contract values, PII
- Health-related details, personal struggles beyond general energy/mood
- Trade secrets, unreleased product details, confidential project specifics
Handling rules:
- If detected → Redact or generalize (e.g., "Client XYZ breach" → "a client data incident"; "IP 192.168.x.x" → "[IP redacted]"; "met with Jane Doe" → "met with a stakeholder").
- Never output raw sensitive data in any section.
- Flag redactions in output (see privacy_flags below).
- If redaction would prevent accurate scoring/metrics, ask one targeted clarifying question (e.g., "Can you provide an anonymized version of the client/incident description?").
- Limit sensitivity-related questions to 1 total (counts toward the 3-question cap).
Prioritize privacy over detail preservation.

### 1. Validation Pass (in priority order – ask at most 3 questions total)
After sensitivity scan, check in this order and ask only if critical:
0. Sensitivity-related clarification needed (only if blocks scoring) → 1 question max
1. Date missing or invalid format → Ask for YYYY-MM-DD
2. Energy missing or not 1–10 integer → Ask to correct
3. Major automation mentioned without clarity → Ask:
   - Is the automation/script reusable?
   - Estimated time saved per future use (if known)?
4. Incidents/alerts mentioned without quantity → Ask approximate count and severity (low/medium/high)
5. Any other critical vagueness blocking scoring/metrics → Ask up to 2 more targeted questions
If after 3 questions data remains insufficient for scoring/metrics, proceed with available evidence only and set confidence=low.
Never fabricate numbers, never assume time savings, never inflate impact.

### 2. Initiative Scoring Logic
Infer initiative_level strictly from evidence. Default to the **lowest** level supported by the text when ambiguous.
- **reactive** — Responding to assigned alerts/tickets, primarily execution of assigned tasks, no systemic/process improvement mentioned
- **proactive** — Improving existing processes, writing reusable scripts/tools, tuning detections/rules, suggesting enhancements, cross-team help beyond own assignment
- **strategic** — Designing new controls/systems, reducing systemic risk at scale, influencing cross-team/org direction, creating long-term measurable automation, driving operational/cultural change
Tiebreaker: when evidence could support multiple levels, choose the lowest defensible one.

### 3. Burnout Signal Hooks
Extract and record signals only – **never diagnose burnout**.
- sustained_low_energy: yes if energy ≤4 **and** previous 2+ days also ≤5 (if history available) or user explicitly notes pattern
- high_meeting_load: yes if ≥6 hours of meetings **or** “meeting-heavy day” / “back-to-back meetings” language
- high_reactive_load: yes if ≥70% of described work appears reactive (estimate from content volume)
- frustration_signal: yes if strong negative language (“frustrating”, “exhausting”, “infuriating”, “burning out”)
Only set yes if clear textual evidence exists.

### 4. Metric Tracking Refinement
Track only what is explicitly or reasonably inferable from intake. Label estimates clearly.
- Alerts investigated: [number or range]
- Scripts created: [number] (reusable: yes/no)
- Detection rules modified: [number]
- Meetings attended: [number or hours]
- Estimated hours saved: [number] (per use / total) – **only if user states or strongly implies**
- Other measurable outputs: [brief description]
Separate confirmed vs. estimated. Do **not** project cumulative savings unless user provides basis.

### 5. Scoring Rules
- impact_score (0–10): (number of distinct contributions + initiative bonus + metric strength) / max possible
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

### 6. Feedback Signal Hooks
Extract and record external feedback (manager, peer, cross-team, etc.) only when provided in the dedicated field – never infer, fabricate, or solicit unless critical vagueness blocks other scoring.
- Record notes verbatim or lightly paraphrased for clarity if lengthy.
- Tag source type if user specified (e.g., Manager, Peer, Cross-team); default to "External" if unspecified.
- Identify recurring themes only across multiple days/entries (e.g., "collaboration praised" on 3+ occasions → note in Trend Signals).
- Do not assign scores, impact, initiative levels, or burnout flags based on feedback.
- Apply Sensitivity Scan: generalize any names/details (e.g., "Jane said..." → "a stakeholder noted...").
- Flag presence in metadata (external_feedback_present).
Only process if user provides content in the field.

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
tags: [tag1, tag2, tag3] ← max 5, keyword-style
impact_score: #/10
confidence: low | medium | high
external_feedback_present: yes | no
burnout_flags:
  sustained_low_energy: yes | no
  high_meeting_load: yes | no
  high_reactive_load: yes | no
  frustration_signal: yes | no
privacy_flags:
  sensitive_redacted: yes | no   ← "yes" if any redaction/generalization occurred
  pii_detected: yes | no
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
(Include only sections with content. Use generalized language if original input contained sensitive details; add "(generalized)" if altered.)

## Quantified Metrics
- Alerts investigated:
- Scripts created:
- Detection rules modified:
- Meetings attended:
- Estimated hours saved:
- Other measurable outputs:
(Label estimates clearly, e.g., (est.))

## Impact Summary
Concise, evidence-based, neutral summary of demonstrated value. No exaggeration. Use generalized terms where privacy required.

## Skill Signals
- Technical: …
- Behavioral: … (include patterns from external feedback if relevant, e.g., "Behavioral: collaboration noted positively by peers/cross-team in multiple entries")
(Max 6–8 bullets total)

## Trend Signals
Observations useful for quarterly aggregation, promotion analysis, burnout monitoring.
- [existing or inferred trends...]
- External feedback patterns: [neutral summary if patterns exist, e.g., "Manager highlighted proactive contributions in 2 entries"; "Peers/cross-team noted helpful collaboration on detection work"; "No external feedback recorded"]

## Confidence Explanation
Short rationale for the assigned confidence level (include note if external feedback influenced trends but not scores).