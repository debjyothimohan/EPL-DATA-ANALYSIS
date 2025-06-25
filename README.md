# EPL Data Analysis (2024–25)



## **Overview**

This repository contains a Jupyter Notebook that performs a comprehensive statistical analysis of **English Premier League (EPL)** player performance for the **2024–2025 season**. The project covers the entire data analysis workflow, from data loading and cleaning to in-depth exploratory data analysis (EDA). The analysis is broken down into player-level and team-level insights, utilizing both raw and derived metrics to identify top performers and uncover trends.

The goal is to provide a detailed, data-driven perspective on player and team performance based on a wide range of statistical categories.



## **Data Source**

The analysis is based on the `epl_player_stats_24_25.csv` dataset. This dataset contains comprehensive statistics for each player in the English Premier League for the 2024–25 season.



## **Key Features**

* **Player & Club Info**: Name, Club, Nationality, Position
* **Playing Time**: Appearances, Minutes
* **Attacking Stats**: Goals, Assists, Shots, Shots on Target, Hit Woodwork
* **Passing & Possession Stats**: Passes, Crosses, Through Balls, Touches, Dispossessed
* **Defensive Stats**: Tackles, Interceptions, Clearances, Clean Sheets
* **Disciplinary Records**: Yellow Cards, Red Cards, Fouls
* **Goalkeeping Stats**: Saves, Penalties Saved, Punches



## **Analysis Workflow**

### **1. Data Loading & Initial Exploration**

* The dataset is loaded using **pandas**
* Inspected the structure using `.head()` and `.columns`



### **2. Data Cleaning & Preprocessing**

* Checked for missing values using `df.isna().sum()`
* Verified that there are no duplicate rows using `df.duplicated().sum()`
* Automatically identified columns containing percentage signs (`%`), removed them, and converted to float
* Standardized all column names to `snake_case` using lowercase and underscores

---

### **3. Exploratory Data Analysis (EDA)**

#### **General Overview**

* Generated summary statistics using `df.describe()` for all numeric columns
* Created histograms for columns such as goals, assists, and minutes
* Created box plots to identify outliers for minutes played, goals, and assists



#### **Player-Level Analysis**

##### **Basic Metrics**

* **Top 10 Goal Scorers**
* **Top 10 Assist Providers**
* **Top 10 Players by Minutes Played**
* **Top 10 Players by Passes Attempted**
* **Top 10 Players by Fouls Committed**



##### **Advanced Metrics**

Several derived features were calculated for deeper insight:

* **Goal Contribution**: `goals + assists`
* **Per 90-Minute Stats**:
   * `goals_per_90`
   * `assists_per_90`
   * `goal_contrib_per_90`
* **Accuracy Features**:
   * `shot_accuracy = shots_on_target / shots`
   * `pass_accuracy = successful_passes / passes`
   * `cross_accuracy = successful_crosses / crosses`
* **Discipline Score**: `yellow_cards + 2 × red_cards`



##### **Relational Analysis**

Used scatter plots to analyze relationships between:

* **Goals vs. Assists**
* **Minutes Played vs. Goals**



#### **Team-Level Analysis**

Aggregated stats to the team (club) level for comparison:

* **Total Goals and Assists by Club**
* **Average Goal Contribution per Player by Club**
* **Average Minutes Played per Player by Club**
* **Total Fouls Committed by Club**
* **Total Cards (Yellow + Red)**
* **Average Pass Accuracy by Club**
* **Most Clean Sheets by Club**
* **Total Touches by Club**



#### **Positional Breakdown**

* Created a pivot table showing goals by club and position (e.g., **DEF**, **MID**, **FWD**)
* Visualized using a stacked bar chart to understand which positions contribute most to scoring for each club


