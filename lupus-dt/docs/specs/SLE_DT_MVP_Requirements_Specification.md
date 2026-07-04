# SLE Digital Twin MVP Requirements Specification

## 1. Purpose and Project Definition

This document defines the technical and thesis-deliverable requirements for the Systemic Lupus Erythematosus Digital Twin (SLE-DT) MVP. The project will produce two final deliverables:

1. **A client-facing SLE-DT research application** with APIs and a machine-learning/digital-twin backend.
2. **A final publishable thesis paper** describing the scientific motivation, system architecture, methodology, validation results, limitations, and future work.

The MVP is a research system, not a clinical decision-support tool. It is designed to model SLE immune-state deviation from healthy controls, identify molecular endotypes, simulate pathway-level restoration toward a healthy immune state, and generate explainable candidate biological hypotheses.

---

## 2. Final MVP Scope

### 2.1 MVP Identity

The final MVP is:

> **A modular, FAIR-aligned, transcriptomics-first, molecular-endotype-aware, explainable SLE Immune Digital Twin for immune-state modeling and immune-tolerance-restoration hypothesis generation.**

### 2.2 In Scope

The MVP shall include:

- Public bulk transcriptomic datasets for SLE and healthy controls.
- Healthy reference immune-state modeling.
- Patient/sample-level SLE immune-state modeling.
- Differential expression analysis.
- Pathway enrichment or pathway scoring.
- Molecular endotype discovery.
- Disease-state deviation scoring.
- Virtual pathway-restoration simulation.
- Explainable pathway/target ranking.
- A client-facing research application.
- Backend APIs for data, model inference, simulation, and results retrieval.
- Verification and validation artifacts.
- A final publishable thesis paper.

### 2.3 Out of Scope

The MVP shall not include:

- Clinical deployment.
- Diagnosis, treatment recommendation, or medication selection.
- Patient-facing medical advice.
- Real-time monitoring.
- Wearables.
- EHR integration.
- Protected health information.
- Federated learning implementation.
- Multi-omics integration.
- TCR-seq model training.
- Drug-response simulation.
- Organ-specific or whole-body lupus simulation.
- Regulatory submission.

These items may be discussed as future work.

---

## 3. Literature-Driven Design Rationale

### 3.1 Transcriptomics-First MVP

The project remains transcriptomics-first because reviewed SLE DEG literature supports the use of public gene-expression datasets, healthy controls, differential gene expression, pathway enrichment, and PPI analysis for identifying reproducible SLE molecular mechanisms [1]–[6].

### 3.2 Molecular Endotype Requirement

Molecular stratification is required because SLE is heterogeneous, and the reviewed precision-rheumatology and SLE-personalized-treatment literature emphasizes biological subtyping as central to precision medicine [7], [10], [11].

### 3.3 Immune Digital Twin Framing

The system is framed as an Immune Digital Twin because reviewed IDT architecture literature states that immune twins should model both disease/pathology-specific events and immune-system responses [13].

### 3.4 Neutrophil, Interferon, B-Cell, and T-Cell Biology

The biological model must prioritize:

- Neutrophil activation, neutrophil-mediated immunity, and neutrophil degranulation from the SLE DEG review [1].
- Type-I interferon signaling from precision-rheumatology literature [7].
- B-cell/autoantibody biology and patient subtyping from SLE-personalized-treatment literature [10].
- T-cell and immune-repertoire modeling as future work, informed by deep-learning/TCR literature but not included in the MVP because the reviewed TCR paper did not include SLE [14].

### 3.5 Governance and Validation

Security, privacy, governance, and validation are requirements because healthcare AI and federated-learning literature emphasizes stakeholder review, privacy risk, security risk, access control, and lifecycle governance [12], [13]. For the MVP, these requirements are limited to public-data governance, reproducibility, traceability, and clear non-clinical-use statements.

---

## 4. Final Deliverable 1: Client-Facing SLE-DT Application

### 4.1 Application Goal

The client-facing application shall allow a user to explore SLE digital-twin outputs generated from public transcriptomic data. It should make the research workflow understandable through interactive visualizations, explainable rankings, and reproducible output summaries.

### 4.2 Primary Users

The MVP application is intended for:

- Thesis evaluators.
- Biomedical informatics researchers.
- Computational biology reviewers.
- Rheumatology or immunology advisors.
- Future collaborators evaluating the research platform.

It is not intended for patients or clinical decision-making.

### 4.3 Required User Workflows

The application shall support the following workflows:

1. **Dataset Overview**
   - View datasets used.
   - View sample counts, controls, SLE samples, data source, and preprocessing status.

2. **Healthy Reference Twin Exploration**
   - View healthy baseline pathway activity.
   - View baseline gene-expression summary.

3. **SLE Patient/Sample Twin Exploration**
   - Select a patient/sample or representative sample.
   - View immune-state deviation from healthy baseline.
   - View activated or suppressed pathways.

4. **Molecular Endotype Exploration**
   - View molecular clusters/endotypes.
   - Compare pathway activity across endotypes.
   - View endotype-specific disease drivers.

5. **Virtual Restoration Simulation**
   - Select a pathway or ranked pathway set.
   - Simulate partial restoration toward healthy-state activity.
   - View predicted reduction in distance-to-health.

6. **Explainable Target/Pathway Ranking**
   - View ranked pathways and candidate genes.
   - View evidence supporting each ranking.
   - View DEG, pathway, network, and restoration-score contributions.

7. **Export Results**
   - Export summary tables.
   - Export figures for thesis/paper use.
   - Export model run metadata.

### 4.4 Required UI Views

The client-facing application shall include:

- Landing / project overview page.
- Dataset inventory page.
- Healthy reference twin page.
- Patient/sample twin page.
- Molecular endotype dashboard.
- Pathway deviation dashboard.
- Virtual perturbation / restoration simulation page.
- Explainable ranking page.
- Validation summary page.
- Export/download page.

### 4.5 Required Visualizations

The application should include, where feasible:

- Heatmap of pathway activity across samples/endotypes.
- Healthy vs SLE pathway deviation plot.
- Endotype clustering visualization.
- Ranked pathway/target bar chart.
- Restoration-score plot.
- Gene/pathway contribution table.
- Validation summary table.

---

## 5. Final Deliverable 1: API Requirements

### 5.1 API Role

The API layer shall separate the client application from the analysis/model layer. It should expose reproducible endpoints for retrieving datasets, model outputs, pathway scores, endotypes, simulations, and validation results.

### 5.2 Required API Endpoints

The MVP API should include endpoints equivalent to:

```text
GET /api/health
GET /api/datasets
GET /api/datasets/{dataset_id}/summary
GET /api/reference/healthy
GET /api/twins
GET /api/twins/{sample_id}
GET /api/twins/{sample_id}/deviation
GET /api/endotypes
GET /api/endotypes/{endotype_id}
GET /api/pathways
GET /api/pathways/rankings
POST /api/simulations/pathway-restoration
GET /api/simulations/{simulation_id}
GET /api/validation/technical
GET /api/validation/biological
GET /api/exports/{run_id}
```

### 5.3 API Output Requirements

API responses should include:

- Data payload.
- Method metadata.
- Model/run identifier.
- Timestamp or version identifier.
- Dataset provenance.
- Warning that outputs are research hypotheses, not medical recommendations.

### 5.4 API Non-Requirements

The MVP API does not need:

- Authentication for protected patient data.
- EHR integration.
- Real-time streaming.
- Federated training endpoints.
- Clinical decision-support workflow endpoints.

---

## 6. Final Deliverable 1: Machine-Learning and Digital-Twin Model Requirements

### 6.1 Model Objective

The model shall represent each SLE sample/patient as an immune-state twin and compare that state to a healthy reference twin.

### 6.2 Data Inputs

Required MVP inputs:

- Public SLE transcriptomic expression matrix.
- Healthy control expression matrix.
- Gene identifiers.
- Dataset metadata.
- Pathway definitions.

Optional, if available:

- Disease activity metadata.
- Organ involvement metadata.
- Treatment metadata.

### 6.3 Preprocessing Requirements

The preprocessing pipeline shall include:

1. Dataset ingestion.
2. Quality-control checks.
3. Normalization.
4. Gene identifier harmonization.
5. Missing-data handling.
6. Batch-effect assessment and correction where applicable.
7. Dataset provenance documentation.
8. Output of processed expression matrix.

### 6.4 Feature Engineering Requirements

The model shall generate:

- Gene-level differential-expression features.
- Expression deviation scores.
- Pathway activity scores.
- Healthy reference pathway profile.
- Patient/sample pathway profile.
- Distance-to-health metrics.
- Endotype labels.
- Candidate target/pathway features.

### 6.5 Healthy Reference Twin

The healthy reference twin shall represent baseline immune-state behavior using healthy control transcriptomic profiles.

Required outputs:

- Healthy gene-expression baseline.
- Healthy pathway-activity baseline.
- Healthy variance or confidence estimates where feasible.

### 6.6 Patient/Sample Immune-State Twin

Each patient/sample twin shall represent deviation from the healthy reference.

Required outputs:

- Gene-level deviation profile.
- Pathway-level deviation profile.
- Endotype assignment.
- Ranked abnormal pathways.
- Distance-to-health score.

### 6.7 Molecular Endotype Model

The model shall cluster or stratify SLE samples into molecular endotypes using transcriptomic/pathway features.

Required outputs:

- Endotype labels.
- Endotype-level pathway signatures.
- Endotype-specific candidate drivers.
- Endotype stability evaluation.

### 6.8 Virtual Perturbation Engine

The perturbation engine shall simulate pathway-level restoration by adjusting abnormal pathway scores toward the healthy reference.

Required outputs:

- Baseline distance-to-health.
- Post-perturbation distance-to-health.
- Restoration score.
- Ranked pathways by predicted restoration impact.

### 6.9 Explainable Ranking Engine

The ranking engine shall prioritize pathways and candidate targets using interpretable evidence.

Ranking factors may include:

- Differential-expression strength.
- Pathway deviation magnitude.
- Network/PPI centrality.
- Endotype specificity.
- Restoration score.
- Cross-dataset reproducibility.
- Literature-supported relevance.

Required outputs:

- Ranked pathway list.
- Ranked candidate genes where supported.
- Explanation for each ranking.
- Evidence source breakdown.

---

## 7. Verification and Validation Requirements

### 7.1 Verification Goal

Verification confirms that the system was built correctly and that each module performs its intended function.

### 7.2 Verification Deliverables

The project shall produce:

- Dataset inventory.
- Preprocessing log.
- DEG parameter log.
- Pathway database/version log.
- PPI source log.
- Endotype method log.
- Twin construction method description.
- Perturbation method description.
- Ranking/scoring method description.
- API endpoint documentation.
- Reproducibility instructions.
- Known limitations statement.

### 7.3 Technical Validation

Technical validation shall evaluate:

- Reproducibility of preprocessing and model outputs.
- Stability of pathway rankings.
- Cross-dataset consistency.
- Sensitivity to preprocessing choices.
- Endotype robustness.
- API response correctness.
- Application-to-API integration correctness.

### 7.4 Biological Validation

Biological validation shall verify whether the system recovers known SLE-relevant biology:

- Neutrophil activation / degranulation / neutrophil-mediated immunity [1].
- Type-I interferon signaling [7].
- B-cell-related immune signatures [10].
- Published hub genes from DEG/PPI literature: CCNB2, CDCA8, AURKB, BUB1B, RRM2, BIRC5, UBE2C [1].

### 7.5 Endotype Validation

Endotype validation shall assess:

- Cluster stability.
- Cohort reproducibility.
- Biological interpretability.
- Within-endotype pathway consistency.
- Differences in pathway ranking across endotypes.

### 7.6 Application Validation

The client-facing application shall be validated by confirming:

- All required pages load successfully.
- API calls return expected outputs.
- Visualizations match backend results.
- Exported tables/figures match model outputs.
- Medical-use disclaimers are visible.

### 7.7 Acceptance Criteria

The MVP is complete only if it demonstrates:

- Successful construction of a healthy reference twin.
- Successful construction of patient/sample immune-state twins.
- Reproducible DEG and pathway outputs.
- At least one interpretable molecular endotype analysis.
- A documented twin-comparison method.
- A documented virtual-perturbation method.
- Ranked candidate pathways/targets with explainability evidence.
- Recovery or clear discussion of known SLE mechanisms.
- A working client-facing application.
- Working API endpoints.
- Clear separation between research hypotheses and clinical recommendations.
- A completed publishable paper draft.

---

## 8. Governance, Ethics, and Responsible AI Requirements

### 8.1 MVP Governance

Because the MVP uses public datasets only and does not process protected health information, production healthcare compliance workflows are not required. However, the system shall still include:

- Dataset provenance documentation.
- Dataset usage documentation.
- Reproducibility documentation.
- Code and model traceability.
- Non-clinical-use disclaimer.
- Documentation of model limitations.

### 8.2 Security and Privacy Scope

The MVP shall not process PHI. Future versions involving clinical or institutional data should incorporate:

- Access control.
- Encryption.
- Threat modeling.
- Privacy impact assessment.
- Security review.
- Governance approval workflows.

### 8.3 Future Federated Learning

Federated learning may support future multi-institutional SLE-DT development, but it is not part of the MVP. Reviewed literature emphasizes that federated learning does not eliminate privacy risk because model updates can leak sensitive information [12].

---

## 9. Development Plan From Inception to Thesis Completion

### Phase 1: Requirements and Literature Consolidation

Deliverables:

- Final requirements specification.
- Dataset selection criteria.
- Final MVP scope.
- Thesis research questions.

### Phase 2: Data Pipeline

Deliverables:

- Dataset inventory.
- Data ingestion scripts.
- Preprocessing workflow.
- Quality-control report.
- Processed expression matrix.

### Phase 3: Model Development

Deliverables:

- Healthy reference twin.
- Patient/sample twin representation.
- Pathway scoring model.
- Endotype model.
- Virtual perturbation engine.
- Explainable ranking engine.

### Phase 4: Application and API Development

Deliverables:

- Backend API.
- Client-facing dashboard.
- Visualization components.
- Export functions.
- API documentation.

### Phase 5: Verification and Validation

Deliverables:

- Technical validation report.
- Biological validation report.
- Endotype validation report.
- Application validation checklist.
- Reproducibility package.

### Phase 6: Thesis Paper and Publication Package

Deliverables:

- Final publishable paper.
- Figures and tables.
- Methods appendix.
- Limitations and future work section.
- GitHub/repository documentation if applicable.

---

## 10. Final Deliverable 2: Publishable Paper Requirements

### 10.1 Paper Goal

The final paper shall describe the SLE-DT MVP as a reproducible, explainable, transcriptomics-first Immune Digital Twin framework for SLE immune-state modeling and tolerance-restoration hypothesis generation.

### 10.2 Recommended Paper Structure

1. **Title**
   - Example: *A Transcriptomics-First Molecular-Endotype-Aware Immune Digital Twin for Systemic Lupus Erythematosus*

2. **Abstract**
   - SLE motivation.
   - Digital-twin objective.
   - Dataset/method overview.
   - MVP contributions.
   - Key validation results.

3. **Introduction**
   - SLE heterogeneity.
   - Need for precision modeling.
   - Digital twins and immune-state modeling.
   - Thesis contribution.

4. **Related Work**
   - SLE DEG/pathway literature.
   - AI and biomarkers in rheumatology.
   - Immune Digital Twins.
   - Digital health/governance.
   - Deep learning/TCR work as future context.

5. **Methods**
   - Datasets.
   - Preprocessing.
   - DEG analysis.
   - Pathway scoring.
   - Endotype discovery.
   - Healthy reference twin construction.
   - Patient twin construction.
   - Virtual perturbation.
   - Explainability and ranking.

6. **System Architecture**
   - Client application.
   - APIs.
   - ML/digital-twin backend.
   - Data/model artifacts.

7. **Validation**
   - Technical validation.
   - Biological validation.
   - Endotype validation.
   - Application/API validation.

8. **Results**
   - DEG/pathway results.
   - Endotype results.
   - Twin comparison examples.
   - Perturbation ranking results.
   - Biological interpretation.

9. **Discussion**
   - Interpretation of findings.
   - How results align with SLE literature.
   - MVP value and limitations.
   - Why future modules are deferred.

10. **Limitations**
    - Public datasets only.
    - Bulk transcriptomics only.
    - No clinical validation.
    - No treatment recommendation.
    - Dataset heterogeneity.
    - No SLE-specific TCR modeling in MVP.

11. **Future Work**
    - Multi-omics.
    - Single-cell.
    - TCR repertoire modeling.
    - Federated learning.
    - EHR/wearable integration.
    - Drug-response modeling.

12. **Conclusion**
    - Summary of MVP contribution.
    - Research value.
    - Path toward future SLE Digital Twin development.

### 10.3 Required Paper Figures

The final paper should include:

- SLE-DT architecture diagram.
- Data-processing pipeline diagram.
- Healthy-vs-SLE twin comparison diagram.
- Molecular endotype visualization.
- Pathway ranking visualization.
- Virtual perturbation/restoration diagram.
- Client application screenshot or wireframe.

### 10.4 Required Paper Tables

The final paper should include:

- Dataset inventory table.
- MVP vs future-work scope table.
- Pathway/target ranking table.
- Validation metrics table.
- Literature-to-requirements traceability table.

---

## 11. Final MVP Acceptance Checklist

The project is ready for final submission when all items below are complete:

- [ ] Public datasets selected and documented.
- [ ] Preprocessing pipeline implemented.
- [ ] Healthy reference twin implemented.
- [ ] Patient/sample immune-state twin implemented.
- [ ] Pathway scoring implemented.
- [ ] Molecular endotype discovery implemented.
- [ ] Virtual perturbation implemented.
- [ ] Explainable ranking implemented.
- [ ] Backend API implemented.
- [ ] Client-facing application implemented.
- [ ] Validation report completed.
- [ ] Biological interpretation completed.
- [ ] Paper figures generated.
- [ ] Publishable paper drafted.
- [ ] Limitations clearly documented.
- [ ] Non-clinical-use disclaimer included.

---

## 12. References (IEEE)

[1] Y. Zhao et al., “Identification of Biomarkers and Pathways in Systemic Lupus Erythematosus Through Integrated Bioinformatics Analysis,” 2021.

[2] GSE162828, Gene Expression Omnibus.

[3] GSE169080, Gene Expression Omnibus.

[4] STRING Database.

[5] Cytoscape Network Analysis Platform.

[6] M. E. Ritchie et al., “limma: Linear Models for Microarray and RNA-Seq Data Analysis.”

[7] “Artificial Intelligence, Biomarkers, and Precision Medicine in Autoimmune Inflammatory Rheumatic Diseases.”

[8] “Digital Twins and the Metaverse in Healthcare and Industry.”

[9] “Artificial Intelligence and Autoimmune Disease Research Trends,” 2025.

[10] “AI for Systemic Lupus Erythematosus Personalized Treatment.”

[11] “The Role of Health Information Technology in the Control and Management of Systemic Lupus Erythematosus.”

[12] “Federated Learning Security and Governance in Healthcare.”

[13] A. Niarakis et al., “Immune digital twins for complex human pathologies: applications, limitations, and challenges,” npj Systems Biology and Applications, vol. 10, no. 1, Art. no. 141, 2024, doi: 10.1038/s41540-024-00450-5.

[14] D. Yang, X. Peng, S. Zheng, and S. Peng, “Deep learning-based prediction of autoimmune diseases,” Scientific Reports, vol. 15, no. 1, 2025, doi: 10.1038/s41598-025-88477-4.
