# PRD: Course Completion Engine
## LearnOS Platform — Senior PM Specification

---

**Document Owner**: Senior Product Manager — Learner Experience  
**Status**: Draft v1.4 — Ready for Eng Review  
**Last Updated**: March 2025  
**Reviewers**: Engineering Lead, Design Lead, Data Science, Growth PM, Legal  
**Launch Target**: Q1 2025 (Phase 1)  

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Problem Context](#2-problem-context)
3. [User Research & Insights](#3-user-research--insights)
4. [Goals & Success Metrics](#4-goals--success-metrics)
5. [Scope & Non-Goals](#5-scope--non-goals)
6. [Solution Overview](#6-solution-overview)
7. [Detailed Feature Specs](#7-detailed-feature-specs)
8. [Technical Considerations](#8-technical-considerations)
9. [Experiment Plan](#9-experiment-plan)
10. [Rollout Strategy](#10-rollout-strategy)
11. [Risks & Mitigations](#11-risks--mitigations)
12. [Dependencies](#12-dependencies)
13. [Open Questions](#13-open-questions)
14. [Appendix](#14-appendix)

---

## 1. Executive Summary

LearnOS has 4.2M registered learners and growing. However, **88% of enrolled users never complete a course**, severely limiting lifetime value and referral virality. Research reveals this is not primarily a content quality problem — it is a **product engagement and habit formation problem**.

This PRD defines the **Course Completion Engine (CCE)**: a system of interconnected features designed to reduce cognitive dropout triggers, build learning habits, and create social accountability — ultimately driving completion rates from 12% to 35% within 12 months.

**Business Impact**: Achieving a 35% completion rate unlocks estimated **$24M incremental ARR** through improved trial-to-paid conversion (+8pp), reduced annual churn (-12pp), and increased referral volume (+40%).

---

## 2. Problem Context

### 2.1 The Drop-off Cliff

Analysis of 2.1M user sessions shows a consistent pattern:

- **Day 0–1**: 82% of enrolled users complete Lesson 1
- **Day 3**: Retention drops to 34%
- **Day 7**: Only 18% remain active
- **Day 30**: 8% still learning
- **Completion**: 12% finish the full course

The steepest cliff is between **Day 1 and Day 3**, indicating a habit formation failure rather than a content quality problem.

### 2.2 Revenue Impact

| Metric | Current State | Opportunity |
|--------|--------------|-------------|
| Completion rate | 12% | → 35% |
| Completers who upgrade to Pro | 41% | Baseline |
| Non-completers who upgrade | 6% | Baseline |
| Lost revenue (non-completers) | ~$18M ARR | Recoverable |

### 2.3 Why Existing Solutions Failed

Previous attempts at this problem:
- **Email re-engagement campaigns** — 1.2% re-activation rate; users report feeling "nagged"
- **Daily tips push notifications** — turned off by 78% of users within 2 weeks
- **Progress bars on course pages** — minimal behavioral change observed

Root cause: these were **informational** solutions to a **motivational and structural** problem.

---

## 3. User Research & Insights

### 3.1 Research Methodology

| Method | Sample | Timeframe |
|--------|--------|-----------|
| In-depth user interviews | 40 participants | Jan–Feb 2025 |
| Quantitative survey | 1,200 respondents | Feb 2025 |
| Behavioral data analysis | 2.1M sessions | Q4 2024 |
| Diary studies | 15 participants, 2 weeks | Feb 2025 |
| Heuristic UX audit | Full platform | Jan 2025 |

### 3.2 Key User Personas

#### Persona 1: The Aspirer — "Maya"
- **Demographics**: 26, Marketing Coordinator, Bangalore
- **Goal**: Transition to UX Design within 18 months
- **Behavior**: Enrolls in 3–4 courses, completes 0–1
- **Quote**: *"I start with so much motivation, but after 3 days work gets in the way and I never come back."*
- **Pain**: No external accountability, no recovery path after missing days
- **Opportunity**: Commitment contracts, flexible "pause" feature

#### Persona 2: The Upgrader — "Rajan"
- **Demographics**: 35, Software Engineer, Pune
- **Goal**: Learn System Design to get promoted
- **Behavior**: Watches 2 hrs on Day 1, then sporadically watches 5-min clips
- **Quote**: *"The course is 40 hours. I don't have 40 hours. I need 20-minute chunks."*
- **Pain**: Pacing structure doesn't match time availability
- **Opportunity**: Micro-learning mode, adaptive session lengths

#### Persona 3: The Student — "Priya"
- **Demographics**: 21, Engineering Final Year, Chennai
- **Goal**: Learn Python for campus placements
- **Behavior**: Mobile-first, skips long videos, prefers reading
- **Quote**: *"I'd rather read the transcript than watch a 15-minute video."*
- **Pain**: Video-only format on mobile is slow to consume
- **Opportunity**: Modality switcher (video → text → audio)

#### Persona 4: The Manager — "Suresh"
- **Demographics**: 42, VP Engineering, Mumbai
- **Goal**: Upskill his team of 12
- **Behavior**: Buys team accounts but nobody completes courses
- **Quote**: *"I need to show my CFO that this investment is working."*
- **Pain**: No team-level tracking or accountability
- **Opportunity**: B2B cohort learning, manager dashboards

### 3.3 Jobs-to-be-Done

| JTBD | When I... | I want to... | So I can... |
|------|-----------|-------------|-------------|
| J1 | Enroll in a new course | Feel like completion is achievable | Start with confidence, not overwhelm |
| J2 | Miss a day or week | Easily pick up where I left off | Not feel like I've "failed" |
| J3 | Learn something hard | Get just-right difficulty | Stay in flow, not frustration |
| J4 | Make progress | Feel celebrated and seen | Keep going to the next milestone |
| J5 | Learn with a team | See peers' progress | Feel social accountability |

### 3.4 Root Cause Analysis

Using a 5 Whys framework on the primary dropout trigger ("users who don't return after Day 3"):

1. **Why?** → They forgot about the course
2. **Why?** → No trigger to return after initial impulse fades
3. **Why?** → Notifications are turned off; no meaningful re-engagement hook
4. **Why?** → Previous notifications were generic, not personalized or timely
5. **Why?** → Platform lacks behavioral signal to know the right moment and message

**Root cause**: Absence of a behavior-aware re-engagement system, combined with no habit loop structure.

---

## 4. Goals & Success Metrics

### 4.1 OKRs

**Objective**: Make LearnOS the platform where learners actually finish what they start.

| Key Result | Baseline | Target | Timeline |
|-----------|----------|--------|----------|
| KR1: Course completion rate | 12% | 35% | 12 months |
| KR2: Day-7 learner retention | 18% | 42% | 6 months |
| KR3: Weekly active learners | 340K | 900K | 12 months |
| KR4: NPS (completion cohort) | 22 | 55 | 12 months |
| KR5: Trial → Paid conversion | 6% | 14% | 9 months |

### 4.2 North Star Metric

**Weekly Courses Completed** (WCC) — a learner-level metric that captures both retention and depth.

### 4.3 Guardrail Metrics (Do No Harm)

- Enrollment rate must not drop > 5% (feature must not add friction to starting)
- Content creator earnings must not decline (we serve both learners AND instructors)
- Support ticket volume must not increase > 10%

### 4.4 Measurement Plan

| Metric | Source | Frequency | Owner |
|--------|--------|-----------|-------|
| Completion rate | Data Warehouse | Weekly | Analytics |
| Retention curves (D1/D7/D30) | Amplitude | Daily | PM |
| NPS | Delighted | Monthly | CX |
| Conversion rate | Stripe + CRM | Weekly | Growth |
| Feature adoption | Mixpanel | Daily | PM |

---

## 5. Scope & Non-Goals

### 5.1 In Scope (Phase 1 — Q1 2025)

- Learning streak system with commitment contracts
- Cohort-based course start (group enrollment)
- Adaptive daily learning goal setting (5 / 15 / 30 min)
- "Resume" smart landing — returns user to exact drop-off point
- Progress milestone celebrations (25%, 50%, 75%, 100%)

### 5.2 In Scope (Phase 2 — Q2 2025)

- AI pacing engine (adjusts weekly lesson plan based on pace)
- Content modality switcher (video → transcript → audio)
- Personalized "daily lesson" surface on home screen

### 5.3 Out of Scope

- Live/synchronous courses (separate workstream)
- Certificate redesign
- Mobile app redesign (companion project)
- Instructor-facing analytics overhaul
- Payments / pricing changes

---

## 6. Solution Overview

### 6.1 The Habit Loop Framework

Drawing from Nir Eyal's Hook Model and BJ Fogg's Tiny Habits:

```
TRIGGER → ACTION → REWARD → INVESTMENT
   ↓          ↓        ↓          ↓
Daily nudge  1 lesson  Streak    Commit to
(external)   (small)  badge     tomorrow
```

The Course Completion Engine implements all four stages.

### 6.2 Feature Overview

| Feature | Phase | Primary Persona | Expected Impact |
|---------|-------|----------------|----------------|
| Learning Streak | 1 | All | +15pp D7 retention |
| Commitment Contract | 1 | Aspirer | +8pp D30 retention |
| Cohort Start | 1 | Aspirer, Manager | +12pp completion |
| Smart Resume | 1 | All | -40% re-entry friction |
| Milestone Celebrations | 1 | All | +6pp completion |
| AI Pacing Engine | 2 | Upgrader | +10pp completion |
| Modality Switcher | 2 | Student | +7pp engagement |

---

## 7. Detailed Feature Specs

### Feature 1: Learning Streak System

**Description**: A daily learning streak counter that increments each day a user completes at least one lesson. Breaks if user misses a day (with 1 grace day).

**User Story**:  
*As a learner, I want to see my daily learning streak, so that I feel motivated to keep my momentum alive.*

**Acceptance Criteria**:
- [ ] Streak counter visible on home screen and course player header
- [ ] Streak increments when ≥ 1 lesson completed in a calendar day (user's local timezone)
- [ ] Streak shows longest streak achieved alongside current streak
- [ ] "Streak shield" available (1 free grace day per 7-day streak)
- [ ] Streak breaks trigger a specific "restart" flow (not generic notification)
- [ ] Streak milestones (7, 30, 100 days) trigger a full-screen celebration

**Design Notes**:
- Flame icon (🔥) with numeric counter — familiar mental model from Duolingo
- Counter color shifts: gray (0) → amber (1–6) → orange (7+) → gold (30+)
- Avoid: Making streak loss feel punishing. Tone = supportive, not shaming.

**Edge Cases**:
- User in UTC+5:30 must see their local midnight as day boundary
- Streak must be paused (not broken) if user sets "vacation mode"
- Free users can see streak; feature is not paywalled
- Offline lesson completion must sync streak on next connection

---

### Feature 2: Commitment Contract

**Description**: At course enrollment, user selects a weekly time commitment (30 min / 1 hr / 2 hr) and optionally adds an "accountability buddy" email. A soft contract is shown.

**User Story**:  
*As a learner who wants to finish a course, I want to commit to a specific learning schedule at enrollment so that I hold myself accountable and the platform knows how to support me.*

**Acceptance Criteria**:
- [ ] Commitment step inserted in enrollment flow (after payment, before Course Home)
- [ ] Three time options: 30 min/wk, 1 hr/wk, 2 hr/wk
- [ ] Optional: "Who can keep you accountable?" (email input → sends invite)
- [ ] System generates a personalized pacing plan based on commitment level
- [ ] User can update commitment level at any time in settings
- [ ] System sends a "commitment check" notification if user falls 2 weeks behind plan

**Design Notes**:
- Frame as empowering ("You're in control of your pace") not restrictive
- Show estimated completion date based on commitment level
- Accountability buddy email must be double opt-in (buddy confirms)

---

### Feature 3: Cohort-Based Enrollment

**Description**: Users can join a "cohort" — a group of learners starting the same course on the same date. Cohorts have a shared discussion thread and optional peer check-ins.

**User Story**:  
*As a learner, I want to start a course with other people at the same time, so that I feel part of a community and stay accountable.*

**Acceptance Criteria**:
- [ ] "Start with a cohort" option on course enrollment page (alongside "Start at my own pace")
- [ ] Cohort sizes: 10–25 learners. Auto-filled; new cohort opens when full.
- [ ] Cohort has a shared feed: celebrate milestones, post questions, encourage peers
- [ ] Weekly cohort summary email: "4 of your 18 cohort peers completed Module 2 this week"
- [ ] Cohort leaderboard (optional — user can opt out of being listed)
- [ ] Cohort lifetime = course duration + 2 weeks

**Privacy Considerations**:
- Cohort feed is opt-in only
- Users can use a display name different from account name in cohort
- No cohort messaging in free tier (view-only)

---

### Feature 4: Smart Resume Engine

**Description**: When a user returns after > 3 days away, instead of dropping them on the course home page, they land on a personalized "pick up here" screen showing exactly where they left off, why it matters, and a one-tap continue button.

**Acceptance Criteria**:
- [ ] "Smart Resume" surface triggers when user re-enters after ≥ 72 hours away
- [ ] Shows: lesson thumbnail, title, timestamp (e.g., "You stopped at 4:32"), time to finish
- [ ] Shows: motivational context ("You're 68% through Module 3 — almost there!")
- [ ] One primary CTA: "Resume Now"
- [ ] Secondary CTA: "Go to Course Home" (for users who want to navigate freely)
- [ ] A/B test: full-screen modal vs. top-of-page banner

---

### Feature 5: Milestone Celebrations

**Description**: At 25%, 50%, 75%, and 100% course completion, users see a full-screen animated celebration with a shareable badge.

**Acceptance Criteria**:
- [ ] Triggers automatically when user completes the lesson crossing the threshold
- [ ] 100% celebration includes: confetti animation, certificate preview, share options
- [ ] Shareable card generated (PNG) sized for LinkedIn, Twitter, WhatsApp
- [ ] Analytics event fires on each milestone celebration shown and on each share action
- [ ] Users can disable celebrations in accessibility settings

---

## 8. Technical Considerations

### 8.1 Architecture Notes

- **Streak service**: New microservice — stateless, Redis-backed, handles timezone logic
- **Cohort matching**: Batch job runs nightly to group learners by course + enrollment window
- **Smart Resume**: Leverages existing `last_watched_position` table; requires new recommendation layer
- **Pacing engine** (Phase 2): Will require ML model; Data Science team estimates 6-week build

### 8.2 API Contracts (Draft)

```
GET /api/v2/learner/{id}/streak
Response: { current_streak: int, longest_streak: int, last_active_date: ISO8601, shield_available: bool }

POST /api/v2/enrollment/{id}/commitment
Body: { weekly_minutes: int, buddy_email: string | null }
Response: { pacing_plan: PacingPlan, estimated_completion_date: ISO8601 }

GET /api/v2/learner/{id}/resume
Response: { course_id: string, lesson_id: string, position_seconds: int, completion_pct: float }
```

### 8.3 Data & Privacy

- All streak and cohort data stored in GDPR-compliant data store
- Accountability buddy emails require double opt-in before storage
- Cohort data retained for 90 days post-cohort end
- No PII shared with cohort members (only display names)

---

## 9. Experiment Plan

### Experiment 1: Learning Streak vs. Control

| | Details |
|-|---------|
| **Hypothesis** | Learners with streak tracking active will have 15pp higher D7 retention than control |
| **Control** | Current experience (no streak) |
| **Variant A** | Streak counter — home screen only |
| **Variant B** | Streak counter — home + course player |
| **Primary Metric** | D7 retention |
| **Guardrail** | Enrollment rate (must not drop > 3%) |
| **Sample Size** | 50,000 users per variant |
| **Duration** | 4 weeks |
| **Confidence Level** | 95% |

### Experiment 2: Commitment Contract Placement

| | Details |
|-|---------|
| **Hypothesis** | Adding commitment contract post-enrollment will improve D30 retention by 8pp |
| **Control** | No commitment step |
| **Variant** | Commitment step at enrollment |
| **Primary Metric** | D30 retention |
| **Guardrail** | Enrollment completion rate (funnel must not drop > 5%) |
| **Sample Size** | 30,000 users per variant |
| **Duration** | 6 weeks |

---

## 10. Rollout Strategy

### Phase 1: Internal Alpha (Week 1–2)
- All features live for LearnOS employees (n=400)
- Focus: Bug identification, edge case discovery

### Phase 2: Closed Beta (Week 3–6)
- Streak + Smart Resume to 5% of new learners in India (primary market)
- Daily monitoring of guardrail metrics
- Qualitative interviews with 10 beta users

### Phase 3: Gradual Rollout (Week 7–12)
- 5% → 25% → 50% → 100% over 6 weeks
- Feature flag control via LaunchDarkly
- Rollback trigger: D1 enrollment rate drops > 5% in 48-hour window

---

## 11. Risks & Mitigations

| Risk | Probability | Impact | Mitigation |
|------|------------|--------|-----------|
| Streak causes anxiety / negative emotion | Medium | High | Tone testing in UX; "vacation mode" bypass; opt-out |
| Cohort feature slows enrollment (too much friction) | Medium | High | A/B test with control; monitor funnel daily |
| Accountability buddy emails feel spam-like | Low | Medium | Double opt-in; clear from address; easy unsubscribe |
| Streak data loss due to service outage | Low | High | Redis replication; manual recovery SLA in runbook |
| Cohort groups become toxic/negative | Low | High | Community guidelines; report + mute tools; moderation queue |

---

## 12. Dependencies

| Dependency | Team | Required For | ETA |
|-----------|------|-------------|-----|
| Streak microservice | Backend (Arjun's team) | Feature 1 | Week 4 |
| Timezone-aware event system | Platform | Feature 1 | Week 3 |
| Cohort DB schema | Data Engineering | Feature 3 | Week 5 |
| Celebration animation library | Design System | Feature 5 | Week 6 |
| ML pipeline for pacing | Data Science | Phase 2 | Week 16 |

---

## 13. Open Questions

| # | Question | Owner | Due |
|---|---------|-------|-----|
| Q1 | Should streak include weekend days? Or weekday-only? | PM + Research | Week 2 |
| Q2 | What is the cohort max size for good social dynamics? (Pilot: 15) | Research | Week 4 |
| Q3 | Do we allow instructors to opt their course out of cohort feature? | Policy + Legal | Week 3 |
| Q4 | Should the streak shield be a paid feature or free? | Growth PM | Week 2 |
| Q5 | What does the pacing engine do when a user is 4 weeks behind? Reset or catch-up plan? | PM + DS | Week 8 |

---

## 14. Appendix

### A. Competitive Benchmarks

| Platform | Completion Rate | Key Retention Mechanic |
|---------|----------------|----------------------|
| Duolingo | 40%+ (daily active) | Streaks, leagues, lives |
| MasterClass | 22% | Cinematic content quality |
| Coursera (with cert) | 30% | Certificate motivation, deadlines |
| Udemy | 6–10% | Price anchoring only |
| Brilliant.org | 35% | Daily problems, habit loop |
| **LearnOS (current)** | **12%** | Email campaigns only |

### B. Opportunity Solution Tree

```
Goal: Increase completion rate to 35%

├── Opportunity 1: Build habit loop
│   ├── Solution: Streaks
│   ├── Solution: Daily goals
│   └── Solution: Calendar integration
│
├── Opportunity 2: Reduce re-entry friction
│   ├── Solution: Smart resume
│   └── Solution: "5-min lesson" daily surface
│
├── Opportunity 3: Social accountability
│   ├── Solution: Cohort learning
│   ├── Solution: Accountability buddy
│   └── Solution: Peer progress feed
│
└── Opportunity 4: Personalized pacing
    ├── Solution: AI pacing engine
    └── Solution: Modality switcher
```

### C. RICE Score Summary

| Feature | Reach | Impact | Confidence | Effort | RICE Score |
|---------|-------|--------|-----------|--------|-----------|
| Streak System | 9 | 9 | 85% | 3 | 22.95 |
| Smart Resume | 10 | 7 | 90% | 2 | 31.5 |
| Milestone Celebrations | 10 | 6 | 90% | 1 | 54.0 |
| Commitment Contract | 8 | 8 | 75% | 2 | 24.0 |
| Cohort Learning | 6 | 9 | 70% | 5 | 7.56 |
| AI Pacing Engine | 8 | 9 | 60% | 8 | 5.4 |

---

*Document version: 1.4 | This PRD is a living document. All major changes require sign-off from Eng Lead, Design Lead, and VP Product.*
