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
**File post cleaning:** https://github.com/nandinikapoor102002-lab/My-first-Github-project/blob/main/data/asian_islamic_neareastern_met_CLEANED.csv 

**What has already been done to the data:**
- Downloaded full MET dataset (484,956 rows) in chunks
- Filtered to three departments: Asian Art, Islamic Art, Ancient Near Eastern Art
- Cleaned and validated for analysis
- Preserved NULL values (honest data approach)
- Saved as CSV (23.49 MB)

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
- Tool: JupyterLab
- Notebook: [notebooks/Met museum data.ipynb](notebooks/Met%20museum%20data.ipynb)

### 2. Selection / Sampling
- Filtered the full dataset to three departments: Asian Art (37,000),
  Islamic Art (15,573), and Ancient Near Eastern Art (6,223)
- Selected these departments because they are directly relevant to the
  research question about cultural distribution across Asia and the
  Islamic world
- Dropped 9 redundant columns (internal IDs, duplicate URLs)
- Result: 58,796 rows, 45 columns, 23.49 MB


## Workflow

The project follows a 7-stage reproducible workflow:

### 1. Data Access
- **Tool:** JupyterLab
- **Task:** Downloaded full MET Museum open access dataset (484,956 rows)
- **Output:** Raw CSV file

### 2. Selection / Sampling
- **Task:** Filtered to three relevant departments
- **Rationale:** Direct relevance to research question about cultural distribution
- **Output:** 58,796 rows × 45 columns

### 3. Cleaning / Preprocessing
- **Task:** Identified missing values, handled inconsistencies
- **Key Gaps Documented:**
  - Dynasty: 100% missing
  - Artist information: 82% missing
  - Country: 74% missing
  - Period: 43.8% missing
- **Output:** `data/dataset_statistics.csv`

### 4. Enrichment / Linking
- **Status:** Not yet implemented
- **Future Plan:** Link Culture field to external geographic data

### 5. Analysis
- **Tool:** Jupyter Notebooks
- **Implemented in:**
  - `02_transformation_analysis.ipynb` — Culture distribution
  - `03_analysis.ipynb` — Period, Country, Department, Completeness

### 6. Visualisation
- **Outputs:**
  - Bar charts (cultures, periods, countries)
  - Missing data visualization
  - Summary statistics table

### 7. Archiving & Sharing
- Code stored on GitHub (public repository)
- Dataset described with source & license
- All outputs in `/data` folder
- Ready for Zenodo publication
  
### 4. Enrichment / Linking
- Not applicable at this stage
- Future possibility: linking Culture field to external geographic
  data to map object origins more precisely

  ---

## Analysis Notebooks

### 02_transformation_analysis.ipynb

**Purpose:** Analyze cultural distribution in the MET dataset

**What it does:**
1. Loads cleaned CSV (58,796 objects)
2. Filters to objects with recorded Culture (42,117 objects)
3. Counts objects per culture
4. Creates visualization of top 15 cultures
5. Documents findings and limitations

**Key Findings:**
- **Japan dominates:** 16,937 objects (40.2% of analyzable collection)
- **China second:** 13,502 objects (32.0%)
- **Combined East Asian:** 30,439 objects (72.2% of collection)
- **Reflects museum bias:** 19th-20th century Western collecting priorities

**Data Quality:**
- Culture completeness: **71.6%** (42,117/58,796 objects)
- 28.3% lack culture information
- NULL values preserved (not filled with placeholders)

## Key Research Findings

### 1. Cultural Distribution
- Japanese & Chinese cultures dominate (64.5% of analyzable collection)
- Reflects 19th-20th century European/American collecting priorities
-  South Asian, Islamic, Near Eastern vastly underrepresented
-   8.3% of collection lacks culture attribution

### 2. Temporal Coverage
- Objects span multiple historical periods  
- 43.8% lack period information  
- Only 56.2% analyzable by time period

### 3. Geographic Coverage
-**SEVERE DATA GAP:** Only 25.5% have country recorded  
-74.4% of objects lack geographic origin  
-Country-based analysis highly limited

### 4. Data Quality & Transparency
- HIGHLY VARIABLE completeness across fields  
- Core research metadata (Culture/Country/Period) incomplete  
- Cleaned dataset preserves NULL values (honest approach)  
- all limitations explicitly documented

---

## Important Context

### What This Dataset Shows
- Museum collecting priorities and institutional bias
- What the MET chose to acquire and document
- 19th-20th century Western focus on East Asian art

### What This Dataset Does NOT Show
- Complete or representative sample of global cultural heritage
- Actual distribution of cultural production globally
- Equal representation of all cultures and time periods

### Museum Collecting Bias
The dominance of Japanese & Chinese objects reflects institutional collecting history, not cultural significance or production. This is a key finding demonstrating how museums encode historical biases into their collections.

---

## Research Notes

### Known Limitations
- Period and Dynasty fields are empty for many objects
- Country and Region fields inconsistently filled
- Artist information missing for 82% of objects
- Results reflect museum bias, not global cultural distribution


## Reproducibility

### To Reproduce This Analysis
1. Clone this GitHub repository
2. Download the cleaned CSV from `/data` folder
3. Run `02_transformation_analysis.ipynb` (requires pandas, matplotlib)
4. All outputs will be saved to `/data` folder





