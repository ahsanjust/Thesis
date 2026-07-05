# Action Items - Meeting: June 30, 2026

---

## Tasks

### 1. Systematic Literature Search
- [x] Formulate search strategy across SCI-E/SSCI/SCIE journals (IEEE, Springer, MDPI, Elsevier, ACM, Wiley)
- [x] Draft search query strings
  - `"feature selection" AND ("filter" OR "wrapper" OR "embedded" OR "metaheuristic" OR "swarm intelligence")`
- [ ] Search databases:
  - [ ] Google Scholar
  - [ ] IEEE Xplore
  - [ ] SpringerLink
  - [ ] Scopus / Web of Science
  - [ ] ACM Digital Library
- [ ] Time window: Last 10 years (2016–2026), focus on 2020–2026
- [ ] Apply snowballing from relevant survey papers
- [ ] Filter by inclusion criteria:
  - [ ] Peer-reviewed journal/conference papers (SCI/SCIE/SSCI/ESCI)
  - [ ] English only
  - [ ] Feature selection algorithm or domain-specific application
- [ ] Exclude duplicates, preprints, non-relevant surveys

### 2. Paper Collection & Organization
- [ ] Create `papers/feature_selection_surveys/` folder
  - [ ] Organize PDFs by domain subfolders
  - [ ] Rename files using naming convention:
    `Domain_Year_Publisher_JournalTier_Topic.pdf`
- [ ] Create a master spreadsheet/table:
  - [ ] Columns: Title, Authors, Year, Venue, DOI, Category, Algorithm, Domain, Classifier, Dataset, Accuracy, Key Findings
  - [ ] Save as `papers/feature_selection_master_list.csv` or `.md`
- [ ] Document all excluded papers with reasons

### 3. Paper Categorization & Clustering
- [ ] Categorize each paper:
  - [ ] Algorithm type: Filter / Wrapper / Embedded / Metaheuristic / Hybrid
  - [ ] Specific technique name
- [ ] Cluster papers by domain:
  - [ ] Healthcare/Medical/Bioinformatics
  - [ ] Cybersecurity/IDS/IIoT
  - [ ] Image/Signal Processing
  - [ ] Finance/Economics
  - [ ] Software Engineering/Defect Prediction
  - [ ] Remote Sensing/IoT
  - [ ] Cross-domain/General
- [ ] Within each domain, summarize:
  - [ ] Common feature selection approaches used
  - [ ] Performance benchmarks
  - [ ] Gaps identified by the authors

### 4. Analysis & Synthesis
- [ ] Comparative analysis of algorithms across domains
- [ ] Identify trending algorithms and declining ones
- [ ] Identify research gaps and open challenges per domain
- [ ] Note high-performing combinations (e.g., PSO+RF, GWO+XGBoost)

### 5. Deliverable for Next Meeting (2026-07-07)
- [ ] Literature review summary document
  - [ ] Methodology
  - [ ] Results per domain
  - [ ] Summary tables
  - [ ] Research gaps
- [ ] Updated `papers/` directory with all gathered/renamed papers
- [ ] Master list of all reviewed papers

---

## Next Meeting
**Date**: 2026-07-07 (proposed)
**Preparation**: Literature review summary, master list of papers, analysis of research gaps
