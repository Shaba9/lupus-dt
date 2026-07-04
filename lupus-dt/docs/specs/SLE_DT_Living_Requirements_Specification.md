# SLE Digital Twin Living Requirements Specification (SLE-DT LRS)

## Revision Status

### Integrated Literature Reviews
1. SLE DEG Bioinformatics Review.
2. AI, Biomarkers, and Precision Rheumatology Review.
3. Digital Twins and the Metaverse in Healthcare Review.
4. AI Autoimmune Research Trends (2025 Bibliometric Analysis).
5. AI for Systemic Lupus Erythematosus Personalized Treatment.
6. The Role of Health Information Technology in the Control and Management of SLE.
7. Federated Learning Security and Governance in Healthcare.
8. Immune Digital Twins for Complex Human Pathologies: Applications, Limitations, and Challenges.
9. Deep Learning-Based Prediction of Autoimmune Diseases.

### Current Revision Purpose
This revision merges the deep-learning/TCR-repertoire literature review into the living specification while preserving the current MVP scope. The new review adds future architecture guidance for T-cell receptor sequencing, multi-instance learning, CNN motif-detection models, BiLSTM-attention sequence models, immune repertoire features, and transfer-learning possibilities. Because the article does **not** include SLE, these additions are treated as future or stretch capabilities, not MVP requirements.

---

## 1. Canonical Thesis Direction

### 1.1 Selected MVP Architecture
**Transcriptomics-First + Molecular-Endotype-Aware Immune Digital Twin**

The project is explicitly framed as an **Immune Digital Twin (IDT)** rather than only a general healthcare Digital Twin. The system models both disease-state deviation and immune-system response patterns relevant to SLE.

### 1.2 MVP Scope Decision
The MVP remains focused on:
- Systemic Lupus Erythematosus (SLE).
- Bulk transcriptomic data.
- Healthy-vs-disease immune-state modeling.
- Molecular endotype discovery.
- Immune-tolerance restoration.
- Explainable pathway and target prioritization.
- Research-only, non-clinical deployment.
- Modular, FAIR-aligned architecture.
- Basic scalability and reproducibility design.

The deep-learning/TCR review does **not** change the MVP because SLE was not included in the study and because the proposed models rely on TCR-seq data rather than the transcriptomic datasets selected for the thesis MVP. Its main value is as a future roadmap for immune-repertoire and sequence-modeling extensions.

### 1.3 Research Objective Representation
The Digital Twin represents:
- Patient immune state.
- Disease-state deviation from health.
- Molecular endotypes.
- Active immune pathways.
- Pathology-associated transcriptomic deviation.
- Immune-response patterns.
- Candidate restoration opportunities.
- Patient-specific biological hypotheses.

It does **not** represent:
- A treatment recommendation engine.
- A clinical decision support product.
- A telemedicine platform.
- A patient-management application.
- A production federated-learning system.
- A regulatory-grade medical device.
- A drug-response Digital Twin.
- A full organ-level or whole-body lupus simulator.
- A TCR-seq diagnostic classifier in the MVP.

### 1.4 Final MVP Identity
The current thesis MVP is best described as:

> **A modular, FAIR-aligned, transcriptomics-first, molecular-endotype-aware Immune Digital Twin for SLE immune-state modeling and immune-tolerance-restoration hypothesis generation.**

---

## 2. Executive Thesis Objective
Develop an explainable Immune Digital Twin that models patient-specific immune dysregulation, identifies disease-driving pathways, stratifies patients into biologically meaningful molecular endotypes, simulates immune-tolerance restoration scenarios, and generates testable therapeutic hypotheses.

---

## 3. MVP Requirements

### 3.1 Included in MVP
- Public GEO datasets.
- Healthy control cohorts.
- Differential expression analysis.
- Pathway enrichment/scoring analysis.
- Protein-protein interaction (PPI) analysis.
- Molecular endotype discovery.
- Healthy reference twin.
- Patient immune-state twin.
- Twin comparison engine.
- Virtual perturbation engine.
- Explainable target/pathway ranking.
- Technical validation.
- Biological validation.
- Basic public-data governance documentation.
- FAIR-aligned dataset and artifact organization.
- Modular software architecture.
- Reproducible workflow outputs.

### 3.2 Explicitly Out of Scope for MVP
- Clinical deployment.
- Treatment recommendation.
- Real-time monitoring.
- Telemedicine implementation.
- Wearable integration.
- Multi-omics integration.
- EHR integration.
- Production federated learning.
- Processing protected health information.
- Regulatory approval.
- Drug-response simulation.
- Organ-specific simulation.
- Whole-body lupus simulation.
- Cloud-production deployment.
- TCR-seq model training.
- TCR repertoire classification.
- CNN/BiLSTM diagnostic classifiers.

### 3.3 MVP Feasibility Rationale
The MVP remains feasible because it relies on public transcriptomic datasets and avoids protected clinical data, multi-institutional deployment, real-time monitoring, regulated clinical use, and specialized immune-repertoire sequencing inputs. The TCR deep-learning paper supports future immune-sequence modeling but does not justify expanding the MVP beyond transcriptomics.

---

## 4. Immune Digital Twin Design Principles

### 4.1 Pathology + Immune Response Requirement
An effective Immune Digital Twin should represent two foundational elements:
- Pathology-specific events.
- Immune-system responses to those events.

For the SLE-DT MVP, this translates into:
- Disease-state transcriptomic deviation from healthy controls.
- Immune pathway activity differences.
- Molecular endotypes reflecting immune-response variation.
- Restoration simulations that estimate movement toward healthy immune-state behavior.

### 4.2 Modular Architecture Requirement
The SLE-DT shall be designed as a modular research platform rather than a monolithic system. Each module should answer a specific research question and be independently testable.

Required MVP modules:
1. Data ingestion module.
2. Quality-control and normalization module.
3. Differential expression module.
4. Pathway scoring module.
5. PPI/network analysis module.
6. Molecular endotype module.
7. Healthy reference twin module.
8. Patient immune-state twin module.
9. Twin comparison module.
10. Virtual perturbation module.
11. Explainability module.
12. Target/pathway ranking module.
13. Validation and verification module.
14. Governance documentation module.

Future modules may include:
- Biomarker prediction.
- Flare prediction.
- Treatment-response modeling.
- Organ-specific simulation.
- Multi-omics integration.
- Federated learning.
- Digital biomarker integration.
- TCR repertoire modeling.
- Multi-instance immune-repertoire learning.
- Sequence-attention explainability.

### 4.3 FAIR Principles Requirement
The SLE-DT should align data and model artifacts with FAIR principles:
- **Findable:** datasets, gene signatures, pathway sets, models, and outputs should have clear identifiers and metadata.
- **Accessible:** public datasets and processed artifacts should have documented access conditions.
- **Interoperable:** gene identifiers, pathway definitions, and metadata schemas should use reusable standards where feasible.
- **Reusable:** code, parameters, preprocessing steps, and model outputs should be documented for reproducibility.

### 4.4 Scalability Requirement
The MVP does not require production-scale cloud deployment. However, architecture should avoid design choices that prevent future scaling.

Scalability considerations:
- Ability to add new SLE cohorts.
- Ability to add new pathway databases.
- Ability to process incomplete or heterogeneous datasets.
- Ability to extend from cohort-level analysis to patient-level twin generation.
- Ability to later incorporate cloud computing if dataset size or computation requirements grow.
- Ability to add non-transcriptomic immune-repertoire modules later without replacing the MVP architecture.

### 4.5 Interoperability Requirement
Future expansion should support integration across datasets and modules. MVP interoperability requirements include:
- Standardized gene identifiers.
- Documented pathway source/version.
- Standardized output formats for pathway scores, endotypes, and rankings.
- Portable scripts or notebooks.
- Clear separation between data preprocessing, modeling, simulation, and reporting.

Future TCR integration would additionally require:
- TCR sequence metadata standards.
- Patient-level repertoire identifiers.
- Encoding method documentation.
- Sequence model parameter documentation.

---

## 5. SLE Heterogeneity Requirements
SLE presents with highly variable manifestations and disease trajectories.

### Requirements
- The architecture must assume patient heterogeneity.
- Patient grouping must be performed prior to major downstream analyses whenever feasible.
- Disease modeling should not assume a single dominant disease mechanism across all patients.
- Validation should assess whether prioritized pathways remain stable within identified endotypes.
- Future clinical expansions should be capable of integrating organ involvement, symptom clusters, disease severity, treatment history, and patient-reported outcomes.
- Future immune-repertoire expansions should evaluate whether TCR features vary across SLE endotypes.

---

## 6. Molecular Endotype Requirements
Disease subtyping is a foundational requirement.

### 6.1 Required MVP Signals
- Gene-expression signatures.
- Pathway activation profiles.
- Interferon activity.
- Immune-state signatures.
- B-cell-related signatures.

### 6.2 Future Endotype Layers
Potential future grouping strategies identified across reviewed literature:
- Biological markers.
- Organ involvement.
- Disease severity.
- Symptom clusters.
- Treatment-response patterns.
- Longitudinal clinical trajectories.
- TCR repertoire patterns.
- Attention-derived sequence motifs.

### 6.3 Current MVP Decision
Biological and transcriptomic stratification remains the preferred MVP approach because it is directly supported by available data and aligns with the thesis goal of molecular-endotype-aware immune-state modeling.

---

## 7. Scientific Foundation

### 7.1 Core Biological Themes
- Immune tolerance restoration.
- Molecular heterogeneity.
- Patient stratification.
- Explainable AI.
- Transcriptomic disease-state modeling.
- Pathology-specific immune response modeling.
- T-cell receptor repertoire modeling as a future immune-feature layer.

### 7.2 Key Disease Mechanism Categories
- Neutrophil biology.
- Interferon biology.
- B-cell biology.
- T-cell regulatory biology.
- T-cell receptor diversity and immune repertoire signatures as a future extension.

### 7.3 Priority Hub Genes
The following hub genes remain priority monitoring targets from prior DEG/PPI literature integration:
- CCNB2
- CDCA8
- AURKB
- BUB1B
- RRM2
- BIRC5
- UBE2C

---

## 8. Data Strategy

### 8.1 Core MVP Datasets
- GSE162828.
- GSE169080.

### 8.2 First-Class Requirement: Healthy Controls
Healthy-control cohorts are critical for meaningful disease-state comparison and must remain a first-class requirement.

### 8.3 Dataset Documentation Requirements
Capture when available:
- Age.
- Sex.
- Ethnicity/ancestry.
- Disease subtype.
- Organ involvement.
- Clinical metadata.
- Treatment history.
- Cohort provenance.
- Dataset source and access conditions.
- Data modality.
- Platform/assay type.
- Sample count by class/endotype where available.

### 8.4 Data Standardization Requirements
Because SLE data may originate from multiple specialties and diagnostic modalities:
- Data normalization shall be documented.
- Batch-effect correction shall be documented.
- Missing-data handling shall be documented.
- Feature provenance shall be documented.
- Dataset inclusion/exclusion criteria shall be documented.
- Gene identifier mapping shall be documented.
- Pathway database versions shall be documented.

### 8.5 FAIR Data and Model Artifact Requirements
The project should maintain:
- Dataset inventory.
- Processed expression matrix metadata.
- DEG result metadata.
- Pathway scoring metadata.
- Model configuration metadata.
- Simulation parameter metadata.
- Output ranking provenance.

### 8.6 Future TCR Dataset Strategy
The deep-learning autoimmune disease review used publicly available TCR-seq data from immuneACCESS and referenced open repositories. For SLE-DT, this suggests a future dataset search requirement:
- Determine whether SLE-specific TCR-seq datasets exist.
- Determine whether lupus cohorts are available through immuneACCESS or related immune-repertoire repositories.
- Document disease labels, cohort sizes, control cohorts, sequence metadata, and class imbalance.
- Determine whether TCR repertoires can be mapped to transcriptomic endotypes.

This remains future work and is not required for the MVP.

### 8.7 Governance Impact of Current MVP Data Choice
Because the MVP uses public datasets only and does not process protected health information, the immediate privacy risk is lower than in clinical or multi-institutional deployment. However, data provenance, dataset usage restrictions, reproducibility, and ethical documentation still remain required.

---

## 9. Clinical Context Layer
SLE management often involves multiple specialties:
- Rheumatology.
- Nephrology.
- Dermatology.
- Neurology.
- Hematology.

Future Digital Twin evolution should support incorporation of disease information from multiple clinical domains. This remains outside the MVP.

---

## 10. Digital Twin Functional Architecture

### 10.1 MVP Functional Components
1. Data ingestion module.
2. Quality-control and normalization module.
3. Differential gene expression engine.
4. Pathway enrichment/scoring engine.
5. PPI/network analysis engine.
6. Molecular endotype discovery engine.
7. Healthy reference twin constructor.
8. Patient immune-state twin constructor.
9. Twin comparison engine.
10. Virtual perturbation engine.
11. Explainability engine.
12. Target/pathway ranking engine.
13. Technical validation and verification module.
14. Biological validation module.
15. FAIR/governance documentation module.

### 10.2 Design Constraint
No universally optimal Digital Twin architecture has been established across the reviewed literature. Therefore, the SLE-DT architecture must remain application-driven and justified by the thesis objective: transcriptomics-first immune-state modeling and immune-tolerance restoration.

### 10.3 Modular Design Requirement
Modules should be loosely coupled so that future components can be added without rewriting the entire system. For example, the same patient twin representation should later support additional modules such as proteomics, EHR data, digital biomarkers, federated learning, treatment-response modeling, or TCR repertoire modeling.

### 10.4 Model Input and Output Control
The architecture should distinguish between:
- Raw input data.
- Processed research data.
- Intermediate model outputs.
- Final hypothesis rankings.
- Future clinical-facing outputs.

For the MVP, all outputs are research artifacts and should not be presented as clinical recommendations.

---

## 11. Security, Privacy, and Governance Requirements

### 11.1 Requirement Status
Security, privacy, compliance, and governance are first-class requirements. They shall not be treated as post-development add-ons.

### 11.2 Applicability to MVP
The MVP uses public datasets and does not access protected health information. Therefore:
- Full clinical compliance workflows are not required for the MVP.
- Production federated learning is not required for the MVP.
- Formal protected-data access workflows are not required for the MVP.

However, the MVP should still include:
- Dataset provenance documentation.
- Dataset usage documentation.
- Reproducibility documentation.
- Code and model traceability.
- Output interpretation guardrails.
- Clear statement that outputs are research hypotheses, not clinical recommendations.

### 11.3 Governance Principles
Future system evolution shall follow:
- Privacy-by-design.
- Security-by-design.
- Explainability-by-design.
- Validation-by-design.
- Verification-by-design.
- FAIR-by-design.
- Human oversight.
- Documentation-first model development.

### 11.4 Privacy Requirements
For the MVP:
- Use public data only.
- Do not process protected health information.
- Track dataset provenance.
- Document usage constraints.

For future clinical or institutional deployments:
- Define data access controls.
- Document lawful/approved data use.
- Evaluate privacy leakage risks.
- Define stakeholder approval workflows.
- Perform privacy impact assessment before sensitive-data access.
- Define informed-consent and patient-rights processes where patient-level clinical data are used.

### 11.5 Security Requirements
Future architectures should support:
- Secure communications.
- Encryption for data/model transfer.
- Role-based access control.
- Audit logging.
- Threat modeling.
- Security monitoring.
- Incident response planning.
- Safeguards against intentional or accidental data corruption.

### 11.6 Access-Control Requirements
Future clinical or patient-facing systems should define access rules for:
- Raw patient data.
- Processed patient data.
- Model predictions.
- Research outputs.
- Clinical-facing results.
- Patient-facing summaries.

Current literature does not specify which exact SLE-DT components should be clinician-only; this remains open.

### 11.7 AI Governance Requirements
Future AI-enabled Digital Twin extensions should support:
- Human approval workflows.
- Decision traceability.
- Model and agent audit logs.
- Security review before sensitive-data access.
- Privacy review before sensitive-data access.
- Governance review before deployment.
- Documentation of model limitations and intended use.
- Continuous auditing where systems influence clinical or research decisions.

---

## 12. Federated Learning Roadmap

### 12.1 Status
Federated Learning is a **future architecture option**, not an MVP requirement.

### 12.2 Potential Benefits for Future SLE-DT
Federated Learning may support:
- Multi-institution collaboration.
- Larger patient populations.
- More diverse cohorts.
- Reduced need for centralized patient-data storage.
- Privacy-preserving model development across hospitals and research institutions.

### 12.3 Key Risks
Federated Learning does not automatically eliminate privacy risk. Future FL-based SLE-DT systems must address:
- Model parameter leakage.
- Reconstruction attacks.
- Membership inference attacks.
- Sensitive attribute inference.
- Communication-channel vulnerabilities.
- Institutional governance complexity.

### 12.4 Candidate Future Capabilities
Future architecture may investigate:
- Federated learning.
- Secure aggregation.
- Differential privacy.
- Federated validation.
- Privacy auditing.
- Automated compliance verification.
- Federated model monitoring.

### 12.5 FL Design Requirement
If FL becomes part of a future SLE-DT phase, security, privacy, legal, governance, and clinical stakeholders must be involved from project initiation rather than after model development.

---

## 13. Cross-Disciplinary Stakeholder Requirements

### 13.1 MVP Stakeholders
The MVP should incorporate or seek feedback from:
- Bioinformatics experts.
- AI/ML researchers.
- Immunology experts.
- Rheumatology experts when available.

### 13.2 Future Clinical / Federated / Institutional Stakeholders
Future phases should include:
- Rheumatologists.
- Immunologists.
- Nephrologists.
- Dermatologists.
- Neurologists.
- Hematologists.
- Bioinformatics experts.
- AI/ML developers.
- Data scientists.
- Healthcare informatics experts.
- Federated solution architects.
- Security specialists.
- Privacy specialists.
- Legal/compliance experts.
- Governance stakeholders.
- Regulatory specialists.

### 13.3 Stakeholder Principle
Healthcare AI, Immune Digital Twins, and Federated Learning systems are socio-technical systems. Technical model development must be aligned with clinical, privacy, legal, governance, regulatory, and security requirements.

---

## 14. Future AI Capability Roadmap

### 14.1 Single-Cell Extensions
- scRNA-seq integration.
- Automated cell-state annotation.
- Cell-state discovery.
- Future immune-cell-state modeling for B cells, T cells, neutrophils, and other immune populations.
- Future comparison of single-cell immune states against transcriptomic molecular endotypes.

### 14.2 Multi-Modal Patient Monitoring
Future phases may investigate:
- Clinical laboratory data.
- Patient-reported outcomes.
- Digital biomarkers.
- Wearable data.
- Longitudinal symptom tracking.
- Disease activity scores.
- Organ involvement data.

### 14.3 Multi-Omics Digital Twin
Future phases may investigate:
- Genomics.
- Epigenomics.
- Proteomics.
- Cytokine profiling.
- Immune-cell phenotyping.
- TCR repertoire sequencing.
- Autoantibody profiles.
- Complement-related biomarkers.

### 14.4 Federated / Privacy-Preserving AI
Future phases may investigate:
- Federated learning.
- Secure aggregation.
- Differential privacy.
- Privacy-preserving analytics.
- Agentic AI governance.
- Federated validation.
- Privacy leakage auditing.
- Secure multi-institution collaboration.

### 14.5 Transfer Learning Roadmap
Transfer learning may be investigated as a future or stretch capability for limited SLE datasets.

Potential uses:
- Pretraining on larger immune or biomedical datasets.
- Fine-tuning on SLE-specific transcriptomic cohorts.
- Fine-tuning autoimmune TCR models on SLE-specific TCR datasets if such datasets become available.
- Improving performance in small or narrowly defined endotypes.
- Supporting future rare-subtype modeling.

Transfer learning is **not required for the MVP**, but it may become useful if the available SLE cohorts are too small for robust modeling.

### 14.6 TCR Repertoire Deep Learning Roadmap
The reviewed deep-learning autoimmune disease paper introduces methods that may be relevant to future immune-repertoire extensions of the SLE-DT. However, because the paper does **not** include SLE, these approaches should remain future work rather than MVP requirements.

Future methods may include:
- **Multi-Instance Learning (MIL):** representing each patient as a “bag” of TCR sequences, where each TCR sequence is an instance and the patient/disease/endotype label is the bag label.
- **CNN-based motif detection:** identifying local amino-acid sequence motifs that may be associated with autoimmune immune signatures.
- **BiLSTM with attention:** modeling long-range sequence dependencies and prioritizing biologically relevant TCR sequence regions.
- **Biochemical amino-acid encoding:** transforming TCR amino-acid sequences into numerical vectors based on biochemical properties.
- **Attention-based interpretability:** using attention weights as exploratory evidence for immune-sequence regions associated with disease or endotype status.

Potential future integration with SLE-DT:
- Add TCR repertoire features as an immune-cell-layer extension.
- Compare TCR-based patient groupings against transcriptomic molecular endotypes.
- Use TCR features to refine patient immune-state representations.
- Evaluate whether TCR motifs correlate with neutrophil, interferon, B-cell, or T-cell pathway activity.
- Investigate whether immune-repertoire features improve endotype stability or restoration-target prioritization.

TCR-seq modeling should remain **out of scope for the MVP** unless SLE-specific TCR datasets are later identified and validated.

### 14.7 Drug Development Roadmap
Immune Digital Twins may eventually support:
- Drug discovery.
- Candidate screening.
- Mechanistic understanding.
- Treatment optimization.
- Clinical trial design.
- Endotype-specific therapeutic hypothesis generation.

However, drug-response Digital Twins require greater biological complexity than the current MVP and remain future work.

---

## 15. Verification, Validation, Auditing, and Monitoring Framework

### 15.1 Purpose of Verification vs. Validation
This section is intentionally separated from general architecture requirements because the thesis system must demonstrate both:

- **Verification:** the system was built correctly according to requirements.
- **Validation:** the system produces scientifically meaningful, reproducible, and biologically interpretable outputs for SLE research.

### 15.2 Technical Verification
The MVP shall verify that each implemented module performs its stated function and produces traceable outputs.

Module-level verification should confirm:
- Data ingestion module correctly loads expected input datasets.
- Quality-control module records filtering, normalization, and missing-data decisions.
- DEG engine produces reproducible outputs under fixed parameters.
- Pathway engine uses documented pathway definitions and versions.
- PPI/network module records database/source assumptions.
- Endotype module records clustering method, parameters, and reproducibility checks.
- Healthy reference twin module documents how baseline profiles are created.
- Patient twin module documents how patient-state representations are generated.
- Twin comparison engine documents distance/deviation metrics.
- Virtual perturbation engine documents perturbation assumptions and output calculations.
- Explainability engine identifies gene/pathway evidence supporting rankings.
- Target/pathway ranking engine records scoring logic and ranking weights.
- Governance documentation module records dataset provenance and intended-use boundaries.

### 15.3 Verification Deliverables
The thesis MVP should produce:
- Dataset inventory.
- Preprocessing log.
- DEG parameter log.
- Pathway database/version log.
- PPI source log.
- Endotype method log.
- Twin construction method description.
- Perturbation method description.
- Ranking equation or scoring-rule description.
- Reproducibility instructions.
- Known limitations statement.

### 15.4 Technical Validation
The MVP should validate technical reliability through:
- Reproducibility.
- Stability.
- Cross-dataset consistency.
- Sensitivity analysis.
- Ranking robustness.
- Module-level testing.

### 15.5 Biological Validation
Recover:
- Neutrophil pathways.
- Interferon pathways.
- B-cell signatures.
- T-cell-related immune signals where supported by transcriptomic data.
- Published hub genes.
- Literature-supported biomarkers.

### 15.6 Stratification Validation
Assess:
- Endotype stability.
- Cohort reproducibility.
- Within-endotype pathway consistency.
- Whether pathway rankings differ meaningfully across endotypes.
- Biological interpretability of patient clusters.

### 15.7 Data Quality Validation
Before incorporation into the twin, data should be evaluated for:
- Missingness.
- Batch effects.
- Identifier consistency.
- Sample-label consistency.
- Outlier behavior.
- Cohort documentation quality.

### 15.8 Future TCR Model Validation
If TCR-seq is later added, validation should include:
- Patient-level separation between training and test repertoires.
- Class-imbalance assessment.
- Disease/endotype label quality assessment.
- Attention/motif interpretability review.
- Independent-cohort validation.
- Assessment of whether learned TCR features generalize beyond dataset-specific artifacts.
- Evaluation of whether TCR-derived features improve patient stratification or pathway prioritization.

### 15.9 Security Validation (Future Phase)
Future implementations involving sensitive or institutional data should evaluate:
- Privacy leakage risk.
- Membership inference risk.
- Reconstruction attack risk.
- Sensitive attribute inference risk.
- Attack-surface exposure.
- Access-control effectiveness.
- Threat-model coverage.

### 15.10 Governance Validation (Future Phase)
Future implementations should evaluate:
- Compliance readiness.
- Documentation completeness.
- Explainability availability.
- Human-review processes.
- Approval workflows.
- Auditability.
- Regulatory-risk assessment.

### 15.11 Continuous Auditing and Monitoring
For the MVP, auditing means reproducibility and traceability of research outputs. For future clinical or federated versions, continuous auditing may include:
- Data drift monitoring.
- Model performance monitoring.
- Privacy leakage monitoring.
- Security-event monitoring.
- Retraining triggers.
- Regulatory documentation updates.

### 15.12 Validation Principle
Validation must include more than performance metrics. For future clinical, federated, or multi-modal versions, validation must include:
- Biological plausibility.
- Software reproducibility.
- Privacy risk.
- Security risk.
- Governance readiness.
- Stakeholder review.
- Dataset generalizability.
- Interpretability of model outputs.

### 15.13 Verification and Validation Acceptance Criteria
The MVP should be considered complete only if it can demonstrate:
- Successful construction of a healthy reference twin.
- Successful construction of patient immune-state twins.
- Reproducible DEG and pathway outputs.
- At least one interpretable molecular endotype analysis.
- A documented twin comparison method.
- A documented virtual perturbation method.
- Ranked candidate pathways/targets with explainability evidence.
- Recovery or discussion of known SLE mechanisms from reviewed literature.
- Clear separation between research hypotheses and clinical recommendations.

---

## 16. Open Research Questions

Unanswered by currently reviewed literature:

1. Can deep learning outperform DEG-to-PPI workflows for SLE-specific biomarker discovery?
2. Which hub genes remain important under graph-learning approaches?
3. Can ML recover biologically meaningful genes removed by traditional thresholds?
4. How accurately can transcriptomics alone predict therapeutic targets?
5. Are public longitudinal SLE cohorts available?
6. How should production Digital Twins implement drift monitoring?
7. Can subtype-specific twins outperform generalized twins?
8. How should wearable-derived biomarkers be integrated?
9. Which public datasets contain both molecular and digital-health data?
10. What minimum biomarker set is necessary for a clinically useful lupus twin?
11. Has a fully customizable patient-specific SLE Digital Twin already been demonstrated?
12. Which healthcare DT category best aligns with lupus research goals?
13. Would an organ-specific lupus DT provide sufficient MVP value?
14. Should architecture evolve toward system-wide or organ-specific twins?
15. Which lupus target organ provides highest-value future organ-level twin?
16. Are existing lupus organ simulation platforms available?
17. Which biological, clinical, behavioral, and environmental variables are essential?
18. Are datasets from B-cell-targeting therapy studies publicly available?
19. Which SLE subtype is the most achievable MVP target?
20. Which sequencing and genome-analysis tools are most established in SLE research?
21. Can multi-omics AI models reliably predict individual treatment response?
22. Can digital-health platforms generate sufficiently standardized datasets for predictive AI?
23. What combination of clinical, laboratory, and patient-reported variables provides the strongest predictive value?
24. Should future ML grouping strategies rely primarily on biological markers, symptom clusters, severity, organ involvement, or treatment history?
25. How can privacy, security, and governance requirements be embedded directly into Lupus-DT workflows?
26. What validation criteria should be required before AI systems access or process sensitive healthcare data?
27. How can Federated Learning models be continuously audited for privacy leakage and security vulnerabilities?
28. What stakeholder approval workflows should be incorporated into future healthcare AI systems?
29. Which Federated Learning architecture is most suitable for a future multi-institution SLE Digital Twin?
30. Which components of a future SLE-DT should be restricted to clinician-only access?
31. How can patient rights, privacy, and informed consent be protected while maintaining model utility?
32. Should predictive outputs be partially restricted to reduce risks associated with self-diagnosis or treatment modification?
33. What safeguards are needed to prevent intentional or accidental corruption of training data?
34. How should continuous auditing and regulatory compliance be operationalized within a future clinical platform?
35. Which transfer-learning strategy, if any, is most appropriate for limited SLE transcriptomic datasets?
36. Which disease-modeling paradigm from broader Immune Digital Twin literature best maps to SLE immune-state restoration?
37. Are there publicly available SLE-specific TCR-seq datasets suitable for model training?
38. Can Multi-Instance Learning be adapted to represent lupus patients as immune-repertoire bags?
39. Could attention mechanisms identify lupus-specific immune-sequence signatures?
40. How should TCR-derived features be integrated with transcriptomic endotypes in a future SLE-DT?
41. Can transfer learning from non-SLE autoimmune TCR models improve SLE immune-repertoire modeling?

---

### 16.1 Questions Partially Addressed by Current Literature
- SLE heterogeneity is a major modeling challenge.
- Patient stratification is necessary.
- Biological grouping appears more aligned with the current MVP than symptom-only grouping.
- Federated Learning may support future multi-institution collaboration without centralizing raw data.
- Federated Learning does not eliminate privacy risk because model updates and parameters can leak sensitive information.
- Security, privacy, legal, and governance expertise should be incorporated from the beginning of future healthcare AI or federated-learning projects.
- The Federated Learning review does **not** justify expanding the MVP; it informs future architecture and governance requirements.
- Immune Digital Twins should model both disease/pathology-specific events and immune responses.
- FAIR principles, modular design, scalability, explainability, access control, validation, auditing, and regulatory awareness should guide the architecture.
- Drug-response Digital Twins are more complex than the current transcriptomics-first immune-state MVP and should remain future work.
- CNN, BiLSTM-attention, amino-acid encoding, and Multi-Instance Learning are potentially relevant mathematical concepts for future immune-repertoire modules, but the reviewed paper does not validate them for SLE.
- The reviewed TCR paper demonstrates strong performance for T1D, MS, RA, and IAA, but its findings cannot be assumed to generalize to SLE.

---

### 16.2 Questions Resolved by Current Literature
- Are any mathematical models from the TCR article conceptually applicable to SLE-DT?  
  **Yes, conceptually.** Multi-Instance Learning, CNN motif detection, BiLSTM-attention sequence modeling, biochemical sequence encoding, and attention-based interpretability may inform future modules. They are not part of the MVP because SLE-specific validation is absent.

- Should TCR-seq be included in the thesis MVP?  
  **No.** The reviewed article does not include SLE and relies on a different modality than the current transcriptomic MVP.

---

## 17. Expected Thesis Contributions
- Explainable SLE Immune Digital Twin architecture.
- Molecular-endotype-aware disease modeling.
- Immune-tolerance restoration framework.
- Heterogeneity-aware patient stratification.
- FAIR-aligned and modular healthcare Digital Twin methodology.
- Validation-oriented Digital Twin design.
- Governance-aware design roadmap.
- Future-ready immune-repertoire modeling roadmap.
- Reproducible research platform.

---

## 18. Final MVP Recommendation
The recommended thesis MVP remains:

**A modular, FAIR-aligned, transcriptomics-first, molecular-endotype-aware, explainable SLE Immune Digital Twin for immune-state modeling and immune-tolerance-restoration hypothesis generation.**

The MVP should not include Federated Learning, multi-omics integration, EHR integration, wearables, real-time monitoring, clinical decision support, protected-data processing, organ-specific simulation, drug-response simulation, or TCR-seq deep-learning classification. These are retained as future roadmap items.

---

## 19. References (IEEE)
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