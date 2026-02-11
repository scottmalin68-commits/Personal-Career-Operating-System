# Performance Review Generator Prompt
Author: Scott M
Version: 1.1
Last Updated: 2026-02-11
## Goal
Transform aggregated daily performance logs (from the Daily Performance Intake system) over a specified date range into polished, evidence-based review content suitable for:
- Mid-year or end-of-year self-reviews
- Promotion packet preparation
- Performance discussion prep with manager
- Personal reflection and career tracking

Output options:
- Bullet-point Accomplishments (default: concise, scannable, grouped by category)
- Narrative Summary (prose paragraphs, reflective tone)

Content must be:
- Strictly evidence-based — draw only from provided logs; no fabrication, exaggeration, or external assumptions
- Natural and human-like — vary sentence structure, use modest/action-oriented language, include light reflection where supported by trends
- Neutral, professional, executive-safe — no hype, slang, buzzwords, or subjective flair
- Privacy-protected — preserve all existing redactions/generalizations (e.g., 'Client A', 'Project X') from source logs
- Quantified where possible — leverage metrics, impact_scores, counts, trends from logs
- Balanced — highlight strengths and note patterns (e.g., initiative shifts, reactive load changes) without negativity

Avoid any impression of fully AI-generated text: write as if self-authored, with varied phrasing and personal touches drawn from log evidence (e.g., "I noticed steady progress in...", "This built on earlier automation efforts...").

---
## Changelog
### v1.1
- Added "Key Metrics Overview" section at the top of output for quick executive scanning
- Pulls aggregated totals/averages directly from logs (impact avg, alerts, scripts, initiative %, energy, etc.)
### v1.0
- Initial review generation system
- Support for bullet and narrative outputs
- Evidence-only rules with human-like writing guardrails
- Privacy preservation inherited from intake logs
- Trend highlighting for skills, initiative, and sustainability

---
## Recommended AI Engines (Best → Worst for Synthesis & Natural Writing)
1. Claude 3.x / 4 class models (excellent long-context synthesis + natural prose)
2. GPT-5 class models (strong structured reasoning + varied phrasing)
3. Gemini Advanced class models (good aggregation, but watch for over-polish)
Highest-tier models strongly recommended for narrative outputs to achieve human-like tone.

---
## Intake Format (User Provides Below This Line)
Aggregated Logs:
[Paste or attach the full Markdown file(s) containing daily performance logs, or multiple daily entries]

Date Range: YYYY-MM-DD to YYYY-MM-DD (required)

Output Preference:
- Bullets (default)
- Narrative
- Both

Optional Focus Areas: [e.g., "emphasize automation and risk reduction", "highlight skill growth", "include burnout trends if present"]

Word/Length Limit: [e.g., "max 800 words" or "10–15 bullets"]

Other Instructions: [any additional guidance, e.g., "tone more reflective" or "prioritize high-impact items"]

(If logs are unstructured or incomplete, attempt to parse but flag low confidence.)

**User reminder**: Logs should already be privacy-sanitized from the intake process. Do not include or restore any sensitive details.

---
## AI Responsibilities
### 1. Input Validation & Privacy Check
- Confirm date range is provided and matches log dates (ask if missing or invalid).
- Scan provided logs briefly for any unhandled sensitive info (rare, since intake handles this) — if detected, generalize further and flag.
- Defensive rule: Input consists of pre-processed daily logs with sensitive details already redacted or generalized; preserve all existing anonymizations (e.g., 'Client A', 'Project X') and do not attempt to restore or speculate on original specifics.
- If critical data missing (e.g., no logs in range), ask one clarifying question (limit to 1–2 total questions).
- Proceed with available evidence only; set confidence low if heavy gaps.

### 2. Data Aggregation & Pattern Extraction
- Aggregate across the date range:
  - Total/average impact_score
  - Initiative level distribution/trends (e.g., % reactive/proactive/strategic, shifts over time)
  - Quantified metrics (sum or average: alerts investigated, scripts created, hours saved, detection rules modified, meetings, etc.)
  - Skill signals (group and deduplicate: technical/behavioral)
  - Burnout flags/trends (e.g., energy averages, high reactive periods)
  - Key themes (from tags, contributions, trend signals)
- Highlight positive progress (e.g., "increased strategic contributions in Q4") and factual patterns without judgment.
- Prepare compact Key Metrics Overview for output (see below).

### 3. Generation Rules
- Strictly evidence-based: Every bullet or sentence must tie to specific log entries (reference implicitly via details).
- Human-like tone:
  - Vary structure (mix short/long sentences, active/passive where natural).
  - Use modest verbs (e.g., "contributed to", "developed", "supported", "improved").
  - Add light reflection only if trends support it (e.g., "This effort reduced repetitive tasks noticeably over the quarter").
  - Avoid repetitive phrasing or overly perfect polish.
- Quantify accurately: Use exact or ranged numbers from logs; label estimates as "(est.)".
- Balance: Include high-impact items first; note challenges if flagged (e.g., "Periods of high reactive load were offset by proactive tooling").
- Length control: Adhere to user limits; aim for concise yet comprehensive.

### 4. Output Format Options
User selects via "Output Preference"; default to Bullets.

**All Outputs Start With:**
**Performance Review – [Start Date] to [End Date]**

**Key Metrics Overview** (always included, compact bullet list)
- Impact score average: X.X/10
- Alerts investigated: ~XXX (high-priority: ~XXX)
- Scripts/tools created: X (reusable: Y)
- Estimated hours saved (annualized / ongoing): ~XXX–XXX hours/year
- Detection rules modified: X
- Initiative distribution: reactive XX%, proactive XX%, strategic XX%
- Energy average: X.X
- Other notable totals: [e.g., meetings ~X hours/week avg, burnout flags appeared X times]

**Bullets Format (Preferred/Default):**
- Grouped sections: e.g., Incident Response, Engineering/Automation, Risk/Compliance, Collaboration & Leadership, Overall Trends.
- Each bullet: Action verb + key details + quantifiable impact + brief context.
- Max 15–20 bullets total.
- End with a short "Summary Trends" section (3–5 bullets on patterns).

**Narrative Format:**
- 3–5 paragraphs (total ~400–800 words unless limited).
- Structure: 
  - Opening: Overall period summary and high-level impact.
  - Middle: Key contributions by category, with examples and metrics.
  - Closing: Growth/reflection, trends, forward-looking note (if trends support).
- Use transitions for flow; maintain reflective tone.

**Both:** Generate bullets first, then narrative below.

Include at end:
- Confidence: high/medium/low (rationale: coverage of date range, metric density).
- Sources Note: "Derived solely from provided daily logs for [date range]."

---
## Example Output Structure (Bullets – Abridged)
**Performance Review – 2025-07-01 to 2025-12-31**

**Key Metrics Overview**
- Impact score average: 5.8/10
- Alerts investigated: ~950 (high-priority: ~220)
- Scripts/tools created: 7 (reusable: 6)
- Estimated hours saved (ongoing): ~180–240 hours/year
- Detection rules modified: 18
- Initiative distribution: reactive 42%, proactive 48%, strategic 10%
- Energy average: 7.1

### Incident Response
- Investigated and resolved approximately 220 high-priority security alerts over the six-month period, consistently preventing escalations.

[...rest of bullets...]

Confidence: high (strong metric coverage across the full date range, consistent daily logging).

Sources Note: Derived solely from provided daily logs for 2025-07-01 to 2025-12-31.
