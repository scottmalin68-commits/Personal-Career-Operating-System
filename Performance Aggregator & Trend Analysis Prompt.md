# Performance Aggregator & Trend Analysis Prompt
Author: Scott M  
Version: 1.2  
Last Updated: 2026-02-11  

## Goal

Aggregate multiple structured Daily Performance Log markdown entries (v1.2 format) and generate:  
- Reliable performance dashboard metrics  
- Trend analysis with statistical safeguards  
- Initiative distribution  
- Promotion-signal extraction (strict evidence-based)  
- Burnout & sustainability signal detection  
- Anomaly and workload spike identification  
- Data continuity analysis  

Prioritize analytical integrity over optimism.  

Never fabricate activity.  
Never inflate impact.  
Never assume missing data equals zero.  
Never extrapolate or interpolate missing values.

All source data has been sanitized during intake processing. Maintain privacy by using only the generalized/anonymized descriptions provided; never reconstruct, de-anonymize, or introduce specific names, clients, companies, or proprietary details.

---

## How To Use This Prompt

1. Paste this full prompt into the AI.  
2. Below the divider line, paste one or more complete Daily Performance Log markdown entries (v1.2 format).  
3. Optionally specify:  
   - Date range (e.g., "Analyze 2026-01-01 to 2026-03-31")  
   - Quarter (e.g., "Analyze Q1 2026")  

The AI will:  
- Validate input format and parse entries  
- Filter by date range if requested  
- Report dataset issues  
- Aggregate supported metrics  
- Detect patterns, spikes, and signals  
- Produce structured output  

IMPORTANT: This prompt expects only standardized v1.2 daily log markdown entries. Do not paste raw notes or unstructured text.

---

## Changelog

### v1.2 (major revision)
- Added precise thresholds/formulas for variance, trends, streaks, spikes, overlap  
- Added composite confidence rubric  
- Added two worked examples (clean & gappy/spiky)  
- Defined input validation & malformed entry rejection  
- Clarified gap treatment in streaks/trends  
- Added density & impact qualifiers for promotion signals  
- Defined section omission rules and limitation phrasing  

### v1.1
- Added incomplete metric coverage detection  
- Added low sample-size warnings  
- Added repeated-behavior requirement for promotion signals  
- Added burnout variance & overlap detection  
- Added anomaly spike detection  
- Added data continuity gap detection  

### v1.0
- Initial aggregation framework  

---

## Recommended AI Engines (Best → Worst)

1. GPT-5 class models (strongest reasoning discipline & trend control)  
2. Claude 3.x / 4 class models (excellent long-context synthesis)  
3. Gemini Advanced class models (good counting, occasional over-inference)  
4. Smaller / mini models (adequate for counting, weak pattern discipline)  

Quarterly/annual analysis → use highest-tier models only.

---

## AI Responsibilities

### 1. Input & Dataset Validation

- Parse only blocks starting with `date: YYYY-MM-DD` and containing the full YAML-like header + sections.  
- Reject malformed entries (missing date, invalid energy, wrong format) and report: "X entries rejected due to format errors."  
- Count valid entries.  
- If valid entries < 5: Flag "Insufficient data for reliable trend analysis." → overall confidence = low  
- If valid entries < 10: Flag initiative distribution & promotion signals as low confidence.  

Date gaps:  
- Sort entries by date.  
- Flag gaps > 7 calendar days between consecutive entries.  
- Report total gap days and largest gap.  
- Gaps are **not** filled — treat as missing (no interpolation).

Date range filtering: inclusive of start and end dates if provided.

---

### 2. Metric Aggregation Rules

Aggregate **only** explicitly stated numeric values. Absent field = unknown (not zero).  

If >20% of entries lack a given metric:  
- Flag: "Incomplete coverage for [metric]; totals likely underrepresent activity."  

Totals (with notes):  
- Total Alerts Investigated  
- Total Scripts Created  
- Total Detection Rules Modified  
- Total Meetings Attended (or hours if provided)  
- Cumulative Estimated Hours Saved (label "(cumulative est.)")  
- Risk-Reduction Actions  
- Cross-Team Engagements  

---

### 3. Initiative Distribution

- Count days by initiative_level  
- Calculate % = (count / total valid entries) × 100  
- If <10 entries → "Low statistical confidence"  
- Always show absolute counts  

Example:  
Reactive: 12 days (48%)  

---

### 4. Estimated Work Distribution

Primary: sum of quantifiable metrics per category (alerts → Incident Response, scripts/rules → Engineering/Automation, etc.)  
Secondary (if metrics sparse): count of non-empty sections per day  

Normalize to percentages.  
Always label: "Estimated Work Distribution (metric-weighted where available)"  
Never imply precise time allocation.

---

### 5. Anomaly & Spike Detection

Define period average = total / valid entries (excluding zero days only if explicitly off-days).  

Spikes flagged if:  
- Alerts investigated ≥ 2.0 × period average **and** ≥ 8 absolute  
- impact_score ≥ 9  
- 3+ consecutive days with reactive_load_estimate = high  
- 4+ consecutive days with high_meeting_load = yes  

Label as "Operational Spike Events"  
Do not speculate cause.

---

### 6. Burnout & Sustainability Signal Detection

- Average Energy: mean of all energy scores  
- Energy Variance: sample standard deviation (high if ≥ 2.5)  
- Sustained Low Energy: 3+ **consecutive** days with energy ≤ 5 (gaps reset streak)  
- Reactive/Meeting Overlap: 3+ consecutive days where (high_reactive_load = yes OR high_meeting_load = yes) **and** energy ≤ 5  
- Downward Energy Trend: if ≥ 10 entries, fit simple linear regression; flag if slope ≤ –0.15 points/day  

Only report patterns — never diagnose burnout.

---

### 7. Promotion Signal Extraction (Strict)

Count only if:  
- Behavior appears ≥ 2 times across dataset **OR**  
- Single instance explicitly described as systemic / org-wide / long-term impact  

Density qualifier: ≥ 2 occurrences in any 30-day window strengthens signal.  

Categories:  
- **Strength Indicators (Repeated or Systemic Evidence)**  
  - Reusable automation (≥2)  
  - Detection improvements (≥2)  
  - Cross-team influence (repeated)  
  - Risk-reduction ownership  
  - Designing controls / Driving process changes  
  - Long-term automation initiatives  

- **Isolated Examples**  
  - One-off behaviors not meeting above criteria  

- **Missing or Underrepresented**  
  - Behaviors that appear 0–1 time despite ≥20 entries (e.g., no strategic days)  

Never speculate what *should* appear.

---

### 8. Overall Confidence Rubric

- **High**: ≥20 valid entries, <10% gap days, >80% metric coverage, low energy variance (<2.0)  
- **Medium**: 10–19 entries, moderate gaps/metrics, or moderate variance  
- **Low**: <10 entries, large gaps, poor metric coverage, high variance, or many estimates  

Always explain main limitations.

---

## Example Outputs (Abridged)

**Example 1 – Clean 14-day dataset**  
→ High confidence, smooth energy ~7.2, 35% proactive, no spikes, 2× reusable automation → strength indicator  

**Example 2 – Gappy 8-day dataset**  
→ Low confidence, 11-day gap flagged, average energy 4.8, sustained low energy (4 consec ≤5), high reactive overlap, isolated strategic day  

---

## Output Format (Strict)

# Aggregated Performance Report – [Scope]

## Scope Analyzed
- Date Range: [start – end or full]  
- Valid Entries: X (Y rejected)  
- Data Continuity Gaps: yes/no (details: largest X days, total gap days Z)  

## Dataset Reliability
- Entry Count Assessment:  
- Metric Coverage Assessment:  
- Statistical Confidence Level:  

## Executive Summary
Concise evidence-based overview.  

## Quantified Metrics
- Total Alerts Investigated:  
- Total Scripts Created:  
- …  

## Initiative Distribution
- Reactive: X days (X%)  
- Proactive: X days (X%)  
- Strategic: X days (X%)  
Confidence:  

## Estimated Work Distribution
- Incident Response: X%  
- Engineering / Automation: X%  
- …  
Method: metric-weighted where available  

## Operational Spike Events
- High Impact Days (impact_score ≥9):  
- Alert Volume Spikes:  
- Consecutive High Reactive Periods:  
- High Meeting Clusters:  

## Promotion-Level Signals

### Strength Indicators (Repeated or Systemic)
-

### Isolated Examples
-

### Missing / Underrepresented Signals
-

## Burnout & Sustainability Signals
- Average Energy: X.X  
- Energy Variance: X.X (high/low)  
- Sustained Low Energy Periods:  
- Reactive/Meeting + Low Energy Overlap:  
- Downward Energy Trend: yes/no (slope –X.XX/day)  

## Overall Confidence Level
low | medium | high  

Limitations / Key Caveats:  
- …

---

Paste Valid Daily Log Entries Below This Line
---------------------------------------------------------