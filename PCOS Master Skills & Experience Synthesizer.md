# Prompt Name: PCOS Master Skills & Experience Synthesizer

Author: Scott M
Version: 1.0
Last Updated: 2026-02-11

---

## GOAL

Aggregate structured outputs from the Personal Career Operating System (PCOS) to produce a polished, ATS-friendly **Master Skills & Experience Summary**:

1. Pull evidence from:
   - `daily_logs.md`
   - `aggregated_activity_summary.md`
   - `promotion_assessment.md`
   - `burnout_trends.md`
   - Optional: `sustainability_integrator.md` for growth/sustainability alignment insights
2. Extract measurable achievements, repeated patterns of success, energy/workload insights, and promotion-ready signals.
3. Generate a Top 10 Skills Matrix, gap analysis, role-tagged bullets, and LinkedIn/recruiter-ready summaries.
4. Maintain full factual accuracy — **no invented experience**.
5. Format output in markdown exactly like the **Master Skills & Experience Summary** prompt.

---

## AUDIENCE

Professionals leveraging PCOS outputs to create resumes, LinkedIn profiles, interview prep material, and career tracking documents.

---

## INPUTS

- User Name: [USER NAME] 
- Target Role / Industry: [USER JOB GOAL] 
- PCOS File Snapshots (paste content or links): 
  - `daily_logs.md` 
  - `aggregated_activity_summary.md` 
  - `promotion_assessment.md` 
  - `burnout_trends.md` 
  - Optional: `sustainability_integrator.md` 
- Optional: Flag for interview prep mode (“interview style”, “prep mode”) 

---

## PROCESSING RULES

1. **Evidence Extraction**
   - Identify repeated accomplishments, key skills, tools used, and measurable outcomes.
   - Pull promotion-ready signals from `promotion_assessment.md`.
   - Pull energy trends, risk mitigation, and sustainability patterns from `burnout_trends.md`.
   - Pull repeated or high-impact tasks from `daily_logs.md` and `aggregated_activity_summary.md`.

2. **Skill Mapping**
   - Generate Top 10 Skills Matrix:
     - Map PCOS evidence to each skill
     - Level: Expert / Strong / Partial / No
     - Include STAR proof / note and ATS keywords

3. **Gap Analysis**
   - Highlight top 3–4 skills with Partial/No evidence.
   - Suggest realistic improvement/proof actions.

4. **Role-Tagged Bullet Extraction**
   - Create bullets grouped by relevance to target role.
   - Include metrics, dates, and company/role attribution.

5. **LinkedIn & Recruiter Prep**
   - Generate 1400-character LinkedIn summary using extracted achievements and skills.
   - Generate 3-line recruiter email template.
   - Optional: Interview prep addendum with top 8 anticipated questions + STAR answers.

6. **Versioning & Changelog**
   - Assign patch version, timestamp, and changelog entry.
   - Record PCOS sources used for this iteration.

---

## OUTPUT FORMAT

- Follow **Master Skills & Experience Summary** markdown exactly.
- Include:
  - Professional Overview 
  - Top 10 Skills Matrix 
  - Skill Gap Action Plan 
  - Core Expertise Areas – Role-Tagged 
  - Early Career Highlights 
  - Technical Competencies 
  - Education / Certifications / Clearance 
  - LinkedIn Summary 
  - Recruiter Email Template 
  - Optional Interview Prep Addendum 
  - FUN SCI-FI CLOSE (non-inspirational quote) 
- At end, append a **PCOS Evidence Summary** listing which PCOS files and sections contributed to each skill, bullet, or insight.

---

## RECOMMENDED AI ENGINES

1. GPT-5 – best reasoning and synthesis 
2. Claude Opus 4 – structured markdown extraction 
3. Gemini Advanced – evidence integration 
4. GPT-4-class – fallback 

---

## RULES

- **Do not invent achievements or experience**. 
- Always cite source PCOS file for extracted evidence. 
- Prioritize ATS-friendly phrasing. 
- Maintain professional tone, lightly geeky if desired. 
- Patch versioning and changelog required. 
- Include date & time of synthesis. 

---

## EXAMPLE END-OF-FILE PCOS EVIDENCE SUMMARY

Append something like this at the end of your output:

## PCOS Evidence Summary
- Top Skill #1: Expert – derived from aggregated_activity_summary.md (Project Alpha, Q1-Q2 2026) + promotion_assessment.md (Strategic Initiative metrics)
- Top Skill #2: Strong – daily_logs.md entries from Jan–Mar 2026; sustainability_integrator.md alignment notes
- STAR Proof for Bullet #3: burnout_trends.md trend snapshot; aggregated_activity_summary.md repeated accomplishment
- Gap Skills: Skill #5, Skill #7 – Partial evidence, plan suggested