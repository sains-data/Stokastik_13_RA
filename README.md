# Markov Chain Parking Lot Occupancy Analysis

## 📋 Project Overview

This project implements a **Markov Chain model** to analyze and predict parking lot occupancy patterns. By analyzing historical parking data, we can determine transition probabilities between different occupancy states and predict future parking availability.

**Group:** Kelompok 13 RA  
**Date:** November 2025

---

## 🎯 Objective

To model parking lot occupancy using Markov Chain theory, enabling:
- Analysis of parking usage patterns
- Prediction of future occupancy states
- Understanding of transition dynamics between different occupancy levels

---

## 📊 State Definition

The parking lot occupancy is divided into 6 discrete states based on the number of occupied spaces:

| State | Occupancy Range | Description |
|-------|-----------------|-------------|
| State 1 | 0 - 10 spaces   | Very Low |
| State 2 | 11 - 20 spaces  | Low |
| State 3 | 21 - 30 spaces  | Medium-Low |
| State 4 | 31 - 40 spaces  | Medium-High |
| State 5 | 41 - 50 spaces  | High |
| State 6 | 51 - 60 spaces  | Very High |

---

## 🔄 Transition Matrix (P)

Based on the analyzed dataset, the transition probability matrix between states is:

| From    | State 3 | State 4 | State 5 |
|---------|--------:|--------:|--------:|
| State 3 |   0.000 |    0.50 |   0.500 |
| State 4 |   0.200 |    0.30 |   0.500 |
| State 5 |   0.125 |    0.75 |   0.125 |

**Interpretation:**
- From **State 3** (21-30 spaces): 50% probability to transition to State 4, 50% to State 5
- From **State 4** (31-40 spaces): 20% to State 3, 30% stays in State 4, 50% to State 5
- From **State 5** (41-50 spaces): 12.5% to State 3, 75% to State 4, 12.5% stays in State 5

---

## 📈 State Transition Diagram

The following diagram visualizes the transitions between states:

<img src="./graf.png" alt="State Transition Diagram" width="600"/>

---

## 🛠️ Implementation

The analysis is implemented in R using:
- **Data processing:** `dplyr`, `tidyr`
- **Visualization:** `ggraph`, `igraph`, `tidyverse`
- **Analysis:** Custom Markov Chain calculations including P² (2-step transitions)

### Key Features:
1. **Data Import & Preprocessing:** Load and clean parking occupancy data
2. **State Classification:** Automatically categorize occupancy into discrete states
3. **Transition Matrix Calculation:** Compute probability of transitions between states
4. **Multi-step Predictions:** Calculate P² for 2-step transition probabilities
5. **Visualization:** Generate state transition diagrams

---

## 📂 Project Structure

```
markov-chain-parking-lot/
│
├── code_R.Rmd              # Main R Markdown analysis file
├── dataset_13_RA.xlsx      # Input dataset
├── graf.png                # State transition diagram
├── README.md               # Project documentation
└── outdate/                # Archive folder
    ├── dataset/            # Previous datasets
    ├── markov.ipynb        # Jupyter notebook version
    └── referensi/          # Reference papers
```

---

## 🚀 Usage

1. Open `code_R.Rmd` in RStudio
2. Install required packages (first code chunk)
3. Load your parking dataset
4. Run all chunks to generate:
   - Transition probability matrix (P)
   - 2-step transition matrix (P²)
   - State transition diagram

---

## 📚 Mathematical Foundation

**Markov Property:** The future state depends only on the current state, not on the sequence of events that preceded it.

**Transition Probability:**
```
P(Xₙ₊₁ = j | Xₙ = i) = pᵢⱼ
```

**n-Step Transition:**
```
P^n = P × P × ... × P (n times)
```

---

## 👥 Contributors

Kelompok 13 RA

---

## 📄 License

This project is part of academic coursework.

---

## 📖 References

See `outdate/referensi/` folder for academic papers on:
- Parking lot occupancy prediction
- Markov Chain applications in traffic systems
- Cooperative multiagent systems for parking