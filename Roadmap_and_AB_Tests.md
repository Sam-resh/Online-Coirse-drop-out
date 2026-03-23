# Product Roadmap — FY2025
## LearnOS Course Completion Engine

---

## Strategic Narrative

Three phases over 12 months: **Hook → Engage → Retain**

- **Phase 1 (Q1)**: Establish the habit loop foundation. Low-tech, high-signal features. Ship fast, learn fast.
- **Phase 2 (Q2)**: Personalize the learning path. Use Phase 1 data to feed ML models.
- **Phase 3 (Q3–Q4)**: Scale social and B2B. Expand the moat.

---

## Phase 1: HOOK (Q1 2025 — Jan to Mar)

**Theme**: Give learners a reason to return tomorrow.

| Feature | Owner | Status | Launch Week |
|---------|-------|--------|------------|
| Milestone celebrations (25/50/75/100%) | Design + FE Eng | 🟢 In Progress | Week 4 |
| Smart Resume Engine | Backend + FE | 🟢 In Progress | Week 5 |
| Commitment Contract at enrollment | FE + Growth | 🟡 Design Review | Week 6 |
| Vacation Mode (pause streaks) | FE | ⚪ Not Started | Week 7 |
| Learning Streak System (microservice) | Backend | ⚪ Not Started | Week 10 |
| Streak milestone notifications | Mobile Eng | ⚪ Not Started | Week 11 |

**Q1 Exit Criteria**:
- D7 retention ≥ 24% (from 18% baseline)
- Milestone celebration used by ≥ 70% of eligible learners
- Smart Resume triggered with ≥ 65% click-through to lesson

---

## Phase 2: ENGAGE (Q2 2025 — Apr to Jun)

**Theme**: Meet learners where they are, not where we assume they are.

| Feature | Owner | Status | Launch Week |
|---------|-------|--------|------------|
| Content Modality Switcher (video ↔ text) | Content + FE | ⚪ Planning | W14 |
| Adaptive Daily Goal Setting | DS + FE | ⚪ Planning | W14 |
| Cohort Enrollment (Beta: 5 courses) | Backend + CX | ⚪ Planning | W16 |
| Daily "Pick Up Here" Home Surface | FE + Design | ⚪ Planning | W17 |
| Accountability Buddy Feature | Backend + FE | ⚪ Planning | W18 |
| Cohort Peer Feed | FE + Trust/Safety | ⚪ Planning | W20 |

**Q2 Exit Criteria**:
- Completion rate ≥ 25%
- Cohort learners show > 15pp higher completion vs. solo learners
- Modality switcher adopted by ≥ 20% of mobile learners

---

## Phase 3: RETAIN + SCALE (Q3–Q4 2025 — Jul to Dec)

**Theme**: Make the network smarter and the value undeniable.

| Feature | Owner | Status | Launch Week |
|---------|-------|--------|------------|
| AI Pacing Engine (ML model v1) | DS + Backend | ⚪ Planning | W26 |
| Smart Re-engagement Notifications (ML) | DS + Mobile | ⚪ Planning | W28 |
| B2B Team Cohorts + Manager Dashboard | B2B Squad | ⚪ Planning | W30 |
| Social Proof Feed ("X peers finished Module 3") | FE | ⚪ Planning | W32 |
| Learning Path Recommendations (post-completion) | DS + Content | ⚪ Planning | W36 |
| API for Corporate LMS Integration | Platform | ⚪ Planning | W40 |

**Year Exit Criteria**:
- Course completion rate ≥ 35%
- WCC ≥ 22,000/week
- NPS ≥ 48

---

# A/B Testing Plan
## Course Completion Engine Experiments

---

## Experiment 1: Learning Streak — Placement Test

| Field | Detail |
|-------|--------|
| **Hypothesis** | Showing the streak counter in the course player (not just home) will increase D7 retention by 10pp vs. home-only |
| **Control** | Streak visible on home screen only |
| **Variant A** | Streak visible: home + course player header |
| **Variant B** | Streak visible: home + course player + lesson completion modal |
| **Primary Metric** | D7 learner retention |
| **Secondary Metrics** | Sessions per week, lessons completed per session |
| **Guardrail** | Enrollment rate (must not drop > 3%), app rating |
| **Traffic Allocation** | 33% Control / 33% A / 33% B |
| **Sample Size** | 50,000 new learners per variant |
| **Duration** | 4 weeks (28 days) |
| **Statistical Power** | 80% at 95% confidence |
| **MDE** | 5 percentage points |
| **Analysis Method** | Frequentist, two-tailed t-test on D7 retention |

---

## Experiment 2: Commitment Contract — Placement

| Field | Detail |
|-------|--------|
| **Hypothesis** | Inserting a commitment contract step post-enrollment (before course home) will increase D30 retention by 8pp |
| **Control** | Current enrollment → course home directly |
| **Variant** | Enrollment → commitment step → course home |
| **Primary Metric** | D30 retention |
| **Guardrail** | Enrollment funnel completion rate (must not drop > 5%) |
| **Traffic** | 50/50 split |
| **Sample Size** | 30,000 new enrollees per variant |
| **Duration** | 6 weeks |

---

## Experiment 3: Smart Resume — Trigger Threshold

| Field | Detail |
|-------|--------|
| **Hypothesis** | Triggering Smart Resume after 48h away (vs. 72h) will increase re-activation rate |
| **Control** | Smart Resume triggers at 72h gap |
| **Variant** | Smart Resume triggers at 48h gap |
| **Primary Metric** | Re-activation rate (return within 24h of trigger) |
| **Guardrail** | Notification opt-out rate |
| **Duration** | 3 weeks |

---

## Experiment 4: Cohort vs. Solo Completion

| Field | Detail |
|-------|--------|
| **Hypothesis** | Learners who start in a cohort will complete at 2x the rate of solo learners |
| **Design** | Quasi-experiment: cohort-enrolled vs. self-paced enrolled in same course |
| **Primary Metric** | 90-day course completion rate |
| **Secondary** | NPS at completion, Pro upgrade rate |
| **Duration** | 90 days (one cohort lifecycle) |

---

## Experiment Calendar

| Week | Experiment | Phase |
|------|-----------|-------|
| Week 4–8 | Streak placement (Exp 1) | Phase 1 |
| Week 5–10 | Commitment contract (Exp 2) | Phase 1 |
| Week 8–11 | Smart resume trigger (Exp 3) | Phase 1 |
| Week 16–22 | Cohort vs. solo (Exp 4) | Phase 2 |
| Week 20–26 | Modality switcher impact | Phase 2 |
| Week 28–36 | ML notification timing | Phase 3 |
