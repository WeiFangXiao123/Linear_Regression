## Predicting Home Sale Prices with Linear Regression
### Objective
The objective of this project is to analyze the relationship between the above-ground living area (```Gr_Liv_Area```) and house sale prices (```SalePrice```) using a simplified ordinal categorization. By binning continuous living area data and fitting a regression model, we aim to quantify how house size correlates with price, enabling clearer interpretation for business stakeholders.
### Dataset
The dataset used is **ameshousing.csv**, containing property transaction records from Ames, Iowa. It includes various structural attributes and sale prices for 300 homes, with key variables like:
- ```Gr_Liv_Area```: Above-ground living area (in square feet)
- ```SalePrice```: House sale price (in USD)

### Methodology
**1. Data Preparation:**
Loaded the dataset using tidyverse, and suppressed scientific notation for readability.

**2. Binning:**
```Gr_Liv_Area``` was split into **four equal-frequency bins** using quantiles. This discretization grouped homes based on similar ranges of living area, resulting in an ordinal predictor (```Gr_Liv_Area_bin```).

**3. Modeling:**
A **linear regression model** was fitted using ```SalePrice``` as the response and the binned ```Gr_Liv_Area_bin``` as an ordinal categorical predictor. The reference group was the smallest living area bin (bin 1).
- All coefficients for bins 2–4 were statistically significant with **p-values < 0.001**.
- R-squared of the model: **0.3526**, indicating **moderate explanatory power**.

**4. Mean Comparison:**
Group means of **SalePrice** were computed for each bin:
- Bin 2 homes were priced ~$24,763 higher than bin 1.
- Bin 3 homes were ~$44,674 higher than bin 1.
- Bin 4 homes were ~$59,200 higher than bin 1.

**5. Visualization:**
A bar chart was created to visually present the mean ```SalePrice``` for each ```Gr_Liv_Area``` bin.
<img width="686" alt="Screenshot 2025-05-19 at 4 24 16 PM" src="https://github.com/user-attachments/assets/5701b5c2-597b-4717-bbb4-375ec538b685" />

### Business Takeaway
House size is strongly correlated with sale price, even when categorized into broad ordinal bins. Larger homes (especially in the top two quartiles) command significantly higher prices. Real estate professionals and property investors can use such binning approaches to segment market offerings and better predict pricing tiers. This simplified modeling also enables communication with non-technical stakeholders by translating continuous metrics into actionable categories.
