# Open Heritage Research Project

## Project Description
This project is part of the course "The Art of Making Data Speak 
(Digital Tools and Methods)" at the Institut für Geschichte, 
Technische Universität Darmstadt. It explores open cultural 
heritage data as a source for historical and humanities research.

## Research Purpose
To analyse patterns in the Metropolitan Museum of Art's collection 
of Asian, Islamic, and Ancient Near Eastern objects — examining how 
artefacts are distributed across cultures, regions, and historical 
periods. This supports broader questions in digital humanities about 
how museum collections represent the world's cultural heritage.

## Research Question
How are Asian, Islamic, and Ancient Near Eastern cultural heritage 
objects distributed across cultures, countries, and historical 
periods in the MET Museum collection?

## Data Origin
**Source:** The Metropolitan Museum of Art Open Access  
**Dataset:** Asian Art, Islamic Art, Ancient Near Eastern Art departments  
**GitHub:** https://github.com/metmuseum/openaccess  
**License:** CC0 — No Rights Reserved. No permission required for any use.  
**License confirmation:** https://www.metmuseum.org/about-the-met/policies-and-documents/open-access  
**Date accessed:** 2026-05-06  
**File:** [asian_islamic_neareastern_met.csv](data/asian_islamic_neareastern_met.csv)

- Rows: 58,796
- Columns: 45
- File size: 23.49 MB

## Why This Source Was Chosen
The MET Open Access dataset was selected because:
- CC0 license — the most open license possible, no restrictions
- No API key or registration required
- Widely used and cited in digital humanities research
- Stable and regularly updated (weekly)
- Directly relevant to historical and cross-cultural analysis

## Data Collection Process
1. Attempted Wikidata SPARQL endpoint — returned 502 errors due 
   to ongoing Blazegraph backend migration (May 2026)
2. Considered V&A Museum API — excluded due to unclear 
   terms and conditions
3. Selected MET Museum open access CSV as the safest and most 
   appropriate source for open humanities research
4. Downloaded full MET dataset (484,956 rows) in chunks via 
   Jupyter Notebook to avoid memory issues
5. Filtered to three relevant departments:
   - Asian Art: 37,000 objects
   - Islamic Art: 15,573 objects
   - Ancient Near Eastern Art: 6,223 objects
6. Dropped 9 redundant columns (internal IDs, duplicate URLs)
7. Final dataset: 58,796 rows, 45 columns, 23.49 MB

## What Is Missing or Uncertain
- Many objects have no Period or Dynasty recorded
- Country and Region fields are inconsistently filled
- Artist information is missing for a large proportion of objects
- Date fields sometimes contain only approximate ranges
- The dataset reflects MET's collection — not a complete picture 
  of global heritage, as colonial collecting history shapes what 
  is held in Western museums

## Notes on Reproducibility
All data collection steps are documented in the Jupyter Notebook 
in the notebooks/ folder. The MET dataset is updated weekly — 
results may differ slightly if downloaded at a later date.

## Repository Structure
- `data/` — contains the raw filtered dataset
- `notebooks/` — contains Jupyter Notebook used for data collection

## Course Information
**Subject:** Open Scholarship in History and Humanities  
**Course:** The Art of Making Data Speak (Digital Tools and Methods)  
**Course Code:** 02-04-0130-ue  
**Institut für Geschichte, Technische Universität Darmstadt**  
**Instructor:** Dr. Nadezhda Povroznik  
**Semester:** Summer Semester 2026
