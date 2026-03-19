# Shelf-Life Prediction via Viscosity Degradation Kinetics

This project demonstrates how data analysis can be applied to evaluate the stability of a semi-solid food system (matrix analogous to purées/extracts) and predict its shelf life based on viscosity degradation.

Shelf-life prediction is essential for defining commercial validity, reducing logistical losses, and ensuring product quality throughout the distribution chain.

---

## Objective

To model viscosity loss over time under different storage conditions and evaluate the impact of temperature on product stability.

The study aims to support shelf-life estimation using a data-driven approach integrated with chemical kinetics and food science principles.

---

## Dataset

The dataset represents a controlled experimental study and includes:

- Multiple production batches  
- Storage at different temperatures (25°C, 35°C, 45°C)  
- Time-based measurements  
- Viscosity values (cP)  

---

## Methodology

The analysis was structured into organized steps following data science best practices:

- **Cleaning:** data cleaning and standardization  
- **EDA (Exploratory Data Analysis):** pattern exploration and trend identification  
- **Modeling:** degradation modeling and kinetic fitting  

### Key steps:

- Data preprocessing and validation  
- Visualization of viscosity degradation over time  
- Evaluation of batch-to-batch variability  
- Estimation of degradation rate constants (k)  
- Application of the Arrhenius model  

---

## Results

### Viscosity Degradation Over Time

![Viscosity Degradation](images/Viscosity-degradation.png)

**Figure 1:** Relative viscosity degradation (%) under three isothermal conditions.

A consistent reduction in viscosity was observed during storage, with faster degradation at higher temperatures.

The **end-of-shelf-life criterion** was defined as **80% of the initial viscosity**.

Based on this threshold:

- At **45°C**, the product reaches the limit at approximately **5 months**  
- At **25°C**, the product remains above the limit throughout the evaluated period  

This behavior is consistent with physicochemical changes such as structural breakdown and increased molecular mobility.

---

### Batch-to-Batch Variability

![Batch Variability](images/Batch-variability.png)

**Figure 2:** Batch variability over storage time.

Batch variability remained relatively controlled, indicating consistency in the production process.

The observed dispersion is expected under real manufacturing conditions and does not compromise the overall degradation trend.

---

### Arrhenius Modeling

![Arrhenius Plot](images/Arrhenius.png)

**Figure 3:** Arrhenius relationship (ln(k) vs 1/T).

The regression showed **strong linearity (R² > 0.90)**, confirming the suitability of the kinetic model.

From the slope (-Ea/R), the **activation energy (Ea)** was estimated, demonstrating the sensitivity of the system to temperature.

This model enables:

- Shelf-life extrapolation for non-tested temperatures  
- Prediction of product behavior under different logistics scenarios  
- Application of **Accelerated Shelf-Life Testing (ASLT)**  

---

## Discussion

Temperature was identified as the primary driver of viscosity degradation.

Higher temperatures increase molecular mobility and accelerate structural breakdown, leading to a faster loss of consistency.

The degradation profile indicates a temperature-dependent system consistent with physicochemical degradation mechanisms in semi-solid foods.

The relatively low variability between batches reinforces the robustness of the dataset and the reliability of the predictive model.

---

## Why Python for Food Stability Analysis?

Transitioning from Excel to Python enabled a more robust and scalable analytical approach:

### Complex Data Handling  
Using Pandas (e.g., `ffill()` and string normalization) automated the cleaning of manually collected data, preventing inconsistencies such as "25 C" vs "25°C".

### Statistical Rigor  
With `scipy.stats`, it was possible to extract **R², standard errors, and p-values**, ensuring proper validation of regression models.

### Arrhenius Predictive Modeling  
Automatic temperature conversion to Kelvin and logarithmic linearization allowed accurate estimation of the **activation energy (Ea)**.

### Variability Visualization  
Automated plotting of standard deviation and error bars enabled simultaneous analysis of multiple batches, which would be time-consuming manually.

The integration of **Pandas, Matplotlib, and SciPy** transformed raw experimental data into **actionable insights**, enabling predictive modeling of shelf life across different storage conditions.

---

## Conclusion

This project demonstrates how data analysis can be integrated with food science to evaluate product stability in a structured, quantitative, and predictive way.

The results highlight temperature as a critical factor affecting viscosity degradation and validate the use of kinetic modeling for shelf-life estimation.

This approach enables:

- Reduction of real-time experimental testing  
- Use of Accelerated Shelf-Life Testing (ASLT)  
- Early prediction of product instability  

Such analyses are directly applicable in industrial environments, supporting better decision-making, process optimization, and product quality control.

---

## Author

**Marina Mendonça**  
Food Science Data Analyst

