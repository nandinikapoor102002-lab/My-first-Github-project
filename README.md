## Workflow

### 1. Data Access
- Downloaded the full MET Museum open access dataset (484,956 rows) 
  from https://github.com/metmuseum/openaccess using pandas chunk 
  loading in Jupyter Notebook
- Tool: JupyterLab, pandas
- Notebook: [notebooks/Met museum data.ipynb](notebooks/Met%20museum%20data.ipynb)

### 2. Selection / Sampling
- Filtered the full dataset to three departments: Asian Art (37,000), 
  Islamic Art (15,573), and Ancient Near Eastern Art (6,223)
- Selected these departments because they are directly relevant to the 
  research question about cultural distribution across Asia and the 
  Islamic world
- Dropped 9 redundant columns (internal IDs, duplicate URLs)
- Result: 58,796 rows, 45 columns, 23.49 MB
- Output file: [data/asian_islamic_neareastern_met.csv](data/asian_islamic_neareastern_met.csv)

### 3. Cleaning / Preprocessing
- Identified missing values per column using df.isna().mean()
- Key gaps: Dynasty (100% missing), Artist information (82% missing),
  Country (74% missing)
- Decisions documented in notebook markdown cells
- Output: [data/dataset_statistics.csv](data/dataset_statistics.csv)

### 4. Enrichment / Linking
- Not applicable at this stage
- Future possibility: linking Culture field to external geographic 
  data to map object origins more precisely

### 5. Analysis
- Will measure distribution of objects by Culture, Country, Period, 
  and Object Type
- Will compare representation across the three departments
- Will analyse gaps in metadata completeness
- Tool: pandas, planned notebook: 02_analysis.ipynb

### 6. Visualisation
- Will create bar charts of top cultures and countries
- Will create timeline of objects by century
- Will create table of missing value percentages by column
- Tool: matplotlib or seaborn, planned notebook: 03_visualisation.ipynb

### 7. Archiving & Sharing
- All code and notebooks stored on GitHub (public repository)
- Raw dataset described in README with source URL and license
- Full CSV file kept locally and on OneDrive as backup
- Statistics output saved to data/ folder
