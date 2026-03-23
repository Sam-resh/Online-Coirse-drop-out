# User Research Report
## LearnOS — Course Dropout Investigation
### January–February 2025

---

**Research Lead**: Senior PM — Learner Experience  
**Collaborators**: UX Research, Data Science, CX Team  
**Status**: Final — Approved for Product Use  

---

## Executive Summary

We conducted a 6-week mixed-methods research sprint to understand *why* LearnOS learners enroll in courses but rarely complete them. Across 40 interviews, a 1,200-person survey, 15 diary studies, and analysis of 2.1M behavioral sessions, one finding was universal:

> **Dropout is not a motivation problem at enrollment — it is a habit and accountability problem in the first 7 days.**

Learners arrive highly motivated. The product fails to convert that initial motivation into a sustainable habit before life disrupts the pattern.

---

## Research Questions

1. At what point do learners drop off, and why?
2. What mental models do learners have about "success" in online learning?
3. What do completers do differently from non-completers?
4. What product interventions would learners welcome vs. reject?

---

## Methodology

### 1. In-Depth User Interviews (n=40)

- **20 dropouts**: Enrolled in ≥ 2 courses, completed 0
- **10 completers**: Completed ≥ 2 courses in past 12 months
- **10 churned-paid**: Were Pro subscribers, cancelled within 90 days
- Duration: 45–60 minutes via Zoom
- Conducted in English, Hindi, Tamil (with interpreter)

### 2. Quantitative Survey (n=1,200)

- Distributed via in-app prompt (30 days after enrollment, < 50% complete)
- Screened for: enrolled learners who stopped at least once
- Collected: demographics, motivation, barriers, product feedback

### 3. Diary Studies (n=15)

- 15 self-selected participants tracked their learning for 14 days
- Daily voice memo: "Did I learn today? Why/why not?"
- Provided rich texture to the quantitative patterns

### 4. Behavioral Data Analysis

- 2.1M sessions analyzed from Q4 2024
- Cohort retention curves by: course category, enrollment source, device, time-of-day
- Drop-off heatmaps within individual lessons

---

## Key Findings

### Finding 1: The Day 3 Cliff

Retention data shows a universal "Day 3 cliff" — the steepest retention drop across all segments:

| Day | Active Learner % |
|-----|-----------------|
| Day 0 | 100% |
| Day 1 | 82% |
| Day 3 | 34% |
| Day 7 | 18% |
| Day 14 | 12% |
| Day 30 | 8% |
| Day 90 | 5% |

**Interpretation**: Day 1 excitement exists. By Day 3, the external trigger (the reason you enrolled) has faded, and no internal trigger has formed yet.

**Diary study quote**: *"Monday I was fired up. Tuesday I did a lesson. Wednesday my boss called a 3pm meeting and by Thursday I forgot I even started the course."* — Rajan, 35, Software Engineer

---

### Finding 2: Learners Don't Have a "Place" for Learning

When asked "Where does online learning fit in your day?", 71% of dropouts said they had no fixed time or ritual for it. Compare with completers:

| | Dropouts | Completers |
|-|---------|-----------|
| Fixed daily learning time | 14% | 78% |
| Associated with a ritual (coffee, commute) | 9% | 64% |
| Set weekly goals in advance | 11% | 72% |

**Implication**: The product needs to help learners build a time-slot — not just remind them to return.

---

### Finding 3: Missing Days Feels Like Failure

Qualitative finding: the emotional response to missing a day is disproportionately negative. Learners don't say "I'll catch up tomorrow" — they say "I've ruined it."

Survey: *"When you stopped completing lessons, what best describes your mindset?"*
- "I'll pick it back up soon" — 31%
- "I lost my momentum / messed up my streak" — 44%
- "I wasn't enjoying it anyway" — 17%
- "Life got in the way, not my fault" — 8%

**Implication**: The product must make recovery emotionally safe. Missing one day must not feel like course failure.

---

### Finding 4: Format Mismatch is Underestimated

The platform is 94% video content. But:
- 39% of users prefer reading to watching (survey)
- 58% of mobile learners report they "can't always have audio on"
- Diary study: learners on commutes want audio; learners at desks want text; learners in evenings want video

**Implication**: Same content in multiple modalities would serve 40% of learners who are currently underserved.

---

### Finding 5: Social Learning is Latent Demand

Most learners don't know cohort learning exists anywhere on LearnOS. But when shown a concept mock:
- 74% said they'd prefer to start a course with a cohort
- 68% said knowing others are at the same point would motivate them
- 51% said they'd feel guilty dropping out if peers were watching progress

**Implication**: Social accountability is a high-leverage, low-built feature.

---

### Finding 6: Completers Use 3 Behaviors Dropouts Don't

Behavioral data + interview analysis revealed 3 distinguishing behaviors of completers:

1. **They start within 24 hours of enrollment** (vs. dropouts who start 3+ days later)
2. **They watch at least 3 lessons in the first session** (vs. dropouts who watch 1 and leave)
3. **They continue despite a gap** — they have a re-entry pattern

**Product implication**: Interventions should focus on (a) first-session depth, (b) early habit formation, and (c) graceful recovery from gaps.

---

## Segment Analysis

### By Course Category

| Category | Avg Completion Rate | Primary Drop-off Reason |
|---------|-------------------|------------------------|
| Programming | 18% | Pacing too slow for experts |
| Design | 14% | Format mismatch (video-heavy) |
| Business | 9% | No clear career ROI framing |
| Personal Dev | 6% | Motivation fluctuates most |
| Data Science | 22% | Highest commitment intent at start |

### By Device

| Primary Device | D7 Retention |
|---------------|-------------|
| Desktop | 24% |
| Mobile | 12% |
| Tablet | 19% |

Mobile learners drop off 2x faster — combination of shorter sessions, interruptions, and format mismatch.

### By Enrollment Source

| Source | D30 Retention |
|--------|--------------|
| Organic search | 11% |
| Social ad | 6% |
| Word of mouth | 19% |
| Employer-paid | 28% |
| Email campaign | 8% |

**Key insight**: Employer-paid and word-of-mouth have the highest retention — external accountability already exists for these users.

---

## What Learners Want (Survey)

*"Which of these would most help you complete a course?"* (multi-select)

| Feature | % Selected |
|---------|-----------|
| Bite-sized daily lessons (10–15 min) | 68% |
| Reminders timed to my schedule | 61% |
| Learning streak / progress tracker | 57% |
| A group to learn with | 54% |
| Reading/audio alternative to video | 51% |
| Certificate with real employer value | 48% |
| Accountability partner | 42% |
| Pause course without losing progress | 39% |

---

## What to NOT Build

Equally important — interventions learners rejected:

- ❌ **Gamified points/badges for every action**: "Feels childish and hollow"
- ❌ **Daily guilt-trip emails**: "I already get too many emails from you"
- ❌ **Mandatory live sessions**: "The whole point is flexibility"
- ❌ **Visible peer comparison leaderboards**: "I don't want to compete, I want to learn"

---

## Interview Highlights

> *"I've started the Python course 3 times. Not because it's bad. I just stop and when I come back I don't know where to restart."*  
> — Priya, 21, Engineering student

> *"If there were 10 of us starting on the same Monday, I would not drop out. Social pressure works on me."*  
> — Meera, 29, Content Creator

> *"I watch the first lesson, feel great, close the app. That's the problem. There's nothing pulling me back tomorrow."*  
> — Vikram, 33, Product Manager

> *"5 minutes a day consistently beats 2 hours once a week for me. But the platform is built for the 2-hour person."*  
> — Ananya, 26, Teacher

---

## Recommendations for Product

Based on this research, the following areas have highest evidence strength:

| Recommendation | Evidence Strength | Effort | Priority |
|---------------|------------------|--------|----------|
| Build learning streaks | Very High | Medium | P0 |
| Smart resume / recovery flow | Very High | Low | P0 |
| Cohort-based enrollment | High | High | P1 |
| Modality switcher | High | Medium | P1 |
| Commitment contract at enrollment | High | Low | P0 |
| 10-minute daily lesson surface | Medium | High | P2 |
| Accountability buddy | Medium | Low | P1 |

---

## Limitations

- Sample skewed toward India (72% of interviewees) — findings may not fully generalize to US/EU learners
- Completers self-selected for diary study — possible motivation bias
- Behavioral data from Q4 (holiday period) may show anomalous patterns

---

*Research conducted January–February 2025. Full interview transcripts and survey data available in the Research Repository (access-restricted). Contact: ux-research@learnos.com*
