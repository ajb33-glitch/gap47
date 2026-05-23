# GAP47 — Japan Earthquake Underinsurance Explorer
### 地震保険格差 · 47 prefectures, one gap.

**Live site → [ajb33-glitch.github.io/gap47](https://ajb33-glitch.github.io/gap47)**

---

## What is GAP47?

Japan has a 84% probability of a major earthquake hitting Tokyo in the next 30 years.  
Yet 37.8% of Tokyo homeowners have no earthquake insurance.

GAP47 maps this mismatch — the **underinsurance gap** — across all 47 Japanese prefectures. It combines official government seismic risk data with insurance penetration rates to answer one question:

> *Where is disaster risk HIGH but insurance coverage LOW — and how big is that gap?*

This is not just a chart. It is a strategic signal for insurers, policymakers, and anyone thinking seriously about Japan's financial resilience to natural disasters.

---

## The Signature Feature — The GAP Score

Each prefecture receives a **GAP score** calculated from two ingredients:

### Ingredient 1 — How likely is an earthquake here?
- **NIED 30-year seismic probability** — Japan's national science agency publishes the probability of a major earthquake hitting each prefecture within 30 years. Think of it like a weather forecast, but for the next three decades.
- **GIROJ risk zone** — The insurance industry's official classification (Zone 1–3). Zone 3 = highest risk. Used to set earthquake insurance premiums across Japan.

### Ingredient 2 — How many households actually have insurance?
- **GIROJ EQ penetration rate** — Of all households that *could* have earthquake insurance, what percentage actually do? Published annually by prefecture.
- **e-Stat household counts** — 2020 Housing Census data to convert percentages into real numbers: actual families left unprotected.

### The formula (in plain English)
```
Risk score  = (30yr earthquake probability × 70%) + (zone severity × 30%)
GAP score   = Risk score − Insurance coverage rate
```

- **Positive score** → risk exceeds coverage → underinsurance gap exists
- **Higher score** → bigger gap → more urgent
- **Negative score** → coverage exceeds risk → relatively well protected

The seismic probability is weighted more heavily (70%) because it is a precise, comparable number. The zone classification adds directional context (30%).

---

## Key Findings

| Rank | Prefecture | EQ Coverage | Seismic Risk (30yr) | Uninsured HH | GAP Score |
|------|------------|-------------|----------------------|--------------|-----------|
| 1 | Tokyo-to 東京都 | 62.2% | 84.1% | ~2,322k | +0.472 |
| 2 | Kanagawa-ken 神奈川県 | 64.0% | 82.3% | ~1,463k | +0.328 |
| 3 | Chiba-ken 千葉県 | 65.4% | 85.0% | ~957k | +0.264 |
| 4 | Saitama-ken 埼玉県 | 65.6% | 82.3% | ~1,021k | +0.257 |
| 5 | Shizuoka-ken 静岡県 | 69.1% | 89.7% | ~585k | +0.161 |

**National average EQ coverage: 73.2%** · **Critical-gap prefectures: 5 of 47** · **Est. exposed households in critical zones: ~6.3M**

All 5 critical-gap prefectures sit in the Kanto region or Pacific coast — exactly where the next major earthquake is most likely to strike.

---

## Data Sources

| Source | What it provided |
|--------|-----------------|
| [NIED — j-shis.bosai.go.jp](https://www.j-shis.bosai.go.jp/) | 30-year seismic exceedance probability by prefecture |
| [GIROJ — giroj.or.jp](https://www.giroj.or.jp/) | EQ insurance penetration rates + risk zone classifications, FY2024 |
| [e-Stat — e-stat.go.jp](https://www.e-stat.go.jp/) | 2020 Housing & Land Survey: household counts by prefecture |
| FSA / GIAJ | P&C premium volume and market penetration trends 2015–2024 |
| Cabinet Office | Municipal earthquake risk classification, 2024 |

All data is sourced from Japanese government or officially-designated industry bodies. No proprietary or estimated data is used in the core GAP score calculation.

---

## Stack

| Layer | Tool | Why |
|-------|------|-----|
| Data collection | e-Stat, NIED, GIROJ (manual) | Official Japanese government open data |
| Processing & ETL | Google Sheets | No-code, auditable, shareable |
| Visualization | Datawrapper | Publication-quality choropleth, embeddable |
| Hosting | GitHub Pages | Free, public URL — live and shareable |

**Philosophy: no-code first.** Every step in this project can be understood and reproduced without writing a single line of code. That was a deliberate choice — domain insight, not engineering complexity, is the point.

---

## Why This Project Exists

GAP47 started as a weekend hobby project — one question on a Saturday morning: *does insurance coverage actually match earthquake risk across Japan's 47 prefectures?* The answer turned out to be more striking than expected.

Anyone can make a chart. The harder thing is understanding *why* the numbers matter, *which* numbers to compare, and *what* the gap means for real people. That's what this project is about.

Japan's next major earthquake is a matter of when, not if. The gap between risk and coverage is not an abstract statistic. It is ~6.3 million households with no financial buffer for an event that government science says is near-certain.

---

*A weekend project · Data: NIED · GIROJ · e-Stat · FSA · Cabinet Office · Built 2025*
