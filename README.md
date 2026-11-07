# Does Medium-Term Price Momentum Predict Future Equity Returns?

## Write-up 

The full report is here: [Report/medium_momentum_indicator_write_up.pdf](https://github.com/henryyu849/Medium-Momentum-Strategy/blob/main/Report/medium_momentum_indicator_write_up.pdf)

## Introduction 

I will aim to test whether the null hypothesis that the indicator of medium-term price momentum is not significant is true or not - I will use a method similar to Jegadeesh and Titamn, who tested on the NYSE and AMEX from 1965-1989, where I will use overlapping cohorts from each month in my portfolio. From this method, I hope to ues a Newey-West t-test and Wilcoxon signed-rank test to test whether the mean and median of my returns is significant from the null of 0. 

Within this project, I will allow myself to use AI as an assisting tool, where I will use it to help with syntax or presentation/formatting, however I will not use it to generate its own code for complex functions - I have only generated code (which I have cited) in instances where it was out of my knowledge and also was not too relevant to the main code. 


## Project structure
- `1 - Data_Collection.ipynb`: downloads prices from yfinance (from 2010)
- `2 - Data_Clean.ipynb`: cleans data and builds monthly returns
- `3 - Momentum_Signal.ipynb`: builds momentum signal
- `4 - Portfolio Sort Analysis.ipynb`: builds the portfolio and strategy functions
- `5 - Statistical Testing.ipynb`: tests results of my portfolio return using statistics
- `6 - Performance Testing.ipynb`: tests other performance metrics and shows a summarised graph of returns. 

## Method
- Signal: cumulative return from t-12 to t-2 (skipping the most recent month)
- Portfolios: equal-weighted top decile minus bottom decile
- Overlapping cohorts for K = 1, 3, 6, 12
- Tests: Newey-West (K-1 lags), Wilcoxon signed-rank

## How to run
1. Install requirements: `pip install -r requirements.txt`
2. Run the notebooks in order (1, 2, then 3)

## Requirements
Python 3.x, pandas, numpy, yfinance, statsmodels, scipy, matplotlib

## Limitations
- Survivorship bias (yfinance only includes currently listed stocks)
- Returns are gross of transaction costs
- No factor adjustment; short sample (about 15 years)

## Author
Henry
