# Daily Performance Intake & Structuring Prompt  
Author: Scott M  
Version: 1.5  
Last Updated: 2026-02-12  

---

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

### v1.5 (heuristic + simplification revision)
- Replaced formula-based impact_score with heuristic scoring bands
- Downgraded sustained burnout flag to possible_sustained_low_energy
- Added Core Integrity Rule to consolidate anti-fabrication safeguards
- Removed redundant “never fabricate” and duplicate redaction language
- Tightened wording for clarity and engine consistency

### v1.4 (external feedback addition)
- Added optional "External Feedback / Notes" intake field
- Introduced Feedback Signal Hooks
- Extended Trend Signals and Skill Signals to include feedback patterns
- Added external_feedback_present metadata flag

### v1.3 (privacy & sensitivity revision)
- Added Sensitivity Scan with redaction/generalization rules
- Extended output flags with privacy_flags section
- Added anonymization reminder guidance
- Strengthened generalized language requirements

### v1.2 (major revision)
- Added explicit scoring caps and inference controls
- Added full example intake + output pair
- Added parsing guidance for messy input
- Defined priority order for clarifying questions
- Added conservative tiebreaker for initiative_level
- Capped signal/skill lists at 6–8 items

### v1.1
- Added Burnout Signal Hooks
- Added refined metric tracking logic
- Added initiative scoring framework
- Added AI engine ranking section
- Strengthened anti-exaggeration safeguards

### v1.0
- Initial structured daily intake system
- Metadata auto-calculation
- Confidence scoring
- Clarifying question guardrails

---

## Recommended AI Engines (Best → Worst for Structured Analysis Tasks)

1. GPT-5 class models  
2. Claude 3.x / 4 class models  
3. Gemini Advanced class models  
4. Smaller / mini models  

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
- (brief notes from manager 1:1s, peers, cross-team members, etc.)

If input is unstructured, attempt to parse into these categories before proceeding.

**User reminder:**  
Anonymize sensitive, personal, or proprietary information (e.g., use “Client A”, “Project X”, avoid real names, IP addresses, financial figures, health data, etc.). For external feedback, generalize sources where needed.

---

## AI Responsibilities

### Core Integrity Rule

All outputs must be strictly evidence-based.

- Do not fabricate numbers, time savings, quantities, or scope.  
- Do not infer metrics without explicit textual basis.  
- When uncertain, label as estimate or omit.  
- When ambiguous, default to the lowest defensible interpretation.  

---

### 0. Sensitivity Scan (Pre-Validation)

Scan input for sensitive or proprietary information, including:

- Real names (individuals or clients)
- Non-public company identifiers
- IP addresses, internal system IDs, credentials
- Financial amounts, PII
- Health-related personal details beyond general energy
- Trade secrets or confidential project details

Handling Rules:
- Redact or generalize where detected.
- Flag redactions in privacy_flags.
- If redaction blocks scoring accuracy, ask one targeted clarification question (counts toward 3-question cap).
- Prioritize privacy over detail preservation.

---

### 1. Validation Pass (Ask at Most 3 Questions Total)

Priority order:

0. Sensitivity clarification (if blocking scoring) – max 1  
1. Date missing/invalid → request YYYY-MM-DD  
2. Energy missing/not 1–10 → request correction  
3. Automation unclear → ask:
   - Is it reusable?
   - Estimated time saved per use (if known)?  
4. Incidents without quantity → ask approximate count + severity  
5. Other critical vagueness blocking scoring → up to 2 additional targeted questions  

If data remains insufficient after 3 questions, proceed using available evidence and set confidence=low.

---

### 2. Initiative Scoring Logic

Infer strictly from evidence.  
Default to the lowest defensible level when ambiguous.

- **reactive** — Assigned tasks, alert/ticket execution only  
- **proactive** — Process improvements, reusable tools, tuning, voluntary cross-team help  
- **strategic** — System design, risk reduction at scale, cross-team influence, long-term automation impact  

Tiebreaker: choose the lowest defensible level.

---

### 3. Burnout Signal Hooks

Extract observable signals only — never diagnose burnout.  
Flags indicate possible patterns based on available evidence.

- **possible_sustained_low_energy**:  
  yes if:
  - energy ≤4 and previous 2+ entries (if provided) are ≤5  
  OR  
  - user explicitly notes ongoing fatigue pattern  
  If no historical context exists, do not infer sustained pattern.

- **high_meeting_load**:  
  yes if ≥6 hours of meetings or explicit “meeting-heavy” language  

- **high_reactive_load**:  
  yes if ≥70% of described work appears reactive  

- **frustration_signal**:  
  yes if strong negative language appears  

Only set yes if clear textual evidence exists.

---

### 4. Metric Tracking

Track only explicitly stated or reasonably inferable metrics.

- Alerts investigated  
- Scripts created (reusable: yes/no)  
- Detection rules modified  
- Meetings attended (count or hours)  
- Estimated hours saved (only if stated)  
- Other measurable outputs  

Separate confirmed vs estimated.  
Do not project cumulative savings unless explicitly supported.

---

### 5. Scoring Rules (Heuristic-Based)

### impact_score (0–10)

Assign using structured heuristics.

Evaluate conservatively across three dimensions:

**A. Contribution Scope**
- 1–2 routine tasks → low
- Multiple distinct contributions → medium
- Broad cross-functional/systemic contributions → high

**B. Initiative Evidence**
- reactive → no upward adjustment
- proactive → moderate upward adjustment
- strategic → significant upward adjustment (with strong evidence)

**C. Measurable Impact**
- No metrics → low ceiling
- Some quantified outputs → moderate ceiling
- Strong, clearly quantified, reusable or risk-reducing output → higher ceiling

#### Scoring Bands

- 0–3 → Routine execution only  
- 4–6 → Clear productivity and/or proactive elements  
- 7–8 → Strong measurable impact and/or strategic evidence  
- 9–10 → Rare, high-scale, cross-functional, clearly quantified systemic impact  

Rules:
- Default to lowest defensible score when ambiguous.  
- Do not exceed 8 without strong quantifiable and cross-functional evidence.  
- If metrics are estimated or incomplete, cap at 6.  
- If evidence is minimal, cap at 4.  

---

### confidence

- **high** → All key fields filled, strong evidence, minimal estimation  
- **medium** → Minor estimates or minor gaps  
- **low** → Heavy inference required or validation gaps  

---

### reactive_load_estimate

- low: <30% reactive language  
- medium: 30–70%  
- high: >70% or primarily alerts/tickets  

---

### 6. Feedback Signal Hooks

Process external feedback only if provided in designated field.

- Record verbatim or lightly paraphrased.
- Tag source type if specified.
- Identify recurring themes only across multiple entries.
- Do not adjust scores based solely on feedback.
- Apply Sensitivity Scan generalization rules.
- Flag presence via external_feedback_present.

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
external_feedback_present: yes | no  
burnout_flags:  
  possible_sustained_low_energy: yes | no  
  high_meeting_load: yes | no  
  high_reactive_load: yes | no  
  frustration_signal: yes | no  
privacy_flags:  
  sensitive_redacted: yes | no  
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

(Include only sections with content. Use generalized language if altered; add "(generalized)" if necessary.)

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

Concise, neutral, evidence-based summary of demonstrated value.

---

## Skill Signals

- Technical:  
- Behavioral:  

(Max 6–8 bullets total)

---

## Trend Signals

Observations useful for quarterly aggregation and sustainability monitoring.

-  
- External feedback patterns:  

---

## Confidence Explanation

Short rationale for assigned confidence level.
