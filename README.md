 🏅 Olympic Medal Analysis Dashboard — Power BI


📊 Project Overview

This project is an interactive **Olympic Medal Analysis Dashboard** developed in **Microsoft Power BI**.

The dashboard analyzes Olympic medal data from **1896 to 2016**, allowing users to explore medal performance across different countries, sports, years, and medal types.

The main objective of the project was to transform raw Olympic medal data into an interactive and easy-to-understand dashboard that provides insights into country performance and medal distribution.

---

 🎯 Project Objectives

The main objectives of this project were to:

- Analyze Olympic medal performance across countries.
- Compare Gold, Silver, and Bronze medals.
- Analyze medal performance by year and sport.
- Identify countries with the highest number of medals.
- Provide interactive filtering for deeper analysis.
- Create a clear and user-friendly Power BI dashboard.
- Present detailed medal-level information alongside high-level KPIs.

---

🛠️ Tools & Technologies

- **Microsoft Power BI**
- **Power Query** – Data cleaning and transformation
- **DAX** – Measures and calculations
- **Data Modeling** – Star schema / dimensional modeling
- **Power BI Visualizations** – Charts, KPI cards, slicers and tables

---

📁 Dataset

The dataset contains Olympic medal information that can be analyzed using dimensions such as:

- Country
- Sport
- Year
- Medal Type

The dashboard covers Olympic Games from **1896 to 2016**.

The data is transformed in Power Query before being loaded into the Power BI data model.

---

🧹 Data Preparation

The data preparation process included:

- Removing unnecessary columns.
- Checking and handling missing values.
- Standardizing country and sport names.
- Ensuring the Olympic year was stored correctly.
- Cleaning medal categories.
- Preparing the data for dimensional modeling.
- Creating relationships between fact and dimension tables.

---

 🧩 Data Model

The dashboard follows a **star-schema approach**.

The central fact table contains Olympic medal records, while dimension tables provide descriptive information for:

- Countries
- Sports
- Years
- Medal types

### Fact Table

**FactMedals**

Contains the individual medal records used for analysis.

Example fields:

- MedalKey
- CountryKey
- SportKey
- YearKey
- MedalKey

### Dimension Tables

**DimCountry**

- CountryKey
- CountryName

**DimSport**

- SportKey
- SportName

**DimYear**

- YearKey
- Year

**DimMedal**

- MedalKey
- MedalType

This structure makes it easier to filter and analyze medal data while keeping the model organized and scalable.

---

📈 Dashboard Features

🥇 Medal KPI Cards

The dashboard displays three main KPIs:

- Gold Medals
- Silver Medals
- Bronze Medals

These KPIs dynamically change according to the selected filters.

---

### 🌍 Country Filter

Users can select a specific country or view all countries.

This allows the dashboard to be used for both:

- Overall Olympic analysis
- Individual country analysis

---

### 📅 Year Filter

The year slicer allows users to analyze medal performance for a specific Olympic year.

For example, selecting **1924** updates the dashboard to show medal results for that Olympic Games.

---

### 🏃 Sport Filter

Users can filter the analysis by sport.

This makes it possible to investigate questions such as:

- Which countries performed best in Athletics?
- How many medals were awarded in Swimming?
- Which countries dominated a particular sport?

---

### 🏆 Country Medal Ranking

The horizontal bar chart ranks countries according to the number of medals won.

Gold, Silver, and Bronze medals are displayed separately, making it easier to compare overall medal performance.

---

### 📋 Medal Detail Table

The detailed table provides a more granular view of the data.

It includes:

- Country
- Sport
- Year
- Number of Medals
- Medal Type

This allows users to move from a high-level overview into more detailed medal analysis.

---

## 📐 DAX Measures

Example measures used for the dashboard include:

### Gold Medals

```DAX
Gold Medals =
CALCULATE(
    COUNTROWS(FactMedals),
    DimMedal[MedalType] = "Gold"
)


