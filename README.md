# Gender Wage Gap: An Oaxaca-Blinder Decomposition

Econometric analysis of the gender wage gap using the Wooldridge `wage1` dataset 
(526 US workers), applying OLS regression and Blinder-Oaxaca decomposition to 
separate the gap into components explained by observable characteristics versus 
differential returns to those characteristics.

## Research Question
Does a gender wage penalty persist after controlling for education, experience, 
and tenure — and if so, is it driven by differences in worker characteristics 
or by differences in how those characteristics are rewarded?

## Method
- **OLS regression** across three specifications: raw gap → human capital 
  controls (education, experience, tenure) → nonlinear returns to experience
- **Blinder-Oaxaca decomposition** to split the gap into:
  - Endowment effect (differences in characteristics)
  - Coefficient effect (differences in returns to those characteristics)
  - Interaction effect
- Heteroskedasticity-robust standard errors throughout

## Key Results
| | |
|---|---|
| Raw gender wage gap | 33% (log points: 0.397) |
| Adjusted gap (controlling for education, experience, tenure) | 26% (log points: 0.298) |
| Share of gap explained by endowments | ~17.5% |
| Share of gap explained by coefficient effects | ~73% |

The dominant coefficient effect suggests the gap is driven more by men and women 
receiving different returns to the same characteristics than by differences in 
the characteristics themselves — consistent with Blau and Kahn (2017) and 
Goldin (2014).

## Repo Structure
├── scripts/gender_paygap_wage1.do    # Full Stata code
├── output/                            # Regression log + graphs
└── report/                            # Full write-up with literature review

## Data
Sourced directly from the public Wooldridge textbook data repository within the 
script — no data files are redistributed here. Running the `.do` file pulls it 
automatically from:
`http://fmwww.bc.edu/ec-p/data/wooldridge/wage1.dta`

## Tools
Stata (OLS, robust SE, `oaxaca` decomposition package)
