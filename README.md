# Predição de Shelf-Life via Cinética de Degradação de Viscosidade

Este projeto demonstra como a análise de dados pode ser aplicada para avaliar a estabilidade de um sistema alimentício semissólido (matriz análoga a extratos/purês) e prever sua vida de prateleira com base na degradação da viscosidade.

A predição de shelf-life é essencial para definir validade comercial, reduzir perdas logísticas e garantir a qualidade do produto ao longo da cadeia de distribuição.

---

## Objective

To model viscosity degradation over time under different storage conditions and evaluate the impact of temperature on product stability.

This study supports shelf-life estimation using a data-driven approach combined with food science and kinetic modeling principles.

---

## Dataset

The dataset represents a controlled experimental study and includes:

- Multiple production batches  
- Storage at different temperatures (25°C, 35°C, 45°C)  
- Time-based measurements  
- Viscosity values (cP)  

---

## Methodology

The analysis was structured into well-defined data science steps:

- **Cleaning:** data cleaning and standardization  
- **EDA (Exploratory Data Analysis):** pattern exploration  
- **Modeling:** degradation modeling and kinetic analysis  

Key steps:

- Data preprocessing and validation  
- Visualization of viscosity degradation over time  
- Evaluation of batch-to-batch variability  
- Estimation of degradation rate constants (k)  
- Arrhenius modeling  

---

## Results

### Viscosity Degradation Over Time

![Viscosity Degradation](images/Viscosity-degradation.png)

**Figure 1:** Relative viscosity degradation (%) under three isothermal conditions.

A consistent reduction in viscosity was observed during storage, with faster degradation at higher temperatures.

The **end-of-shelf-life criterion** was defined as **80% of the initial viscosity**.

- At **45°C**, the product reaches this limit at approximately **5 months**  
- At **25°C**, the product remains above the limit throughout the evaluated period  

This behavior is consistent with physicochemical changes such as structural breakdown and increased molecular mobility.

---

### Batch-to-Batch Variability

![Batch Variability](images/Batch-variability.png)

**Figure 2:** Batch variability across storage conditions.

Batch variability remained controlled, indicating consistency in the production process.

The observed dispersion is expected under real manufacturing conditions and does not compromise the overall degradation trend.

---

### Arrhenius Modeling

![Arrhenius Plot](images/Arrhenius.png)

**Figure 3:** Arrhenius relationship (ln(k) vs 1/T).

The temperature dependence of degradation was modeled using:

ln(k) = ln(A) - (Ea/R) * (1/T)

The regression showed strong linearity (**R² > 0.90**), confirming the applicability of the kinetic model.

From the slope (-Ea/R), the **activation energy (Ea)** was estimated, demonstrating the sensitivity of the system to temperature.

This model enables:

- Shelf-life extrapolation for non-tested temperatures  
- Prediction of product behavior under different logistics scenarios  
- Application of Accelerated Shelf-Life Testing (ASLT)  

---

## Discussion

Temperature is the main driver of viscosity degradation.

Higher temperatures accelerate molecular mobility and structural breakdown, leading to faster loss of consistency.

The degradation profile indicates a temperature-dependent system consistent with physicochemical degradation mechanisms in semi-solid foods.

Low batch variability reinforces the robustness of the dataset and the reliability of predictive modeling.

---

## Why Python for Food Stability Analysis?

Transitioning from Excel to Python enabled a more robust and scalable analytical approach:

**Complex Data Handling**  
Using Pandas (e.g., `ffill()` and string normalization) automated cleaning of manually collected data, avoiding inconsistencies such as "25 C" vs "25°C".

**Statistical Rigor**  
With `scipy.stats`, it was possible to extract **R², standard errors, and p-values**, ensuring proper validation of regression models.

**Arrhenius Predictive Modeling**  
Temperature conversion to Kelvin and logarithmic linearization allowed accurate estimation of **activation energy (Ea)**.

**Variability Visualization**  
Automated plotting of standard deviation and error bars across batches enabled a comprehensive variability analysis.

The integration of **Pandas, Matplotlib, and SciPy** transformed raw experimental data into actionable insights, enabling predictive modeling of shelf-life across different storage conditions.

---

## Conclusion

This project demonstrates how data analysis can be integrated with food science to evaluate product stability in a structured, quantitative, and predictive way.

The results highlight temperature as a critical factor in viscosity degradation and validate the use of kinetic modeling for shelf-life estimation.

This approach enables:

- Reduction of real-time experimental testing  
- Use of accelerated shelf-life testing (ASLT)  
- Early prediction of product instability  

Such analyses are directly applicable in industrial environments, supporting better decision-making, process optimization, and quality control.

---

## Author

**Marina Mendonça**  
Food Science Data Analyst
