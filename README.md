# March Madness Predictor

> Machine learning models that simulate the NCAA Tournament bracket and predict game outcomes using advanced basketball efficiency stats.

## Overview

This project builds and evaluates predictive models for the NCAA Men's Basketball Tournament ("March Madness"). It pulls team efficiency data from [barttorvik.com](https://barttorvik.com), trains models on historical tournament results, and simulates every round of the bracket to produce predicted winners and margins of victory.

The system has been iterated on since 2022, reaching the **94th percentile on ESPN** in 2025 — correctly predicting the champion (Florida) and all four Final Four teams.

## Features

- Round-by-round bracket simulation with predicted win margins
- Multiple model variants tested each year (original, talent-weighted, matchup-focused)
- Exploratory data analysis identifying which team stats correlate with tournament success
- Daily in-season game simulator for tracking model performance during the regular season
- Per-year output CSVs for every round (Round of 64 → Championship)

## Results

| Year | Predicted Champion | Actual Champion | ESPN Percentile |
|------|--------------------|-----------------|-----------------|
| 2022 | Gonzaga | Kansas | 80.4th |
| 2025 | Florida | Florida ✓ | 94.1th |
| 2026 | Duke | TBD | TBD |

**2025 Final Four:** Auburn, Florida, Duke, Houston — all four correct.

## Requirements

- Python 3.8+
- Jupyter Notebook or JupyterLab
- pandas, numpy, scikit-learn, matplotlib, seaborn

Install dependencies:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

## Usage

### 1. Run exploratory data analysis

Open `archive_march_madness/March_Madness_EDA.ipynb` to explore which team stats correlate with tournament performance. Key features identified:

| Stat | Description |
|------|-------------|
| ADJOE | Adjusted Offensive Efficiency |
| ADJDE | Adjusted Defensive Efficiency |
| TOR | Turnover Rate |
| FTRD | Free Throw Rate Differential |
| 3P_D | Opponent 3-Point % |
| 2P_O | 2-Point Field Goal % |

### 2. Simulate the bracket

Open `March_Madness_Final_Simulator.ipynb` and run all cells. The notebook:

1. Loads team stats from barttorvik.com (link in the first cell — update the date range each year)
2. Runs the chosen prediction model for each matchup
3. Writes round-by-round results to `final_model_output/<year>/`

Output files follow the pattern `<date>_roundofXX_winners.csv` and `<date>_roundofXX_margins.csv`.

### 3. Run daily game predictions (in-season)

```bash
python archive_daily_simulator/ncaab_daily_game_simulator.py
```

Predictions are written to `archive_daily_simulator/daily_predictions/`.

## Data Source

All team stats are sourced from [barttorvik.com](https://barttorvik.com). The simulator notebook contains a direct link to the team-tables export page — update the `begin` and `end` date parameters at the start of each tournament cycle.

## Project Structure

```
├── March_Madness_Final_Simulator.ipynb   # Main bracket simulator
├── final_model_output/                   # Per-year simulation results
│   ├── 2025/
│   └── 2026/
├── march_madness_data/                   # Historical data and combined stats
├── archive_march_madness/                # EDA notebook and earlier model iterations
└── archive_daily_simulator/             # In-season daily game predictor
```

## Contributing

PRs and issues welcome. Please open an issue before large changes.

## License

MIT — see [LICENSE](LICENSE)
