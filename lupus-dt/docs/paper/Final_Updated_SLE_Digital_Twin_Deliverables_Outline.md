# Final Deliverables Outline: Explainable Gene-Expression-Based Digital Twin for Immune Tolerance Restoration in Systemic Lupus Erythematosus (SLE)

## 1. Thesis Vision
Develop a software-only, explainable SLE Digital Twin (SLE-DT) that uses publicly available transcriptomic data to:
- Model patient-specific immune-state deviations.
- Compare disease-state and healthy-state immune behavior.
- Identify disease-driving pathways and genes.
- Simulate virtual restoration of abnormal immune pathways.
- Prioritize candidate tolerance-restoration targets.
- Generate biologically interpretable hypotheses for future experimental validation.

### MVP Scope (Required)
- Bulk transcriptomic data only.
- Public datasets only (GEO).
- Healthy vs SLE comparison.
- Pathway-level digital twin.
- Explainable target ranking.
- Literature-supported validation.

### Out of Scope
- Clinical deployment.
- Wet-lab validation.
- Drug prescribing.
- Real-time patient monitoring.
- Regulatory-grade decision support.
- Multi-omics integration.
- Single-cell digital twins.

---

## 2. Scientific Foundation

### Immune Tolerance Focus
The digital twin should be framed around restoration of immune tolerance rather than disease prediction alone.

### Key Biological Insight From Literature Review
The reviewed study identified:
- 790 reproducible differentially expressed genes (DEGs).
- Consistent enrichment of:
  - Neutrophil activation
  - Neutrophil-mediated immunity
  - Neutrophil degranulation
- Hub genes:
  - CCNB2
  - CDCA8
  - AURKB
  - BUB1B
  - RRM2
  - BIRC5
  - UBE2C

Implication:
Neutrophil dysregulation should be treated as a first-class disease mechanism within the digital twin architecture.

---

## 3. Research Questions

### Primary Research Question
Can an explainable transcriptomic digital twin identify biological pathways whose correction most effectively restores an SLE immune system toward a healthy reference state?

### Secondary Questions
1. Which pathways contribute most strongly to deviation from healthy immune behavior?
2. Are neutrophil-related pathways consistently prioritized across patients?
3. Can pathway-level perturbation simulations generate biologically plausible restoration hypotheses?
4. Which genes and pathways show reproducible importance across independent datasets?
5. Does patient-specific modeling provide advantages over cohort-average analysis?

---

## 4. Gap Analysis

### Existing Work
- Biomarker discovery.
- Flare prediction.
- Treatment response prediction.
- DEG analysis.
- PPI analysis.

### Remaining Gap
Current studies identify biomarkers but do not:
- Build patient-specific digital twins.
- Quantify distance from healthy immune states.
- Simulate tolerance restoration.
- Rank interventions based on restoration potential.

### Gap Addressed By MVP
Create an explainable restoration-oriented digital twin that converts transcriptomic observations into actionable biological hypotheses.

---

## 5. Data Strategy

### Primary Datasets
#### GEO
- GSE162828
- GSE169080

### Optional Expansion Datasets
- Additional GEO SLE cohorts.
- ImmPort datasets.
- ArrayExpress lupus datasets.

### Dataset Inclusion Criteria
- Human SLE samples.
- Healthy control cohort.
- Raw or normalized expression data available.
- Sufficient sample metadata.

### Data Governance
- Publicly available datasets only.
- Reproducible acquisition pipeline.
- Dataset version tracking.

### Known Limitations
- Batch effects.
- Cohort heterogeneity.
- Missing metadata.
- Treatment-history variability.

---

## 6. Data Preprocessing Pipeline

### Steps
1. Data ingestion.
2. Quality assessment.
3. Normalization.
4. Gene identifier harmonization.
5. Batch-effect correction.
6. Feature filtering.
7. Dataset integration.

### Deliverables
- Reproducible preprocessing workflow.
- Dataset quality report.
- Integrated expression matrix.

---

## 7. Biological Feature Engineering

### Gene-Level Features
- Differential expression.
- Expression z-scores.
- Disease vs healthy deviation measurements.

### Pathway-Level Features
#### Core Pathways
- Neutrophil activation.
- Neutrophil degranulation.
- Neutrophil-mediated immunity.

#### Additional Immune Pathways
- Interferon signaling.
- Cytokine signaling.
- Adaptive immunity pathways.
- Innate immunity pathways.

### Network Features
- Protein-protein interaction connectivity.
- Hub gene centrality.
- Pathway influence scores.

### Distance Metrics
- Patient-to-healthy distance.
- Pathway deviation score.
- Global immune-state deviation score.

---

## 8. Healthy Reference Twin

### Purpose
Construct a baseline healthy immune-state representation.

### Outputs
- Healthy pathway activity profile.
- Healthy gene-expression profile.
- Healthy network topology.

---

## 9. Patient Digital Twin

### Purpose
Represent a patient-specific disease state.

### Components
- Gene-expression layer.
- Pathway layer.
- Network layer.
- Explainability layer.

### Patient Profile Generated
- Activated pathways.
- Suppressed pathways.
- Candidate disease drivers.
- Deviation from healthy baseline.

---

## 10. Twin Comparison Layer

### Comparative Analysis
Healthy Twin vs Patient Twin

### Outputs
- Deviated pathways.
- Deviated genes.
- Network disruptions.
- Candidate restoration opportunities.

---

## 11. Explainable Disease Mechanism Layer

### Goal
Translate transcriptomic differences into interpretable biological explanations.

### Required Explanations
- Why a pathway is abnormal.
- Which genes drive the abnormality.
- Relationship to known SLE biology.
- Relationship to neutrophil dysregulation when applicable.

---

## 12. Virtual Perturbation Engine

### Purpose
Estimate whether correcting biological abnormalities moves the patient closer to a healthy state.

### Simulations
#### Single-Pathway Perturbation
- Suppress pathway.
- Enhance pathway.

#### Multi-Pathway Perturbation
- Top 2 pathways.
- Top 5 pathways.
- Combined restoration scenarios.

### Restoration Score
Measurement of predicted movement toward healthy-state behavior.

---

## 13. Target Prioritization Engine

### Ranking Inputs
- Differential expression evidence.
- Pathway influence.
- Network importance.
- Restoration impact.
- Cross-dataset reproducibility.

### Candidate Categories
#### Gene Targets
- CCNB2
- CDCA8
- AURKB
- BUB1B
- RRM2
- BIRC5
- UBE2C

#### Pathway Targets
- Neutrophil activation.
- Neutrophil degranulation.
- Neutrophil-mediated immunity.
- Other significantly enriched immune pathways.

### Outputs
- Ranked pathway list.
- Ranked gene list.
- Patient-specific restoration recommendations.

---

## 14. AI Extension Layer (Stretch Goal)

### Purpose
Investigate limitations identified in traditional DEG→PPI workflows.

### Candidate Methods
- Autoencoders.
- Graph Neural Networks.
- Network embeddings.
- Representation learning.

### Comparative Evaluation
Compare against:
- Traditional DEG analysis.
- PPI network prioritization.

This remains secondary to the MVP.

---

## 15. System Architecture

### Modules
1. Data ingestion.
2. Preprocessing.
3. Feature engineering.
4. Healthy twin generation.
5. Patient twin generation.
6. Twin comparison.
7. Perturbation simulation.
8. Target ranking.
9. Visualization dashboard.

### Data Flow
Input Data → Preprocessing → Features → Healthy Twin → Patient Twin → Twin Comparison → Simulation → Ranking → Dashboard

---

## 16. Visualization Dashboard

### Required Visuals
- Pathway activity heatmaps.
- Healthy vs patient comparison charts.
- Gene-expression summaries.
- PPI/network visualization.
- Restoration-score rankings.

### Explainability Views
- Gene contribution scores.
- Pathway influence breakdown.
- Simulation outcome explanations.

---

## 17. Validation Strategy

### Technical Validation
- Pipeline reproducibility.
- Sensitivity analysis.
- Ranking stability.
- Cross-dataset agreement.

### Biological Validation
Compare findings with:
- Known SLE genes.
- Known SLE pathways.
- Literature-supported mechanisms.

### Validation Questions
- Are neutrophil pathways consistently recovered?
- Are known hub genes prioritized?
- Are restoration recommendations biologically plausible?

---

## 18. Evaluation Metrics

### Data Metrics
- Number of usable samples.
- Number of integrated datasets.

### Model Metrics
- Ranking stability.
- Reproducibility.
- Cross-cohort consistency.

### Biological Metrics
- Recovery of known biomarkers.
- Recovery of literature-supported pathways.
- Recovery of hub genes.

---

## 19. Thesis Deliverables

### Software Deliverables
- Data pipeline.
- Digital twin framework.
- Simulation framework.
- Visualization dashboard.
- Documentation.

### Research Deliverables
- Literature review.
- Dataset inventory.
- Biological analysis.
- Case studies.
- Validation study.

### Publication Deliverables
- Thesis manuscript.
- Conference paper draft.
- Journal manuscript draft.
- Open-source repository.

---

## 20. Risks and Mitigations

### Risk
Dataset heterogeneity.

### Mitigation
Batch correction and cross-dataset validation.

### Risk
Limited clinical metadata.

### Mitigation
Focus initial MVP on transcriptomics.

### Risk
Biological overinterpretation.

### Mitigation
Require literature-supported evidence for conclusions.

---

## 21. Open Research Questions

The literature review explicitly identified the following unanswered questions. They remain open because the reviewed article did not answer them:

1. Can modern deep learning models outperform traditional DEG-to-PPI workflows for identifying SLE biomarkers?
2. Which hub genes remain important when analyzed using neural-network or graph-based learning approaches?
3. Can machine learning identify disease-associated genes excluded by conventional FDR and fold-change thresholds?
4. How effectively can AI predict therapeutic targets from transcriptomic data alone?

These questions should be listed as future research directions rather than thesis MVP requirements.

---

## 22. Future Work Beyond MVP

- Multi-omics integration.
- Proteomics integration.
- Epigenetic modeling.
- Single-cell sequencing support.
- Drug-response simulation.
- Causal pathway modeling.
- Longitudinal patient twins.
- Cross-autoimmune-disease extension.

---

## 23. References (IEEE Style)

[1] Y. Zhao et al., “Identification of Biomarkers and Pathways in Systemic Lupus Erythematosus Through Integrated Bioinformatics Analysis,” 2021. Source reviewed in literature review document.

[2] GEO Dataset GSE162828.

[3] GEO Dataset GSE169080.

[4] STRING: Search Tool for the Retrieval of Interacting Genes/Proteins.

[5] Cytoscape Network Analysis Platform.

[6] Ritchie et al., limma: Linear Models for Microarray and RNA-Seq Data Analysis.
