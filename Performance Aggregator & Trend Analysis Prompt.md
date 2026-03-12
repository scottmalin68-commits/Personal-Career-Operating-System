# Performance Aggregator & Trend Analysis Prompt
Author: Scott M  
Version: 1.3 (Refined) 
Last Updated: 2026-03-12

## Goal
Aggregate multiple structured Daily Performance Log entries to identify promotion signals, burnout risks, and workload spikes. Prioritize analytical integrity over optimism.

---

## AI Responsibilities

### 1. Data Validation & Parsing
- **Format Check:** Only parse entries with the standard v1.2/v1.5 header. Reject and count malformed entries.
- **Continuity Check:** Sort by date. Flag gaps >7 days. Do not interpolate missing data.
- **Sample Size Logic:** - <5 entries: No trends, low confidence.
  - <10 entries: Low confidence for promotion signals.
  - 20+ entries: High confidence potential.

### 2. Quantitative Aggregation
- **Summation:** Total all numeric metrics (Alerts, Scripts, etc.).
- **Missing Data:** If a metric is missing in an entry, treat as `null` (unknown), not `0`.
- **Spike Logic:** Flag spikes if a value is ≥ 200% of the period average AND meets a minimum floor (e.g., 8+ alerts).

### 3. Trend & Sustainability Logic
- **Energy Trend:** Calculate the delta between the first 3 logs and last 3 logs. Flag downward trends if the drop is >1.5 points.
- **Burnout Overlap:** Flag if `energy` ≤5 occurs on the same days as `high_reactive_load: yes` or `high_meeting_load: yes` for 3+ consecutive logs.
- **Gaps:** Treat date gaps as a "reset" for all consecutive streaks.

### 4. Promotion Signal Logic (Strict Evidence)
- **Strength Indicators:** Only list behaviors that appear ≥2 times OR are explicitly marked as "systemic/org-wide."
- **Isolated Examples:** One-off wins that don't show a pattern yet.
- **Underrepresented:** Mention "Strategic" or "Proactive" gaps if they appear <10% of the time in a large dataset (20+ logs).

---

## Output Format (Strict)

# Aggregated Performance Report: [Date Range]

## 1. Dataset Health
- **Valid Entries:** X | **Rejected:** Y
- **Data Gaps:** [Details on largest gaps]
- **Statistical Confidence:** [Low/Med/High] + Rationale

## 2. Metric Totals (Quantified)
- [List all summed metrics here]
- **Cumulative Est. Hours Saved:** [Sum]

## 3. Work & Initiative Distribution
- **Reactive:** X days (X%)
- **Proactive:** X days (X%)
- **Strategic:** X days (X%)
- **Primary Focus:** [Incident Response / Engineering / etc.]

## 4. Promotion-Level Signals
### Strength Indicators (Patterns)
- (List repeated technical/behavioral wins)
### Isolated Notable Wins
- (One-off high-impact events)

## 5. Sustainability & Burnout Scan
- **Avg Energy:** X.X
- **Spikes:** [List high-impact or high-volume spikes]
- **Risk Signals:** [Downward trends or high-load/low-energy overlaps]

## 6. Conclusion & Limitations
- [Short evidence-based summary]
- [List data gaps that limit the analysis]

---
Paste Daily Log Entries Below This Line