---
title: "NFL Week 10 · 2026 — My Elo Model Picks"
date: 2026-11-10
draft: false
categories:
  - NFL
  - Sports Analytics
tags:
  - Elo
  - NFL Predictions
  - FiveThirtyEight
---

**Picks locked in before the first kickoff.** Results added after Monday Night Football.

---

## What is this?

I built a reimplementation of [FiveThirtyEight's Elo rating system](https://github.com/fivethirtyeight/nfl-elo-game) for NFL games, backtested it against historical data, and now I'm logging my picks every week before kickoff.

The model works by rating every team after every game — going back to 1920 — and computing win probabilities from the rating difference. No injuries, no weather, no gut feel. Just Elo.

**Backtest result** (2021–2025, n=1,420 games): log-loss 0.643, accuracy 63.3%. Beats a home-team-always baseline every single season.

The full code and predictions CSV are in the [nfl_predictor repo](https://github.com/DatWins/nfl_predictor).

---

## Week 10 picks

14 games, Nov 12–16. I'm following the model direction on every game — picking whoever has the higher Elo win probability.

| Game | Date | My pick | Elo % | Spread |
|------|------|---------|-------|--------|
| WAS @ NYG | Thu 11/12 | **NYG** | 53.9% home | NYG -1.5 |
| NE @ DET | Thu 11/13 🌍 | **DET** | 55.7% | DET -3.5 |
| CIN @ ATL | Sun 11/15 | **CIN** | 58.2% home wins, picking upset | ATL -2.5 |
| DEN @ CAR | Sun 11/15 | **DEN** | 65.3% road fav | DEN -6.5 |
| KC @ DAL | Sun 11/15 | **KC** | 54.9% road fav | DAL -1.5 |
| JAX @ CLE | Sun 11/15 | **JAX** | 61.3% road fav | JAX -9.5 |
| MIN @ GB | Sun 11/15 | **GB** | 56.1% home | GB -2.5 |
| TEN @ IND | Sun 11/15 | **TEN** | 26.6% — model's longest shot | IND -6.0 |
| BUF @ MIA | Sun 11/15 | **BUF** | 61.7% road fav | BUF -9.5 |
| NYJ @ NO | Sun 11/15 | **NO** | 69.3% home | NO -4.5 |
| SF @ ARI | Sun 11/15 | **SF** | 64.4% road fav | SF -6.0 |
| LV @ SEA | Sun 11/15 | **SEA** | 90.4% home — model's most confident | SEA -13.5 |
| PIT @ HOU | Sun 11/15 | **PIT** | 28.1% — heavy underdog | HOU -4.5 |
| LAC @ BAL | Mon 11/16 | **BAL** | 61.5% home | BAL -3.5 |

🌍 = international game (Munich), played at neutral site — HFA not applied

**Notable:**
- **TEN and PIT** are the two picks where I'm going against the model's confidence — Elo strongly favors IND and HOU, but I'm logging the model's pick, not my gut
- **SEA at 90.4%** is an unusually strong signal — worth watching whether that rating holds up
- 7 of 14 games involve road favorites, which is rare; the model's Elo ratings are overriding home-field advantage in those matchups

---

## Results

*To be filled in after Monday Night Football, Nov 16.*

| Correct | Wrong | Record |
|---------|-------|--------|
| — | — | —/14 |

---

*Predictions CSV committed to [nfl_predictor/predictions/2026-week10.csv](https://github.com/DatWins/nfl_predictor/blob/main/predictions/2026-week10.csv) before kickoff.*
