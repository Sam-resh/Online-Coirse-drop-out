# 📚 LearnOS — Reducing Course Dropout Rates
### A FAANG-Level Product Management Case Study

> **Product**: LearnOS — Online Learning Platform  
> **Role**: Senior Product Manager  
> **Problem**: 88% of users who enroll in courses never complete them  
> **Goal**: Increase course completion rate from 12% → 35% in 12 months  

---

## 🗂️ Project Index

| Document | Description | Status |
|----------|-------------|--------|
| [PRD — Course Completion Engine](./docs/PRD_Course_Completion_Engine.md) | Full product requirements document | ✅ Complete |
| [User Research Report](./docs/User_Research_Report.md) | 40 interviews + survey synthesis | ✅ Complete |
| [Competitive Analysis](./docs/Competitive_Analysis.md) | Coursera, Udemy, Duolingo, MasterClass | ✅ Complete |
| [RICE Prioritization](./docs/RICE_Prioritization.md) | Feature scoring & ranking | ✅ Complete |
| [Metrics & OKR Framework](./docs/Metrics_OKR_Framework.md) | North star, leading/lagging indicators | ✅ Complete |
| [Product Roadmap](./docs/Roadmap.md) | 3-phase, 12-month plan | ✅ Complete |
| [A/B Testing Plan](./docs/AB_Testing_Plan.md) | Experiment design & hypothesis | ✅ Complete |
| [GTM Strategy](./docs/GTM_Strategy.md) | Go-to-market & launch plan | ✅ Complete |

---

## 🧭 Problem Statement

**"LearnOS has 4.2M registered learners. 91% complete less than 30% of any course they start. The platform earns $0 from incomplete learners who churn before upgrading to Pro. Despite strong top-of-funnel acquisition, retention collapses after Day 3."**

### Why This Matters

- 📉 Average completion rate across the platform: **12%**
- 💸 Revenue lost to early churn: estimated **$18M ARR**
- 😤 Top complaint in user reviews: *"I always start but never finish"*
- 🔁 Referral rate 4x higher among course completers vs. non-completers

---

## 🔍 Research Summary

### Method
- **40 user interviews** (20 dropouts, 10 completers, 10 churned-paid)
- **1,200-person survey** across 6 user segments
- **Behavioral data analysis** on 2.1M sessions
- **Heuristic audit** of onboarding and course UX

### Top 5 Drop-off Root Causes

| # | Root Cause | % Users Affected |
|---|-----------|-----------------|
| 1 | No clear learning goal / accountability | 67% |
| 2 | Course pacing feels too slow or too fast | 54% |
| 3 | No habit-forming trigger after day 3 | 48% |
| 4 | Content format mismatch (video vs. text) | 39% |
| 5 | Life events interrupting momentum | 35% |

---

## 🎯 Strategic Bets (Solutions)

### Phase 1 — Hook (Q1): Build the Habit Loop
- **Learning streaks + commitment contracts** (like Duolingo)
- **Cohort-based learning** — start with a group, not alone
- **Adaptive daily goals** — 10 min/day vs. 1 hr/day options

### Phase 2 — Engage (Q2): Personalize the Path
- **AI-powered pacing engine** — auto-adjusts difficulty curve
- **Modality switcher** — same content as video, text, or audio
- **Progress checkpoints** — milestone celebrations at 25%, 50%, 75%

### Phase 3 — Retain (Q3–Q4): Re-engage & Sustain
- **Smart re-engagement notifications** (ML-driven timing)
- **Resume engine** — context-aware "pick up where you left off"
- **Social proof feed** — see peers completing modules in real time

---

## 📊 Success Metrics

| Metric | Baseline | Target (12 mo) |
|--------|----------|----------------|
| Course completion rate | 12% | 35% |
| Day-7 retention | 18% | 42% |
| Day-30 retention | 8% | 24% |
| NPS score | 22 | 48 |
| Trial → Paid conversion | 6% | 14% |
| Avg sessions per week | 1.2 | 3.8 |

---

## 🗓️ Roadmap Overview

```
Q1 2025 ─────────── Q2 2025 ─────────── Q3 2025 ─────────── Q4 2025
│                   │                   │                   │
│ PHASE 1: HOOK     │ PHASE 2: ENGAGE   │ PHASE 3: RETAIN   │ SCALE
│                   │                   │                   │
│ ✦ Streak system   │ ✦ AI pacing       │ ✦ Smart nudges    │ ✦ B2B cohorts
│ ✦ Cohort launch   │ ✦ Modality switch │ ✦ Resume engine   │ ✦ API partners
│ ✦ Commit goals    │ ✦ Milestones      │ ✦ Social proof    │ ✦ White-label
```

---

## 🧩 Key Personas

| Persona | Description | Primary Pain |
|---------|-------------|-------------|
| 🎓 **The Aspirer** | 24–32, wants career change, low discipline | No accountability |
| 💼 **The Upgrader** | 30–40, upskilling at job, time-poor | Pacing too slow |
| 🧑‍🎓 **The Student** | 18–24, cost-sensitive, heavy mobile user | Content format |
| 👩‍💼 **The Manager** | 35–50, buying for team, ROI-focused | No team features |

---

## 📐 How to Use This Repository

```bash
# Clone the repo
git clone https://github.com/your-username/learnos-pm-case-study.git

# Navigate to docs
cd learnos-pm-case-study/docs

# Read the PRD first
open PRD_Course_Completion_Engine.md
```

---

## 🏗️ Project Structure

```
learnos-pm-case-study/
├── README.md                        ← You are here
├── docs/
│   ├── PRD_Course_Completion_Engine.md
│   ├── User_Research_Report.md
│   ├── Competitive_Analysis.md
│   ├── RICE_Prioritization.md
│   ├── Metrics_OKR_Framework.md
│   ├── Roadmap.md
│   ├── AB_Testing_Plan.md
│   └── GTM_Strategy.md
├── assets/
│   ├── user-journey-map.png
│   ├── opportunity-solution-tree.png
│   └── funnel-analysis.png
└── templates/
    ├── interview-guide.md
    └── experiment-brief.md
```

---

## 👤 About This Case Study

This project demonstrates FAANG-level PM thinking across:
- Structured problem decomposition
- Mixed-methods user research
- Data-informed prioritization
- Outcome-oriented roadmapping
- Rigorous experiment design
- Cross-functional stakeholder management

**Built to showcase PM depth for Senior/Staff PM roles at Google, Meta, Amazon, Apple, and high-growth startups.**

---

*Last updated: March 2025 | Product Manager: [Your Name]*
