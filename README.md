# Electrolyser Scheduling and Optimisation

## Overview

This project looks at how the operating schedule of an electrolyser can be changed in response to UK electricity prices and grid carbon intensity.

Instead of running the electrolyser evenly throughout the day, I modelled different scheduling strategies to see how shifting when electricity is used could reduce both the cost and carbon emissions of hydrogen production.

## Aim

To investigate how electrolyser scheduling can be optimised to reduce electricity cost and carbon emissions while still meeting a required hydrogen production target.

## Method

UK electricity price and carbon intensity data from 22 July to 28 July 2026 were collected and processed in Python. DuckDB and SQL queries were used within Python to store, combine and analyse the data, while PuLP was used to build the optimisation models.

I compared an evenly distributed baseline schedule against several different operating strategies:

- Cost-minimising – prioritises periods with lower electricity prices
- Actual-carbon – prioritises periods with lower actual grid carbon intensity
- Forecast-carbon – schedules operation using forecast carbon intensity
- Balanced – considers both electricity cost and carbon emissions

Each strategy still has to meet the required daily hydrogen production target, so the main difference is when the electrolyser operates.

Sensitivity analysis was also carried out to look at how changing some of the model assumptions affects the results.

## Key Results

| Strategy | Cost Saving (%) | Emissions Saving (%) |
|---|---:|---:|
| Cost-minimising | 36.1 | 7.3 |
| Balanced | 35.2 | 11.5 |
| Actual-carbon | 22.1 | 17.4 |
| Forecast-carbon | 13.0 | 16.1 |

The different strategies show the trade-off between reducing electricity cost and reducing emissions.

The cost-minimising strategy produced the largest cost saving, while the carbon-focused strategies achieved larger emissions reductions. The balanced strategy was able to achieve substantial savings in both.

The forecast-carbon schedule also achieved around 93% of the emissions saving of the actual-carbon strategy, showing that useful scheduling decisions can still be made without knowing future carbon intensity perfectly.

## Sensitivity Analysis

Electrolyser electricity consumption was tested at:

- 45 kWh/kg H₂
- 50 kWh/kg H₂
- 55 kWh/kg H₂

I also looked at how changing the value placed on carbon emissions affected the balance between cost and emissions in the optimisation.

## Tools

- Python
- pandas
- PuLP
- DuckDB / SQL
- Matplotlib

## Repository Structure

- Notebooks – data processing, optimisation and analysis
- Figures – plots produced from the results
- Tables – results and sensitivity analysis outputs

## Project Status

The main modelling and analysis for the project are complete.

I am currently writing a full report covering the methodology, assumptions, results, sensitivity analysis, discussion and limitations. This will be added to the repository once complete.

## Motivation

I started this project because I wanted to apply Python and optimisation to an energy problem with a clear Chemical Engineering application.

I was particularly interested in whether the flexibility of electrolysers could be used to respond to changing electricity-system conditions, and how this creates trade-offs between economic and environmental objectives.
```
