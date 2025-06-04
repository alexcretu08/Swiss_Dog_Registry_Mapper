# Swiss_Dog_Registry_Mapper

**Vision:**
- **Data Source:**
  - Obtain or download `dogs_by_municipality.csv` from opendata.swiss (Identitas AG), or generate a synthetic dataset (~5,000 rows) with columns: 
    • `Registration_ID`  
    • `Canton` (e.g., “ZH”, “BE”, “VD”)  
    • `Municipality`  
    • `Breed`  
    • `Age` (years)  
    • `Owner_Gender` (M/F)  
    • `Registration_Date`
- **Data Cleaning & Preprocessing:**
  - Load `dog_registrations.csv` in pandas.
  - Standardize canton codes (e.g., “ZH” → “Zurich”).
  - Normalize breed names (e.g., “Berner Sennenhund” vs. “Bernese Mountain Dog”).
  - Convert `Registration_Date` to datetime and filter to 2024.
- **Exploratory Data Analysis:**
  - Compute total registrations per canton and per municipality.
  - Calculate top 5 most common breeds overall and by canton.
  - Analyze age distribution (mean/median) of registered dogs.
- **Geospatial Visualization:**
  - Use GeoPandas to load a Swiss cantons shapefile.
  - Merge aggregated counts (`registrations_by_canton.csv`) with the GeoDataFrame.
  - Create a Folium or Plotly choropleth map showing “Registrations per 1,000 residents” or absolute counts by canton.
  - Add mouse-hover tooltips: “Canton: XX, Total Dogs: YYY, Top Breed: ZZZ.”
- **Interactive Dashboard:**
  - Build a Streamlit app (`app.py`) where users can:
    1. Select a canton (dropdown).
    2. View a bar chart of top 5 breeds in that canton (Plotly).
    3. See a line chart of monthly registration counts over the past year.
  - Include a sidebar filter for “Breed” (multi-select) to highlight specific breeds across Switzerland.
- **Data Storytelling:**
  - Write `EDA_and_Maps.ipynb` to:
    1. Summarize key findings (“Zurich leads with 12,000 registrations, Bern sees fastest growth, top breed is Labrador Retriever”).
    2. Display static snapshots of the choropleth and breed-by-canton bar charts.
  - Export the notebook as `Swiss_Dog_Registry_Mapper_Report.pdf` for stakeholders.
- **Documentation & Next Steps:**
  - Add a `requirements.txt` listing: `pandas`, `geopandas`, `folium`, `plotly`, `streamlit`.
  - In `README.md`, explain:
    1. How to download or generate `dog_registrations.csv`.
    2. Install dependencies: `pip install -r requirements.txt`.
    3. Run data cleaning: `python clean_data.py`.
    4. Launch dashboard: `streamlit run app.py`.
  - Create a `DEPLOYMENT.md` stub with notes on deploying to Heroku/Streamlit Cloud.

**Key Skills Practiced:**
- Geospatial (GeoPandas, Folium, choropleth mapping)  
- Data cleaning & aggregation (pandas)  
- Data Storytelling (notebook → PDF)  
- Interactive visualization (Plotly, Streamlit)
