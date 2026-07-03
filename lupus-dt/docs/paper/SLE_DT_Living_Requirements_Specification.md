# SLE Digital Twin Living Requirements Specification (SLE-DT LRS)

## Document Purpose
This document serves as the authoritative living requirements specification for the SLE Digital Twin research program. Future literature reviews, biological discoveries, datasets, and architectural decisions should be merged into this specification while preserving traceability and rationale.

---

## Current Canonical Thesis Scope
### Selected Architecture Direction
**Transcriptomics-First + Molecular-Endotype-Aware Digital Twin**

Rationale:
- Transcriptomics is the strongest currently validated evidence layer.
- Molecular heterogeneity is a core challenge in SLE.
- Molecular endotypes provide a feasible balance between novelty and thesis scope.
- Multi-modal Digital Twin capabilities remain future expansion areas.

### Research Positioning
The SLE-DT is:
- Explainable.
- Patient-specific.
- Immune-tolerance-restoration focused.
- Molecular-endotype aware.
- Neutrophil-pathway aware.
- Interferon-signature aware.
- Target prioritization focused.
- Research-oriented rather than a clinical product.

---

## Executive Thesis Objective
Develop an explainable, patient-specific, transcriptomics-first Digital Twin for Systemic Lupus Erythematosus (SLE) that models immune dysregulation, identifies disease-driving pathways, simulates restoration of immune tolerance, and prioritizes candidate therapeutic targets.

## MVP Definition
### Included
- Public SLE transcriptomic datasets.
- Healthy vs SLE state modeling.
- Differential expression analysis.
- Pathway activity analysis.
- PPI network analysis.
- Healthy reference twin.
- Patient-specific twin.
- Molecular endotype stratification.
- Virtual pathway perturbation.
- Explainable target prioritization.
- Cross-dataset validation.

### Explicitly Out of Scope
- Clinical deployment.
- Drug prescribing.
- Regulatory-grade decision support.
- Wet-lab validation.
- Real-time monitoring.
- Wearable integration.
- Imaging integration.
- Multi-omics integration.

---

## Architecture Evolution Roadmap
### Phase 1 (Current MVP)
- Transcriptomics.
- Molecular endotypes.
- Healthy twin.
- Patient twin.
- Pathway restoration simulation.
- Target ranking.

### Phase 2 (Candidate Expansion)
- Proteomics.
- Cytokine signatures.
- Serologic biomarkers.
- Composite biomarker scoring.
- Therapy-response prediction.

### Phase 3 (Longitudinal Digital Twin)
- EHR integration.
- Wearables.
- Digital biomarkers.
- Continuous recalibration.
- Drift monitoring.
- Longitudinal patient models.

---

## Scientific Foundation
### Immune Tolerance Restoration
Primary system objective is restoration of immune homeostasis rather than disease prediction.

### Neutrophil Biology
Mandatory pathway categories:
- Neutrophil activation.
- Neutrophil-mediated immunity.
- Neutrophil degranulation.

### Hub Genes
Priority monitoring targets:
- CCNB2
- CDCA8
- AURKB
- BUB1B
- RRM2
- BIRC5
- UBE2C

### Interferon Biology
The Type-I interferon axis shall be modeled as a first-class pathway due to its relevance to molecular stratification and treatment response.

---

## Research Questions
### Primary Question
Can an explainable transcriptomic Digital Twin identify pathways whose correction most effectively restores an SLE immune state toward a healthy immune state?

### Secondary Questions
- Which pathways explain the largest disease-state deviation?
- Are neutrophil pathways consistently dominant?
- Are interferon-signature endotypes observable?
- Which genes remain reproducibly important across cohorts?
- Can restoration-oriented ranking generate biologically plausible targets?

---

## Data Strategy
### Core Datasets
- GSE162828
- GSE169080

### Optional Future Sources
- ImmPort
- ArrayExpress
- Additional GEO SLE datasets

### Diversity Requirements
Capture where available:
- Age
- Sex
- Ethnicity/ancestry
- Disease subtype
- Clinical metadata

---

## Molecular Endotype Stratification
### Purpose
Identify biologically distinct SLE subpopulations.

### MVP Endotype Signals
- Gene-expression similarity.
- Pathway activity profiles.
- Interferon activity.
- Immune pathway activation patterns.

### Deliverables
- Patient clusters.
- Endotype definitions.
- Endotype-specific disease drivers.

---

## Biomarker Framework
### MVP Biomarkers
- DEGs.
- Pathway signatures.
- Hub genes.
- Endotype signatures.

### Future Biomarkers
- Proteomic biomarkers.
- Cytokine panels.
- Serologic biomarkers.
- Imaging biomarkers.
- Digital biomarkers.

### Design Principle
Composite biomarkers should be treated as the preferred long-term direction.

---

## Data Processing Pipeline
1. Dataset acquisition.
2. QC.
3. Normalization.
4. Batch correction.
5. DEG analysis.
6. Pathway scoring.
7. Network construction.
8. Endotype identification.
9. Twin generation.

---

## Healthy Reference Twin
- Healthy transcriptomic profile.
- Healthy pathway profile.
- Healthy network profile.

## Patient Digital Twin
Layers:
- Gene layer.
- Pathway layer.
- Network layer.
- Explainability layer.
- Molecular endotype layer.

## Twin Comparison Engine
Outputs:
- Disease-driving genes.
- Disease-driving pathways.
- Network disruptions.
- Candidate restoration opportunities.

## Virtual Perturbation Engine
Simulations:
- Single-pathway restoration.
- Multi-pathway restoration.
- Hub-gene adjustment.

Outputs:
- Restoration score.
- Distance-to-health reduction.
- Pathway impact ranking.

## Explainability Framework
Every recommendation should provide:
- Responsible genes.
- Responsible pathways.
- Transcriptomic evidence.
- Literature support.
- Endotype context.

## Target Ranking Framework
Factors:
- DEG strength.
- Pathway influence.
- Network centrality.
- Restoration impact.
- Cross-dataset reproducibility.

Outputs:
- Ranked pathways.
- Ranked genes.
- Ranked restoration hypotheses.

---

## Responsible AI and Governance
### Standards
- TRIPOD+AI alignment.
- PROBAST+AI considerations.

### Fairness Requirements
- Population representation review.
- Generalizability assessment.
- Bias documentation.

### Future Operational Requirements
- Drift monitoring.
- Recalibration.
- Periodic validation.

---

## Validation Strategy
### Technical
- Reproducibility.
- Stability analysis.
- Sensitivity analysis.

### Biological
Recover:
- Neutrophil pathways.
- Interferon pathways.
- Hub genes.
- Published biomarkers.

---

## Open Research Questions
1. Can deep learning outperform DEG-to-PPI workflows?
2. Which hub genes remain important under graph-learning approaches?
3. Can ML recover biologically meaningful genes removed by filtering thresholds?
4. How accurately can transcriptomics alone predict therapeutic targets?
5. Are longitudinal SLE cohorts publicly accessible?
6. How should drift-monitoring be implemented in production Digital Twins?
7. Can subtype-specific twins outperform generalized twins?
8. How should wearable biomarkers be integrated?
9. Which public datasets include longitudinal molecular and digital-health data?
10. What minimum biomarker combination is required for a clinically useful Lupus Digital Twin?
11. Has a fully customizable patient-specific SLE Digital Twin already been demonstrated?

---

## Expected Thesis Contributions
- Explainable SLE Digital Twin architecture.
- Immune-tolerance restoration framework.
- Molecular-endotype-aware SLE modeling.
- Neutrophil-centric pathway prioritization.
- Reproducible research platform.
- Publishable biological hypotheses.

---

## References (IEEE)
[1] Y. Zhao et al., “Identification of Biomarkers and Pathways in Systemic Lupus Erythematosus Through Integrated Bioinformatics Analysis,” 2021.
[2] GSE162828, GEO.
[3] GSE169080, GEO.
[4] STRING Database.
[5] Cytoscape.
[6] M. E. Ritchie et al., limma.
[7] Artificial Intelligence, Biomarkers, and Precision Medicine in Autoimmune Inflammatory Rheumatic Diseases.
