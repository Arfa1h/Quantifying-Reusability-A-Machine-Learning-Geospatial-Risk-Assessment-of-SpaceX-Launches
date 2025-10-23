# 🚀 Quantifying Reusability: An End-to-End Data Science Analysis of Falcon 9 Landings

This project develops a comprehensive, full-stack data science pipeline to analyze and predict the success of the SpaceX Falcon 9 rocket's first stage landing. The central motivation is the $\mathbf{\sim \$ 100 \text{ million saving}}$ achieved by reusing the booster, making accurate prediction critical for launch cost determination and competitive strategy.

---

## I. Project Scope & Business Context

The objective is to create a machine learning model to predict the binary outcome ($\mathbf{\text{class}}$) of a Falcon 9 landing given various launch parameters.

* **Business Problem:** If we can determine whether the first stage will land ($\mathbf{83.33\%}$ accuracy), we can accurately determine the cost of a launch. This is vital for competitive bidding.
* **Methodologies Used:** This project spans the entire data science lifecycle:
    * **Data Sourcing:** API Calls & Web Scraping
    * **Analytics:** Python, SQL, and Geospatial (Folium) EDA
    * **Dashboarding:** Plotly Dash
    * **Machine Learning:** Hyperparameter-tuned Classification Models

---

## II. Technical Pipeline Summary

### 1. Data Acquisition and Wrangling

* **Data Sourcing:** Combined data retrieved programmatically via the **SpaceX REST API** with supplementary details obtained through **Web Scraping** for a complete mission history.
* **Data Processing:** Cleaned data, defined the target variable ($\mathbf{\text{class}}$), and applied **One-Hot Encoding** to categorical features ($\text{Launch Site}$, $\text{Orbit}$) and **StandardScaler** to numerical features ($\text{Payload Mass}$, $\text{Flight Number}$).

### 2. Advanced Analytics and Visualization

* **Interactive Dashboard (Plotly Dash):** Developed a dynamic dashboard featuring a Launch Site Dropdown and Payload Range Slider for real-time analysis.
* **Geospatial Analysis (Folium):** Confirmed geographical strategic positioning: sites maintain a $\mathbf{\sim 65\text{ km}}$ distance from cities (safety) but are in close proximity to the $\mathbf{\text{coastline}}$ and $\mathbf{\text{railways}}$ (logistics).
* **Key Findings:** Visual analysis identified a clear $\mathbf{\text{learning curve}}$ (increasing success rate over time) and confirmed the $\mathbf{\text{3,000\text{ kg} \text{ to } 6,000\text{ kg}}}$ range as the optimal payload window.

### 3. Machine Learning Prediction

* **Model Performance:** Three top models achieved an identical and robust test accuracy.
    * $\mathbf{\text{Logistic Regression}, \text{SVM}, \text{and } \text{KNN}}$ all yielded $\mathbf{83.33\%}$ accuracy.
* **Risk Assessment:** The shared **Confusion Matrix** revealed the primary predictive weakness is $\mathbf{False Positives}$ (incorrectly predicting success), which is the highest-risk error for making operational recovery decisions.

---

## 🛠️ Requirements and Setup

1.  **Clone the repository.**
2.  **Install dependencies:** `pip install pandas dash plotly scikit-learn folium`
3.  **Run the application:** `python app.py`

*(Note: The main application file, `app.py`, contains the complete Dash implementation.)*
