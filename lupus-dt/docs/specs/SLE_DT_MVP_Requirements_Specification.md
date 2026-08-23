# SLE Digital Twin MVP Requirements Specification (Reduced Thesis Scope)

## 1. Purpose and Project Definition

This document defines the minimum viable scope for the Systemic Lupus Erythematosus Digital Twin (SLE-DT) Master's thesis project.

The project will produce two deliverables:

- A research prototype demonstrating a transcriptomics-based immune digital twin for SLE.
- A publishable Master's thesis paper describing the methodology, implementation, validation, results, limitations, and future work.

The MVP is a research and hypothesis-generation tool only. It is not intended for clinical diagnosis, treatment recommendation, or patient care.

---

## 2. Final MVP Scope

### 2.1 MVP Identity

The final MVP is:

**A transcriptomics-based immune digital twin that measures how far an SLE immune state deviates from a healthy reference state and estimates how pathway normalization could restore immune health.**

### 2.2 In Scope

The MVP shall include:

- One public SLE transcriptomic dataset.
- Healthy control samples.
- SLE patient/sample data.
- Basic preprocessing and quality control.
- Healthy reference twin construction.
- Patient/sample twin construction.
- Pathway activity scoring.
- Distance-to-health calculation.
- Simple molecular endotype exploration.
- Virtual pathway restoration simulation.
- Streamlit-based research dashboard.
- Verification and validation documentation.
- Final publishable thesis paper.

### 2.3 Out of Scope

The MVP shall not include:

- Clinical deployment.
- Clinical decision support.
- Drug recommendation.
- Drug-response simulation.
- Multi-omics integration.
- Wearables.
- EHR integration.
- Real-time monitoring.
- Federated learning.
- Large-scale explainability engines.
- Protein interaction network analysis.
- Complex ranking frameworks.
- Production APIs.
- Multi-dataset benchmarking.

These items may be discussed as future work.

---

## 3. Thesis Research Question

### Primary Question

Can a transcriptomics-based immune digital twin quantify how far an SLE immune state deviates from a healthy immune state?

### Secondary Question

Can pathway-level virtual restoration move an SLE immune-state representation closer to a healthy reference state?

---

## 4. Final Deliverable 1: Research Application

### 4.1 Application Goal

The application shall allow users to:

- Explore healthy immune-state baselines.
- Explore SLE immune-state deviations.
- Compare patient samples against healthy references.
- Simulate pathway restoration.
- Review validation evidence.

### 4.2 Primary Users

- Thesis committee members.
- Biomedical engineering faculty.
- Bioinformatics researchers.
- Computational biology reviewers.
- Future collaborators.

### 4.3 Required User Workflows

#### Dataset Overview

Users shall be able to:

- View dataset information.
- View sample counts.
- View preprocessing status.

#### Healthy Reference Twin

Users shall be able to:

- View healthy pathway activity.
- View healthy baseline summaries.

#### Patient Twin

Users shall be able to:

- Select an SLE sample.
- View pathway deviations.
- View distance-to-health score.

#### Endotype Exploration

Users shall be able to:

- View sample clusters.
- Compare clusters using pathway activity.

#### Virtual Restoration Simulation

Users shall be able to:

- Select a pathway.
- Adjust the pathway toward healthy values.
- Observe resulting distance-to-health changes.

#### Validation Review

Users shall be able to:

- View biological validation results.
- View technical validation results.

### 4.4 Required UI Views

- Overview page.
- Healthy Reference Twin page.
- Patient Twin page.
- Endotype page.
- Restoration Simulation page.
- Validation page.

### 4.5 Required Visualizations

- PCA or clustering plot.
- Healthy vs SLE pathway comparison chart.
- Distance-to-health chart.
- Endotype cluster visualization.
- Restoration impact visualization.
- Validation summary table.

---

## 5. Machine Learning and Digital Twin Requirements

### 5.1 Model Objective

The model shall represent each SLE sample as an immune-state twin and compare it with a healthy reference twin.

### 5.2 Data Inputs

Required inputs:

- Public transcriptomic expression matrix.
- Healthy control samples.
- SLE samples.
- Dataset metadata.
- Pathway definitions.

### 5.3 Preprocessing Requirements

The pipeline shall include:

- Data ingestion.
- Quality-control checks.
- Normalization.
- Gene identifier harmonization.
- Missing data handling.
- Documentation of preprocessing decisions.

### 5.4 Healthy Reference Twin

The healthy reference twin shall provide:

- Healthy baseline pathway scores.
- Baseline summary statistics.

### 5.5 Patient Immune-State Twin

The patient twin shall provide:

- Pathway deviation profile.
- Distance-to-health score.
- Ranked abnormal pathways.

### 5.6 Distance-to-Health Metric

The system shall compute a quantitative measure representing the distance between:

- Healthy pathway profile.
- SLE pathway profile.

This metric shall serve as the primary digital twin output.

### 5.7 Endotype Analysis

A simple clustering method may be used.

Required outputs:

- Cluster labels.
- Cluster pathway signatures.
- Basic stability discussion.

### 5.8 Virtual Restoration Simulation

The simulation module shall:

- Select a pathway.
- Move pathway activity toward healthy levels.
- Recalculate distance-to-health.
- Estimate improvement percentage.

Required outputs:

- Baseline distance-to-health.
- Post-restoration distance-to-health.
- Improvement score.

---

## 6. Verification and Validation Requirements

### 6.1 Verification Goal

Verification confirms the system functions as designed.

### 6.2 Verification Deliverables

- Dataset inventory.
- Preprocessing log.
- Pathway scoring documentation.
- Twin-construction documentation.
- Simulation documentation.
- Reproducibility instructions.
- Known limitations statement.

### 6.3 Technical Validation

The project shall evaluate:

- Pipeline reproducibility.
- Consistency of pathway scores.
- Correct distance calculations.
- Dashboard functionality.

### 6.4 Biological Validation

The system shall attempt to recover known SLE biology:

- Type I interferon signaling.
- Neutrophil activation.
- B-cell related signatures.

### 6.5 Application Validation

The project shall verify:

- Dashboard pages load correctly.
- Visualizations match backend outputs.
- Simulations produce expected results.
- Non-clinical-use notice is displayed.

### 6.6 Acceptance Criteria

The MVP is complete when:

- Healthy reference twin is implemented.
- Patient twin is implemented.
- Distance-to-health is implemented.
- Pathway scoring is implemented.
- Virtual restoration is implemented.
- Biological validation is completed.
- Dashboard is functional.
- Thesis manuscript draft is complete.

---

## 7. Governance and Ethics

The system shall include:

- Dataset provenance.
- Citation of public datasets.
- Reproducibility documentation.
- Non-clinical-use disclaimer.
- Limitation documentation.

The system shall not process protected health information.

---

## 8. Development Plan

### Week 1

- Literature review.
- Dataset selection.
- Research question finalization.

### Week 2

- Data ingestion.
- Quality control.
- Preprocessing implementation.

### Week 3

- Healthy reference twin.
- Pathway scoring.

### Week 4

- Patient twin implementation.
- Distance-to-health metric.

### Week 5

- Endotype clustering.
- Preliminary analysis.

### Week 6

- Restoration simulation.
- Validation experiments.

### Week 7

- Dashboard development.
- Visualization development.

### Week 8

- Thesis writing.
- Figures.
- Results.
- Final validation package.

---

## 9. Final Deliverable 2: Publishable Paper

### 9.1 Paper Goal

Describe a lightweight immune digital twin framework for quantifying SLE immune-state deviation and simulating pathway restoration.

### 9.2 Recommended Paper Structure

- Abstract
- Introduction
- Related Work
- Methods
- System Architecture
- Validation
- Results
- Discussion
- Limitations
- Future Work
- Conclusion

### 9.3 Required Figures

- System architecture diagram.
- Data processing workflow.
- Healthy vs SLE comparison.
- Endotype visualization.
- Restoration simulation visualization.
- Dashboard screenshot.

### 9.4 Required Tables

- Dataset inventory.
- Validation metrics.
- Pathway ranking summary.
- Scope reduction and future work table.

---

## 10. Final MVP Acceptance Checklist

- Dataset selected.
- Preprocessing implemented.
- Healthy twin implemented.
- Patient twin implemented.
- Pathway scoring implemented.
- Distance-to-health implemented.
- Endotype analysis completed.
- Restoration simulation implemented.
- Dashboard completed.
- Validation completed.
- Thesis draft completed.
- Limitations documented.
- Non-clinical-use disclaimer included.
