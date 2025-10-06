# Mapping "Youth Opportunity Deserts" in San Diego County

Access to positive youth development opportunities—including after-school programs, libraries, parks, and mentorship—varies dramatically across San Diego neighborhoods, potentially limiting life outcomes for young people. The project aims to develop an interactive map that identifies "opportunity deserts" by overlaying locations of youth services with demographic data on youth population density, household income levels, and transportation access. Through GIS analysis, spatial statistics including Getis-Ord Gi* hotspot analysis, and network analysis for travel times, the project will quantify disparities in youth program access across the county. This tool will enable nonprofits and government agencies to strategically plan and fund new youth programs in underserved areas, ensuring equitable access to developmental resources that can break cycles of poverty and improve educational outcomes.


## Contributors

- Lauren Vo
- Rohan Raval


## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for those using this project
├── data
│   ├── external       <- Data from third-party sources
│   ├── interim        <- Intermediate data that has been transformed
│   ├── processed      <- The final, canonical data sets for modeling
│   └── raw            <- The original, immutable data dump
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         project_name and configuration for tools
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials and documentation
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
|
├── style_guide        <- Style guide for coding and naming conventions
│
└── project_name   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes project_name a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── features.py             <- Code to create features for modeling
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```

--------

Project organization based on Cookiecutter Data Science

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>
