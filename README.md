# Eurasian Entity Risk Screener
A from-scratch Python tool that screens companies against OFAC sanctions data 
and World Bank governance indicators to produce composite risk scores — 
with a focus on Eurasian and high-risk jurisdictions.

## What It Does
- Screens any company name against 38,895 OFAC sanctioned entities
- Checks alternate/AKA names to catch transliterated Eurasian entity variants
- Scores countries using six World Bank governance indicators (2024 data)
- Produces a composite risk score and risk level: CRITICAL / HIGH / MEDIUM / LOW
- Accepts batch CSV input and exports results

## Key Output Example
| Company | Country | Sanctions Hit | Governance Score | Risk Level |
|---|---|---|---|---|
| ROSNEFT | Russia | True | -0.96 | CRITICAL |
| WAGNER GROUP | Russia | True | -0.96 | CRITICAL |
| Gazprom | Russia | False | -0.96 | HIGH |
| IRAN AIR | Iran | True | -1.29 | CRITICAL |
| Siemens | Germany | False | 1.36 | LOW |
| Nokia | Finland | False | 1.78 | LOW |

## Governance Indicators Used
Six World Bank Worldwide Governance Indicators (2024):
- Control of Corruption
- Rule of Law
- Political Stability & Absence of Violence
- Government Effectiveness
- Regulatory Quality
- Voice & Accountability

Scores range from -2.5 (worst) to +2.5 (best). Composite score is the average 
across all six dimensions.

## Data Sources
- OFAC Specially Designated Nationals (SDN) List — U.S. Treasury
- World Bank Worldwide Governance Indicators (2024)

## Tech Stack
Python 3.14 · pandas · NumPy · matplotlib · seaborn · openpyxl

## How to Use
1. Create a CSV with columns: `company` and `country`
2. Call `screen_batch('your_file.csv')`
3. Results exported to `screening_results.csv`

## Background
Built by an international affairs analyst specializing in Eurasian political 
economy and cross-border risk intelligence. Conceived as a practical tool 
for entity-level due diligence across European and Eurasian jurisdictions.
