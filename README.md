# EART60702-group-4-project-1

# What Drives a Warming Climate? 
**Exploring the Physical Mechanisms Behind Regional Climate Change**

## Project Overview
This project is a comprehensive climate data analysis based on the Community Earth System Model Large Ensemble Project. Our study focuses on a specific region in Cheshire, Northwest England, UK (Coordinates: **53.246° N, 2.5° W**). 

Historically, this region features a typical temperate maritime climate strongly influenced by the Atlantic Ocean and the Gulf Stream. However, by analyzing 75 years of daily climate projection data (2006–2080), this project moves beyond simple temperature statistics to uncover the underlying physical drivers. We demonstrate how **Radiative Forcing** and **Thermodynamic Positive Feedback** are irreversibly pushing the regional climate into a higher-energy state characterized by "warmer, wetter, and more extreme fluctuations."

---

## File Structure
* `project_1.csv`: The raw climate dataset containing daily projections from 2006 to 2080.
* `project-1_5.0.ipynb`: The core Jupyter Notebook containing all data preprocessing, statistical analysis (linear regression), and data visualizations (styled for dark mode presentations).
* `Project_1_final.pptx` / `Project_1_final.pdf`: The final presentation slides summarizing our analytical framework, physical mechanisms, and key takeaways (provided in both editable PPTX and easily viewable PDF formats).
* `README.md`: This project documentation file.

---

## Dependencies
To run the code in this repository, you need the following Python libraries:
* `pandas`: For data manipulation, time-series processing, and pivot table generation.
* `numpy`: For numerical operations and array processing.
* `matplotlib`: For basic data visualizations (line plots, scatter plots).
* `seaborn`: For advanced statistical visualizations (monthly heatmaps, correlation matrix).
* `scipy.stats`: Specifically `linregress` for calculating linear regression, correlation coefficients (R), and statistical significance.

---

## Core Analytical Modules

Our analysis is structured into four main components:

### 1. Data Preparation & Processing
* Converting timestamp strings into `datetime` objects.
* **Unit Conversions** for readability: 
  * Temperature (`TREFHT`): Kelvin (K) ➡ Celsius (°C)
  * Precipitation (`PRECT`): Flux (m/s) ➡ Annual/Monthly accumulated (mm)
  * Specific Humidity (`QBOT`): (kg/kg) ➡ (g/kg)

### 2. Trend Analysis & Seasonal Distribution
* **Temperature**: Linear regression shows a strong upward trend (~0.4°C per decade, R ≈ 0.92). A monthly heatmap further reveals the increasing frequency and intensity of "deep red spots," indicating more extreme summer heatwaves in the mid-to-late 21st century.
* **Precipitation**: The annual trend exhibits massive inter-annual fluctuations, while the heatmap visualizes the baseline seasonality (wetter autumns, drier summers) and highlights the growing risk of seasonal droughts.

### 3. Energy Source: Radiative Forcing
* Analyzing the correlation between Surface Net Solar Radiation (`FSNS`) and Temperature (`TREFHT_C`).
* A clear positive linear relationship indicates that reduced cloud cover allows more solar radiation to penetrate the atmosphere and directly heat the surface, acting as the primary driver of regional warming spikes.

### 4. The Amplifier: Thermodynamic Feedback
* Exploring the coupling between Temperature (`TREFHT_C`) and Specific Humidity (`QBOT_g_kg`).
* The data perfectly aligns with the **Clausius-Clapeyron relation**, showing that the atmosphere's moisture-holding capacity increases exponentially as it warms. This highly saturated air acts as a potent greenhouse gas, trapping more heat (Positive Feedback) and serving as "fuel" for extreme precipitation fluctuations.

---

## Key Takeaways
1. **Systematic Warming**: The region is experiencing significant, long-term climate warming with reshaped seasonal structures (more extreme summer heat).
2. **Radiative Forcing**: The imbalance of surface energy budget, driven by net solar radiation, is the direct physical cause of temperature spikes.
3. **Thermodynamic Feedback**: The warming is dangerously amplified by the Clausius-Clapeyron effect, locking the region into a warmer, wetter, and more volatile climate state.

---

## Team  Task Distribution
*This project was completed by Group 4 for the EART60702 Earth and Environmental Data Science module.*

| Team Member | Student ID | Main Responsibilities |
| :--- | :--- | :--- |
| **Ruiqi Huang** | 14180111 | Annual trend charts & scatter plots, code integration, README authoring, PPT design. |
| **Kedi Li** | 14200199 | Monthly average trend charts (Heatmaps), PPT design. |
| **Yuhui Duan** | 14219275 | Correlation Matrix visualization, PPT design. |

---

## References
* Loeb, N. G., et al. (2019). "Decomposing shortwave top-of-atmosphere and surface radiative flux variations..." *Journal of Climate* 32(16): 5003-5019.
* Minobe, S., et al. (2008). "Influence of the Gulf Stream on the troposphere." *Nature* 452(7184): 206-209.
* O’Gorman, P. A. & Muller, C. J. (2010). "How closely do changes in surface and column water vapor follow Clausius–Clapeyron scaling..." *Environmental Research Letters* 5(2): 025207.
* Pall, P., et al. (2007). "Testing the Clausius–Clapeyron constraint on changes in extreme precipitation under CO2 warming." *Climate Dynamics* 28(4): 351-363.
* Palter, J. B. (2015). "The role of the Gulf Stream in European climate." *Annual review of marine science* 7(1): 113-137.
* Weilnhammer, V., et al. (2021). "Extreme weather events in europe and their health consequences–A systematic review." *Int. Journal of Hygiene and Environmental Health* 233: 113688.