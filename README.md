# Counterparty Credit Risk Exposure Simulation (IMM-Style Framework)

This repository documents the design and methodology of a Monte Carlo–based counterparty credit risk (CCR) simulation framework, developed in the style of an Internal Models Method (IMM) engine under Basel III/IV.

The project focuses on modeling and simulating exposure profiles for portfolios consisting of corporate bonds and plain-vanilla interest rate swaps, with an emphasis on conceptual soundness, numerical stability, and regulatory alignment rather than production-ready code.

## Project Overview

The framework:
- Models risk-free interest rates using the one-factor Hull–White short-rate model
- Models credit spread dynamics via geometric Brownian motion (GBM)
- Simulates joint risk-factor paths
- Revalues instruments along each path to compute portfolio mark-to-market
- Constructs Expected Exposure (EE) and Potential Future Exposure (PFE) profiles
- Aggregates exposure profiles into Credit Valuation Adjustment (CVA)
- Incorporates historical stress scenarios (e.g. 2008, 2020)
- Emphasizes model risk management principles consistent with SR 11-7

## Current Status

- Core modeling framework and mathematical pipeline are fully specified and documented
- Data sourcing and preprocessing logic is defined (WRDS + SQL pipelines)
- Monte Carlo workflow and exposure aggregation methodology are complete
- Python implementation is partially exploratory and not yet consolidated into a single clean codebase

This repository currently serves as a **research and design reference**, with future plans to:
- Consolidate Python simulations into modular scripts
- Add reproducible examples for EE, PFE, and CVA calculations
- Extend the framework to multiple counterparties and netting sets

## Contents

- `paper/`  
  LaTeX source files for the accompanying research paper, including the main manuscript, bibliography, and figures used in the final results.

- `analysis/` *(in progress)*  
  Research notebooks and exploratory scripts used for volatility modeling, regression analysis, implied vs realized volatility comparisons, and trading signal evaluation.  
   
  These notebooks reflect iterative research workflows and will be progressively cleaned, modularized, and documented.

- `data/` *(to be organized)*  
  Market data sourced primarily from Bloomberg and WRDS, including equity prices, options data, implied volatility surfaces, and macro variables.  
   
  The data has been cleaned and filtered for analysis, but it is not yet fully standardized across assets and time periods. Further organization and metadata documentation are planned.

## Disclaimer

This project is for academic and research purposes only and is not intended for production or trading use.
