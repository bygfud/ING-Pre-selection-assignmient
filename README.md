# Real Estate Price Prediction

This project is centered on forecasting property prices in Poland by leveraging both **web-scraped** listings and **synthetically generated** external data, including indicators such as unemployment, inflation, wages, and population trends.

Proces obejmuje:
- **Scraping real estate offers (apartments, houses, studios) from the Otodom platform.**
- **Generating synthetic observations to expand the dataset.**
- **Enriching the data with additional economic indicators.**
- **Geocoding listings to obtain location coordinates.**
- **Preprocessing and combining all data sources.**
- **Building and evaluating machine learning models to predict property prices.**

---

## Project Structure

```
.
├── Datasets/
│   ├── average_salary.csv
│   ├── data_final.csv
│   ├── gradual_unemployment_rate.csv
│   ├── inflation.xlsx
│   ├── otodom_apartment_offers.csv
│   ├── otodom_house_offers.csv
│   ├── otodom_offers_coordinates.csv
│   ├── otodom_studio_offers.csv
│   └── population.csv
├── WebScraping/
│   ├── WebScraping_apartments.ipynb
│   ├── WebScraping_house.ipynb
│   └── WebScraping_studio.ipynb
├── Coordianetes.ipynb
├── real_estate_prediction.ipynb
├── report_rep_project.html
└── README.md
```

---

## How It Works

### Data Collection / Web Scraping

- **Apartments** (`WebScraping_apartments.ipynb`)
- **Houses** (`WebScraping_house.ipynb`)
- **Studios** (`WebScraping_studio.ipynb`)

---

### Data Preparation

#### Geolocation Completion
`Coordianetes.ipynb` is used to fill in missing latitude and longitude values for property listings through geocoding methods.

#### Creation of Synthetic Samples
To expand the dataset and make it more varied, the project creates **synthetic property listings** by generating new samples that follow the patterns observed in the original data.  
This enhances the training process by giving machine learning models a broader and more representative set of examples.

#### Integration of External Data
The listing data is supplemented with additional external indicators, including:
- Average wages
- Unemployment levels
- Population data
- Inflation figures

These variables are combined with the property records to reflect wider economic conditions.  
The processed and merged dataset is then stored in `data_final.csv`.

Sources of external data:
- [Unemployment Rate (GUS)](https://bdl.stat.gov.pl/bdl/dane/podgrup/wymiary)
- [Average Salary (GUS)](https://bdl.stat.gov.pl/bdl/dane/podgrup/wymiary)
- [Population (World Bank)](https://data.worldbank.org/indicator/SP.POP.TOTL?locations=PL)
- [Inflation (NBP)](https://nbp.pl/statystyka-i-sprawozdawczosc/inflacja-bazowa/)

---

### Model Building
The core machine learning steps are contained in `real_estate_prediction.ipynb`:
- **Data cleaning**
- **Feature engineering**
- **Model training** (e.g., Linear Regression, Decision Trees, XGBoost)
- **Model evaluation** (error metrics like RMSE, R²)

---

## Technologies Used

- Python
- Jupyter Notebook
- pandas, numpy
- scikit-learn
- xgboost
- matplotlib, seaborn
- BeautifulSoup (for scraping)
- requests

---
## How to Run

1. Install the required libraries (suggested: create a virtual environment):
   ```bash
   pip install -r requirements.txt
   ```

2. Run the WebScraping notebooks (optional — data is already provided).

3. Run:
   - `Coordianetes.ipynb` to attach coordinates.
   - `real_estate_prediction.ipynb` to train and evaluate models.

4. Review the final results in `report_rep_project.html`.

---