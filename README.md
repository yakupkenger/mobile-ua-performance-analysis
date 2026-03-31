# 📱 Mobile UA Performance Analysis
### A end-to-end User Acquisition case study covering budget allocation, creative strategy, and campaign performance analysis for a mobile puzzle game launch.

---

## 🗂️ Project Overview

This project simulates the responsibilities of a **Performance Marketing Manager** at a mobile gaming company during the first 30 days of a new puzzle game launch. The work covers three core areas:

| Area | Topics Covered |
|------|---------------|
| **Budget Allocation** | Channel mix strategy, iOS/Android split, country tiering, ROAS modelling, 30-day vs 180-day payback windows |
| **Creative Strategy** | Competitive creative analysis, UGC performance diagnosis, new concept development |
| **Campaign Analytics** | Pre-install funnel metrics (CTR, CTI, CVR, CPI), week-over-week trend analysis, performance decline diagnosis |

---

## 🔧 Tools & Methods

- **Microsoft Excel** — Budget modelling, CPI scaling formulas, ROAS calculations, data visualisation
- **Microsoft Word** — Structured analytical write-ups for each question
- **Facebook Ad Library** — Competitive creative research (Last War, Kingshot, Gossip Harbor, Royal Match)
- **Python (pandas, openpyxl)** — Data processing and Excel automation
- **Statistical methods** — Logarithmic regression for D180 ARPU extrapolation, greedy optimisation for budget allocation

---

## 📊 Question 1 — Budget Allocation & Payback Window Modelling

### 1a & 1b — Channel Mix & Geo Strategy
Explained fundamental differences between **Ad Networks**, **DSPs**, and **Social Networks** across ad placements, unique inventory, and campaign types. Proposed iOS/Android split (60/40) and a tiered country allocation framework (Tier 1/2/3).

### 1c — $10M Budget Allocation (30-Day Window)
Built a dynamic Excel model to allocate $10M across 8 networks while maximising total installs under a portfolio ROAS ≥ 100% constraint.

**Key finding:** The CPI scaling formula (linear: +10/15/20% per $25K step for Ad Networks/DSPs/Social) limits the maximum deployable budget to **$5.975M** at 30-day ROAS ≥ 100%. The remaining $4.025M cannot be profitably deployed within a 30-day payback window.

| Network | Budget | Final CPI | Installs | D30 ROAS |
|---------|--------|-----------|----------|----------|
| Unity | $1,375,000 | $15.25 | 90,164 | 52.5% |
| Mintegral | $1,050,000 | $19.20 | 54,687 | 36.5% |
| Liftoff | $1,050,000 | $19.20 | 54,687 | 52.1% |
| Google UAC | $700,000 | $13.80 | 50,725 | 181.2% |
| AppLovin | $775,000 | $25.90 | 29,923 | 154.4% |
| Moloco | $475,000 | $19.50 | 24,359 | 153.8% |
| Facebook | $275,000 | $12.00 | 22,917 | 291.7% |
| TikTok | $275,000 | $12.00 | 22,917 | 125.0% |
| **TOTAL** | **$5,975,000** | — | **350,379** | **100.3%** |

### 1d — Shift to 180-Day Payback Window
Extrapolated D180 ARPU values using logarithmic regression on D1→D90 trend data. Under a 180-day window, the full $10M becomes deployable.

**Key finding:** Extending the payback window unlocks **+87% more installs** (350K → 655K) and shifts budget priority toward Moloco, Facebook, and TikTok — channels with strong long-term ARPU growth that were constrained under the 30-day window.

---

## 🎨 Question 2 — Creative Strategy & IPM Analysis

### 2a — Royal Match Creative Audit
Reviewed active Royal Match creatives on Facebook Ad Library. Identified 10 consistent creative patterns including: narrative rescue hook, frustration hook, near-miss psychology, device variety, and friction-removal copy ("No ADS, FREE, No WiFi needed").

### 2b — Competitive Creative Analysis
Selected and analysed one video ad each from three competitor games:

| Game | Format | Core Hook | Persuasion Mechanic |
|------|--------|-----------|-------------------|
| **Last War** | Split-screen UGC | Skepticism → live rebuttal → failure as payoff | Objection handling through live demonstration |
| **Kingshot** | Talking head + overlay | Mid-game urgency → strategic narration → social proof | Emotional immersion then rational conversion |
| **Gossip Harbor** | Narrative cinematic | Maternal hardship + baby cry | Narrative empathy before gameplay reveal |

### 2c — New Creative Concept: "Time Freeze Choice"
Proposed a new Royal Match creative concept that replaces the traditional fail-hook with an **agency hook**: the game freezes at a critical puzzle moment and shows the viewer two possible futures — one satisfying chain reaction, one cinematic chaos — before asking "Choose your move."

**Psychological triggers:** Curiosity + control, what-if psychology, dual emotional payoff, agency over passivity.

### 2d — UGC IPM Diagnosis
Compared 4 UGC creatives (2 high IPM, 2 low IPM) and identified the core differentiator:

> *High IPM creatives weave the product into an authentic human moment. Low IPM creatives append the product to a constructed scenario.*

| Creative | IPM | Key Strength / Weakness |
|----------|-----|------------------------|
| Gameplay Reaction | ✅ High | Natural couple dynamic, organic CTA, first frame looks like real Reels content |
| Paper Reveal | ✅ High | 19-second clarity, negative contrast anchoring, zero cognitive load |
| Internal Voice Concept | ❌ Low | Clever premise but no conversion moment — husband decides NOT to recommend |
| Stranger Prank Trend | ❌ Low | Tonal mismatch; product appended after unrelated prank setup |

---

## 📈 Question 3 — Campaign Performance Analysis

### 3a — Key Metrics & Weekly Trends
Calculated CTR, CTI, CVR, CPI, CPC, and CPM across 6 weeks of daily data for 8 ad creatives.

**Weekly summary:**

| Week | Impressions | Installs | CTR | CTI | CPI |
|------|-------------|----------|-----|-----|-----|
| W1 Oct 13–19 | 7.7M | 4,166 | 1.04% | 5.18% | $17.20 |
| W2 Oct 20–26 | 8.3M | 4,438 | 1.11% | 4.85% | $17.28 |
| W3 Oct 27–Nov 2 | 8.2M | 4,650 | 0.97% | 5.87% | $16.77 ✅ peak |
| W4 Nov 3–9 | 8.8M | 3,867 | 1.50% | 2.95% | $20.17 ⚠️ |
| W5 Nov 10–16 | 8.2M | 3,646 | 1.77% | 2.51% | $20.10 |
| W6 Nov 17–23 | 7.7M | 3,285 | 1.74% | 2.46% | $21.36 ❌ |

### 3b — Diagnosing the Decline
Identified three root causes based on pre-install metrics alone:

1. **Wrong creative scaled up** — Ad D (CTR 2.54%, CTI 1.38%) likely received excessive budget in W4, generating high click volume from unqualified users
2. **Creative fatigue** — Best performers (Ad F, Ad E) reached audience saturation after W3
3. **Algorithm audience broadening** — As core segments exhausted, the algorithm expanded to less-qualified users while CPM remained stable

> CPM stayed flat across all 6 weeks ($8.91–$9.50), ruling out media cost changes as a driver. The problem is entirely in the creative-audience fit layer.

### 3c — The Single Action
**Pause Ad D. Reallocate its budget to Ad A and Ad H.**

- Ad D: CTR 2.54%, CTI 1.38% — generating clicks without install intent
- Ad A: CTI 9.41% — highest converter in the campaign, severely underscaled
- Ad H: CTI 8.94% — second highest converter, also underscaled

Expected outcome within 5–7 days: CTI returns to 4.5–5.5%, CPI drops to $16–18, weekly installs recover to ~4,200–4,600.

---

## 📁 Repository Structure

```
mobile-ua-performance-analysis/
│
├── README.md                          ← This file
│
├── outputs/
│   └── Dream_Games_Case_Study_FULL.pdf   ← Complete submission (all questions)
│
└── data/
    └── analysis.xlsx                  ← Budget models & campaign analysis
        ├── Question 1c - Calculation
        ├── Question 1d - Calculation
        └── Question 3a - Analysis
```

---

## 💡 Key Takeaways

- **Budget modelling:** CPI inflation curves make it impossible to deploy a large UA budget profitably under a short payback window — the constraint is structural, not a budget size issue
- **Creative diagnosis:** CTR↑ + CTI↓ divergence is the single most reliable pre-install signal of creative-audience mismatch
- **Payback window strategy:** Extending from 30 to 180 days is not just a financial decision — it fundamentally changes which channels and creatives become viable
- **UGC performance:** The gap between high and low IPM UGC is almost never production quality — it is whether the product feels embedded in a real moment or bolted onto a constructed one

---

*This project was completed as part of a marketing internship application case study.*

