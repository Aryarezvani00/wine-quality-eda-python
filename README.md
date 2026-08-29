# Wine Quality Exploratory Data Analysis

Exploratory data analysis on a combined red & white wine dataset, investigating which chemical properties are associated with wine quality ratings.

## Questions Answered

1. What chemical characteristics are most important in predicting the quality of wine?
2. Is a certain type of wine (red or white) associated with higher quality?
3. Do wines with higher alcoholic content receive better ratings?
4. Do sweeter wines (more residual sugar) receive better ratings?
5. What level of acidity (pH) is associated with the highest quality?

## Dataset

[`wine_data.csv`](data/wine_data.csv) — combined red and white wine samples with the following fields:

`fixed acidity`, `volatile acidity`, `citric acid`, `residual sugar`, `chlorides`, `free sulfur dioxide`, `total sulfur dioxide`, `density`, `pH`, `sulphates`, `alcohol`, `quality`, `color`

## Approach

Full analysis is in [`wine_quality_analysis.ipynb`](python/wine_quality_analysis.ipynb), using **pandas** for data handling, and **seaborn** / **matplotlib** for visualization.

- Computed correlations between all chemical properties and `quality`, isolating the ranked correlations against quality specifically (rather than reading a full 12x12 heatmap) to directly answer which features matter most
- Compared quality distributions between red and white wine
- Visualized the relationship between alcohol content and quality
- Visualized the relationship between residual sugar and quality
- Grouped wines by pH range to see where quality peaks

## Key Findings

- **Alcohol content** has the strongest relationship with quality (r ≈ 0.44) — higher-alcohol wines tend to score higher
- **Density** and **volatile acidity** show moderate negative correlations (r ≈ -0.31 and -0.27) — lower density and lower volatile acidity associate with higher-rated wines
- **Wine color**: white wine has a slightly higher average quality than red, though the difference is modest
- **Residual sugar** shows no meaningful correlation with quality (r ≈ -0.04) — sweetness does not predict rating
- **Acidity (pH)**: top-rated wines cluster in a moderate-to-higher acidity range; very high or low acidity becomes rarer among top-rated wines

Overall, alcohol content, density, and volatile acidity stand out as the most useful chemical predictors of quality in this dataset, while sugar content appears essentially unrelated.

## Tools

`Python` · `pandas` · `seaborn` · `matplotlib` · `Jupyter Notebook`

## What I'd Explore Next

- Build a simple regression or classification model to quantify how well these chemical properties predict quality, rather than relying on correlation alone
- Investigate interaction effects (e.g., does alcohol's effect on quality change at different acidity levels?)
