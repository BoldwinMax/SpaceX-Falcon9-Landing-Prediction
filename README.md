# 🚀 SpaceX Falcon 9 First Stage Landing Prediction

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange.svg)
![Plotly](https://img.shields.io/badge/Plotly-Dash-green.svg)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen.svg)

---

## 📌 Project Overview

This is an end-to-end data science capstone project focused on predicting whether the **SpaceX Falcon 9 first stage will successfully land** after launch. SpaceX advertises Falcon 9 rocket launches at a cost of **$62 million**, significantly cheaper than competitors, largely because the first stage can be reused. Predicting landing success helps estimate launch costs and provides competitive insights for companies bidding against SpaceX.

---

## 🎯 Objective

> **Can we predict whether the Falcon 9 first stage will land successfully?**

By analyzing historical SpaceX launch data, we build and evaluate multiple machine learning classification models to answer this question with measurable accuracy.

---

## 🗂️ Project Structure

```
SpaceX-Falcon9-Landing-Prediction/
│
├── README.md
│
├── notebooks/
│   ├── 01_data_collection_api.ipynb          # Collecting data via SpaceX REST API
│   ├── 02_data_collection_webscraping.ipynb  # Scraping Wikipedia launch records
│   ├── 03_data_wrangling.ipynb               # Cleaning and preparing the dataset
│   ├── 04_eda_sql.ipynb                      # Exploratory Data Analysis using SQL
│   ├── 05_eda_visualization.ipynb            # EDA with Matplotlib & Seaborn
│   ├── 06_interactive_map_folium.ipynb       # Launch site analysis with Folium maps
│   ├── 07_plotly_dash_dashboard.py           # Interactive dashboard with Plotly Dash
│   └── 08_predictive_analysis_classification.ipynb  # ML classification models
│
├── data/
│   ├── spacex_launch_data.csv                # Cleaned dataset from API
│   └── spacex_web_scraped.csv                # Dataset from web scraping
│
└── presentation/
    └── SpaceX_Capstone_Presentation.pdf      # Final project presentation
```

---

## 🔬 Methodology

### 1. Data Collection
- **SpaceX REST API** - Retrieved historical launch records including payload mass, orbit type, launch site, and landing outcome
- **Web Scraping (Wikipedia)** - Scraped Falcon 9 launch records table using BeautifulSoup

### 2. Data Wrangling
- Handled missing values (e.g., imputed PayloadMass with mean)
- Created binary classification label: **1 = Successful Landing**, **0 = Failed Landing**
- Filtered relevant columns for analysis

### 3. Exploratory Data Analysis (EDA)
- **SQL Queries** - Analyzed launch sites, payload ranges, success rates by orbit
- **Visualizations** - Flight number vs. launch site, payload vs. orbit type, yearly success trends

### 4. Interactive Visual Analytics
- **Folium Maps** — Mapped all launch sites, marked success/failure outcomes, analyzed proximity to infrastructure
- **Plotly Dash Dashboard** - Interactive pie charts and scatter plots to explore payload and success rates dynamically

### 5. Predictive Analysis
Trained and tuned four classification models:
- Logistic Regression
- Support Vector Machine (SVM)
- Decision Tree
- K-Nearest Neighbors (KNN)

Evaluated using **accuracy score** and **confusion matrices** on a test split, with **GridSearchCV** for hyperparameter tuning.

---

## 🛠️ Tools & Libraries

| Category | Tools |
|---|---|
| Language | Python 3.8+ |
| Data Manipulation | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Interactive Maps | Folium |
| Dashboard | Plotly Dash |
| Machine Learning | Scikit-learn |
| Database/SQL | SQLite, SQLAlchemy, ibm_db |
| Web Scraping | BeautifulSoup, Requests |
| Environment | Jupyter Notebook |

---

## 📊 Key Findings

- **Launch success rates have improved significantly** over the years, indicating operational maturity
- **KSC LC-39A** had the highest launch success rate among all launch sites
- **Heavier payloads** showed varying success rates depending on the orbit type
- **ES-L1, GEO, HEO, and SSO orbits** showed 100% success rates
- All four ML models achieved **similar accuracy (~83%)**, with the **Decision Tree and SVM** performing best after tuning
- **GridSearchCV** improved model performance by optimizing hyperparameters

---

## ⚙️ How to Run

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn folium plotly dash requests beautifulsoup4
```

### Running the Notebooks
1. Clone this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/SpaceX-Falcon9-Landing-Prediction.git
   cd SpaceX-Falcon9-Landing-Prediction
   ```

2. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

3. Run notebooks **in order** (01 → 08) for the full pipeline

### Running the Dash Dashboard
```bash
cd notebooks/
python 07_plotly_dash_dashboard.py
```
Then open your browser at `http://127.0.0.1:8050/`

---

## 📈 Model Results Summary

| Model | Best Accuracy |
|---|---|
| Logistic Regression | ~83% |
| Support Vector Machine | ~83% |
| Decision Tree | ~83% |
| K-Nearest Neighbors | ~83% |

---

## 📁 Dataset

- **Source**: [SpaceX REST API](https://api.spacexdata.com/v4/launches/past) and [Wikipedia](https://en.wikipedia.org/wiki/List_of_Falcon_9_and_Falcon_Heavy_launches)
- **Records**: ~90 Falcon 9 launches
- **Features**: FlightNumber, PayloadMass, Orbit, LaunchSite, Flights, GridFins, Reused, Legs, LandingPad, Block, ReusedCount, Serial, Longitude, Latitude
- **Target Variable**: `Class` (1 = Landing Success, 0 = Landing Failure)

---

## 👤 Author

**[Bolwin Mweemba**
- IBM Data Science Professional Certificate - Capstone Project
- [LinkedIn Profile](https://www.linkedin.com/in/boldwin-mweemba)
- [GitHub](https://github.com/BoldwinMax)

---

## 📜 Certificate

This project was completed as part of the **IBM Data Science Professional Certificate** on Coursera.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
