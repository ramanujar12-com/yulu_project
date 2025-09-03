# Yulu Cycle Rental Demand Analysis                                                                                        



### **Project Overview**

This project analyzes the demand for shared electric cycles provided by **Yulu**, a leading micro-mobility service provider in India. The primary goal is to identify the key factors that influence the rental demand for these cycles and provide actionable insights to help Yulu recover from recent revenue dips. The analysis uses a dataset containing information on rental counts, weather conditions, time of year, and user type.

***

### **Problem Statement**

Yulu wants to understand the factors affecting the demand for their shared electric cycles in the Indian market. The specific questions to be answered are:

- Which variables are significant in predicting the demand for shared electric cycles?
- How well do these variables describe the electric cycle demands?

***

### **Dataset**

The analysis is based on the `yulu_data.csv` dataset, with the following columns:

| Column | Description |
| :--- | :--- |
| `datetime` | Date and time |
| `season` | Season (1: spring, 2: summer, 3: fall, 4: winter) |
| `holiday` | Whether the day is a holiday (1) or not (0) |
| `workingday` | Whether the day is a weekday and not a holiday (1) or not (0) |
| `weather` | Weather conditions (1: clear, 2: mist, 3: light rain/snow, 4: heavy rain/snow) |
| `temp` | Temperature in Celsius |
| `atemp` | "Feels like" temperature in Celsius |
| `humidity` | Humidity percentage |
| `windspeed` | Wind speed |
| `casual` | Count of rentals by casual users |
| `registered` | Count of rentals by registered users |
| `count` | Total count of rentals (casual + registered) |

***

### **Methodology and Concepts**

The project follows a structured data analysis pipeline, including:

- **Exploratory Data Analysis (EDA):** Initial data inspection, including checking data types, handling missing values, and performing univariate and bivariate analyses to understand the relationships between variables.
- **Hypothesis Testing:** Statistical tests were conducted to validate assumptions and find significant relationships. The following tests were used:
    - **Two-Sample T-Test:** To determine if the `workingday` variable has a significant effect on the number of cycles rented.
    - **ANOVA:** To check if the number of cycles rented is similar or different across various `weather` and `season` conditions.
    - **Chi-Square Test:** To check for a dependency between the `weather` and `season` variables.

***

### **Key Findings and Insights**

### **Observations:**

- **Data Characteristics:** The dataset shows a high frequency of higher humidity and low wind speeds, with a prominent peak at zero wind speed.
- **Variable Relationships:**
    - There is a **strong positive linear relationship** between the number of `registered` users and the total rental `count` (correlation coefficient of 0.98), and a **strong positive relationship** with `casual` users (correlation coefficient of 0.72).
    - `temp` and `atemp` are highly correlated.
    - `humidity` shows a **moderate negative correlation** with `count`.
- **Statistical Significance:**
    - All tested categorical variables (`season`, `holiday`, `workingday`, `weather`, `hour`, `dayofweek`, `month`, `year`) have a statistically significant relationship with bike rental demand, as indicated by low p-values from ANOVA tests.
    - The average number of rentals is **significantly different** between weekdays and weekends.
    - Both `weather` conditions and `seasons` have a significant impact on the average number of rentals.
    - There is a **significant association** between `weather` conditions and `seasons`, meaning certain weather patterns are more likely in specific seasons.

### **Recommendations:**

Based on the analysis, Yulu can implement the following strategies to optimize its operations:

1.  **Adjust Operations Based on Day of the Week:** The significant difference in demand between weekdays and weekends suggests that Yulu should adjust its operational strategies, such as:
    - **Increasing bike availability** during periods of higher demand (either weekdays or weekends, depending on which has a higher average).
    - **Implementing targeted marketing or pricing strategies** based on the day of the week to optimize ridership.

2.  **Leverage Weather and Seasonal Data:**
    - **Adjust bike availability and operational strategies** based on predicted weather conditions and seasonal demand patterns. For example, increase availability during favorable weather conditions and seasons (e.g., clear weather and fall).
    - **Implement promotions or incentives** during unfavorable weather conditions to encourage ridership, if feasible.
    - **Use the significant association between weather and seasons** to anticipate typical weather patterns and proactively adjust bike availability and maintenance schedules.

3.  **Focus on User Segments:**
    - The strong correlation between `registered` users and total `count` indicates that Yulu should focus on strategies to **increase and retain registered users**.

***

### **Technical Details**

- **Language:** Python
- **Libraries:** pandas, numpy, matplotlib, seaborn, scipy, statsmodels
- **Environment:** Google Colab
- **Repository Link:** `https://github.com/ramanujar12-com/yulu_project`

***

### **How to Run the Project**

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/ramanujar12-com/yulu_project.git](https://github.com/ramanujar12-com/.git)
    ```
2.  **Navigate to the project directory:**
    ```bash
    cd yulu_project
    ```
3.  **Open the Jupyter Notebook or Google Colab file (`.ipynb`):**
    - You can open it directly in Google Colab.
4.  **Install the required libraries** (if not already installed):
    ```bash
    pip install pandas numpy matplotlib seaborn scipy statsmodels
    ```
5.  **Run the notebook cells sequentially** to replicate the analysis and view the results.
