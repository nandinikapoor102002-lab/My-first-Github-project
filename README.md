## Project description
This project is part of the course "The Art of Making Data Speak 
(Digital Tools and Methods)" at the Institut für Geschichte, 
Technische Universität Darmstadt. It explores open cultural 
heritage data as a source for historical and humanities research 
(Open Scholarship in History and Humanities).

## Research Purpose
To analyse how Asian, Islamic, and Ancient Near Eastern cultural 
heritage objects are distributed across cultures, countries, and 
historical periods in the MET Museum collection.

## Data Origin
**Source:** The Metropolitan Museum of Art Open Access  
**Date accessed:** 2026-05-06  
**License:** CC0 — No Rights Reserved  
**Description:** Collection metadata for Asian Art, Islamic Art and Ancient Near Eastern Art. 58,796 rows, 45 columns, 23.49 MB.  
**File:** [asian_islamic_neareastern_met.csv](data/asian_islamic_neareastern_met.csv)

**What has already been done to the data:**
- Downloaded full MET dataset (484,956 rows) in chunks
- Filtered to three departments: Asian Art, Islamic Art, Ancient Near Eastern Art
- Dropped 9 redundant columns
- Saved as CSV (23.49 MB)

**What is missing or uncertain:**
- Period and Dynasty fields are empty for many objects
- Country and Region fields inconsistently filled
- Artist information missing for many objects

## Initial Research Steps (Reconstructed)
1. Attempted Wikidata SPARQL — returned 502 errors (backend migration May 2026)
2. Considered V&A Museum API — excluded due to unclear terms and conditions
3. Selected MET Museum CC0 dataset — no restrictions, safe for open research
4. Downloaded and filtered dataset in Jupyter Notebook
5. Uploaded to GitHub

**Notes:**
- What I did but cannot fully remember: initial Wikidata query attempts
- Files that changed without documentation: none — all steps recorded in notebook

## Research Questions

**Main question:** How are Asian, Islamic, and Ancient Near Eastern cultural 
heritage objects distributed across cultures, countries, and historical 
periods in the MET Museum collection?

**Specific aspects:**

1. Which cultures are most represented in the collection?
   - Answered by: `Culture` column

2. Which countries of origin appear most frequently?
   - Answered by: `Country` column

3. How are objects distributed across historical periods?
   - Answered by: `Period`, `Dynasty`, `Object Begin Date` columns
   - Limitation: Period and Dynasty are empty for many objects

4. What types of objects dominate the collection?
   - Answered by: `Object Name`, `Classification` columns

5. What proportion of objects are in the public domain?
   - Answered by: `Is Public Domain` column

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

  ## Results
- **02_transformation_analysis.ipynb**: Culture distribution analysis
- **03_analysis.ipynb**: Period, country, completeness analysis

## Key Findings
- Japan & China: 64.5% of analyzed collection
- Culture data: 71.6% complete
- Country data: 25.5% complete (SEVERE GAP)
- Period data: 56.2% complete

See notebooks for full analysis and visualizations.
