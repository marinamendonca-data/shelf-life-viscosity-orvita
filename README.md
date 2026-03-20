# Shelf-Life Prediction via Viscosity Degradation Kinetics

This project demonstrates how data analysis can be applied to evaluate the stability of a semi-solid food system (matrix analogous to purées/extracts) and predict its shelf life based on viscosity degradation.

Shelf-life prediction is essential for defining commercial validity, reducing logistical losses, and ensuring product quality throughout the distribution chain.

---

## Objective

To model viscosity loss over time under different storage conditions, quantify degradation kinetics, and predict shelf life using a data-driven approach integrated with chemical kinetics and food science principles.

---

## Dataset

The dataset represents a controlled experimental study and includes:

* Multiple production batches
* Storage at different temperatures (25°C, 35°C, 45°C)
* Time-based measurements
* **Viscosity values (cP – absolute measurements)**

---

## Methodology

The analysis was structured following data science best practices:

* **Cleaning:** data standardization and preprocessing
* **EDA:** pattern exploration and degradation behavior
* **Modeling:** kinetic modeling and regression analysis

### Key steps:

* Data preprocessing and validation
* Conversion of viscosity to **relative viscosity (%)** for comparability
* Visualization of degradation trends
* Estimation of degradation rate constants (k)
* Linear regression for shelf-life estimation (t₈₀)
* Application of the Arrhenius model
* Extrapolation to non-tested temperatures

---

## Results

### Viscosity Degradation Over Time

![Viscosity Degradation](images/Viscosity-degradation.png)

**Figure 1:** Relative viscosity degradation (%) under three isothermal conditions.

> ⚠️ Note: The graph represents **relative viscosity (%)**, normalized to the initial value (t=0).
> Raw measurements are expressed in **cP (centipoise)**.

A consistent reduction in viscosity was observed during storage, with faster degradation at higher temperatures.

The **end-of-shelf-life criterion** was defined as **80% of the initial viscosity**.

Estimated shelf life (t₈₀):

* **25°C → ~27.5 months**
* **35°C → ~11.8 months**
* **45°C → ~6.4 months**

---

### Batch-to-Batch Variability

![Batch Variability](images/Batch-variability.png)

**Figure 2:** Variability across batches over time (mean ± standard deviation).

Batch variability remained controlled across all conditions, indicating consistency in the production process.

The observed dispersion is expected in real manufacturing environments and does not compromise the overall degradation trend.

---

### Arrhenius Modeling and Thermal Sensitivity

![Arrhenius Plot](images/Arrhenius.png)

**Figure 3:** Arrhenius relationship (ln(k) vs 1/T).

The regression showed strong linearity:

* **R² = 0.95**

From the Arrhenius slope:

[
\text{slope} = -\frac{E_a}{R}
]

The **activation energy (Eₐ)** was estimated as:

* **Eₐ ≈ 40.1 kJ/mol**

This value indicates a **moderate-to-high temperature sensitivity**, meaning that relatively small increases in temperature significantly accelerate viscosity degradation.

---

### 🔮 Shelf-life Prediction (New Scenario)

Using the Arrhenius model, a new storage condition was simulated:

* **30°C → k ≈ 1.02**
* **Estimated shelf life → ~16.6 months**

This demonstrates the ability to:

* Predict shelf life without real-time experiments
* Support decision-making in intermediate storage conditions
* Apply Accelerated Shelf-Life Testing (ASLT) principles

---

## Discussion

Temperature was identified as the primary driver of viscosity degradation.

Higher temperatures increase molecular mobility and accelerate structural breakdown, leading to faster consistency loss.

The degradation behavior follows a temperature-dependent kinetic model consistent with semi-solid food systems.

The relatively low variability between batches reinforces the robustness of the dataset and supports the reliability of the predictive model.

---

## Why Python for Food Stability Analysis?

Transitioning from Excel to Python enabled a more robust and scalable analytical approach:

### Complex Data Handling

Using Pandas automated cleaning of manually collected data and removed inconsistencies.

### Statistical Rigor

With `scipy.stats`, it was possible to extract **R² and regression parameters**, ensuring proper model validation.

### Arrhenius Predictive Modeling

Temperature conversion to Kelvin and logarithmic transformation enabled estimation of:

* Degradation constants (k)
* **Activation energy (Eₐ)**
* Shelf-life extrapolation

### Variability Analysis

Aggregation and visualization enabled efficient analysis of multiple batches.

The integration of **Pandas, Matplotlib, and SciPy** transformed raw experimental data into **predictive and actionable insights**.

---

## Conclusion

This project demonstrates how data analysis and kinetic modeling can be combined to evaluate product stability in a structured and predictive way.

Key outcomes:

* Quantification of temperature impact on degradation
* Estimation of activation energy (Eₐ)
* Reliable shelf-life estimation under tested conditions
* **Prediction of shelf life at new temperatures (e.g., 30°C)**

This approach reduces reliance on long-term experimental studies and supports faster, data-driven decision-making in food systems.

---

## Author

**Marina Mendonça**
Food Science Data Analyst

