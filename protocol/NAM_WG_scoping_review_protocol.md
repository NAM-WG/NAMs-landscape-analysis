# Scoping Review Protocol: Quantitative Pharmacology as the Translation Layer for Complex In Vitro NAMs

**Working group:** ISoP QSP SIG – New Approach Methodologies (NAMs) & Quantitative Pharmacology WG
**Version:** 0.1 (DRAFT for WG review) · 2026-11-25
**Status:** Not yet registered. Target: OSF Registries (Generalized Systematic Review Registration / scoping review template) before screening starts.
**Reporting standard:** PRISMA-ScR (Tricco et al., 2018); conducted following JBI scoping review guidance (Peters et al., JBI Manual for Evidence Synthesis).
**Primary output file:** `References_Log/NAM_WG_landscape_literature_log.csv` (the data-charting table; see Section 7)

> Items marked **[DECIDE]** need a WG decision before registration.

---

**AI-use statement:** This protocol was drafted with the assistance of Claude Opus 5.5 (Anthropic) and was iteratively reviewed and edited by the human authors, who take full responsibility for its content.

## 1. Background and rationale

Human-relevant in vitro NAMs (microphysiological systems, organ-on-chip, organoids, spheroids, iPSC-derived systems) are being used more and more in drug development. Regulators now expect sponsors to justify them: FDA's March 2026 draft guidance on NAMs sets out four validation principles (context of use, human biological relevance, technical characterization, fit-for-purpose), and ICH M15 sets out general principles for model credibility in MIDD. In vitro readouts don't predict human outcomes on their own. A quantitative model (IVIVE, PBPK, QSP/QST, PK/PD or ML) is usually needed to turn data from an in vitro system into human exposure, efficacy or safety predictions.

Existing reviews cover parts of this space. Soheili et al. (2026) systematically reviewed MPS combined with computational models. Rowland Yeo & van der Graaf (2026) made the case for PBPK and QSP as regulatory-grade NAMs. No review has yet mapped, across platforms and contexts of use, (a) *how* the translation from in vitro to human is done, (b) what credibility evidence supports it, and (c) which development and regulatory decisions these approaches have already informed. A scoping review fits this aim, which is to map the extent, range and nature of the evidence and identify gaps.

## 2. Objectives and review questions

**Objective:** Map published applications in which data from complex in vitro NAMs are integrated with quantitative pharmacology models to predict in vivo or human outcomes in drug development, and characterize their contexts of use, translation methods, credibility evidence and decision impact.

**Review questions**

- **RQ1:** For which contexts of use (PK/exposure, efficacy, acute and chronic safety, dose selection, target/mechanism), organ systems, therapeutic areas and drug modalities have complex in vitro NAM data been combined with quantitative models?
- **RQ2:** Which in vitro platforms and model types are used, and in which combinations?
- **RQ3:** What translation methods carry in vitro readouts to in vivo or human predictions (e.g., direct scaling, IVIVE, PBPK-linked exposure matching, QSP/QST calibration, ML)?
- **RQ4:** What credibility evidence is reported (comparison with clinical, animal or other in vitro data; number of compounds; performance metrics; uncertainty or sensitivity analysis; formal frameworks), and which FDA NAM principles and ICH M15 elements does it address?
- **RQ5:** At what development stage were these approaches applied, and did they inform a prospective decision or regulatory interaction?
- **RQ6:** What 3Rs impact (replace, reduce, refine) is claimed or shown?
- **RQ7:** Where are the main evidence gaps?

## 3. Eligibility criteria (Population–Concept–Context)

| Element | Include | Exclude |
| --- | --- | --- |
| **Population (in vitro system)** | Human (or human-relevant) complex in vitro systems: MPS, organ-on-chip, organoids (including patient-derived), spheroids/3D cultures, perfused/co-culture systems, iPSC-derived tissues | Cell-free assays alone |
| **Concept (quantitative model)** | A mathematical or computational model that uses data from the in vitro system to make a quantitative prediction for in vivo or human (PK, PD, efficacy, toxicity, dose): IVIVE, PBPK, QSP, QST, PK/PD, mechanistic tumor/tissue models, ML/AI, hybrid ML-mechanistic | Purely descriptive in vitro statistics (e.g., IC50 only) with no translation step; models with no in vitro input; models developed mainly with in vivo animal study data |
| **Context** | Pharmaceutical drug discovery, development or regulatory evaluation (small molecules, biologics, ADCs, oligonucleotides, cell/gene therapies, peptides) | Environmental chemical, food, cosmetic or industrial chemical risk assessment (NGRA) |
| **Standard 2D systems** | Included only when coupled to a model **and** a complex system, or as a comparator | — |
| **Study type** | Primary research (experimental, computational or both) | Reviews, perspectives and guidance (charted as context references, not counted in the evidence map; Section 7); conference abstracts; preprints |
| **Dates and language** | 1 Jan 2010 to the search date; English | Non-English |

## 4. Information sources

**Bibliographic databases**

- PubMed/MEDLINE
- Embase (Elsevier) **[DECIDE: subject to institutional access]**
- Scopus or Web of Science Core Collection

**Grey literature and other sources**

- FDA: NAMs Database of Use Case Examples; CDER Streamlined Nonclinical Studies and Acceptable NAMs table; ISTAND and DDT qualification listings; relevant review documents (Drugs@FDA)
- EMA: qualification opinions for novel methodologies; 3Rs working party outputs
- ICCVAM reports; IQ MPS Affiliate publications; Critical Path Institute
- Backward and forward citation searching (snowballing) of all included studies and of key reviews (Soheili 2026; Rowland Yeo & van der Graaf 2026; Balmus 2026)
- WG-member nominations (recorded with `source = Member nomination`)

Records from all sources go through the same screening and charting steps. The PRISMA-ScR flow reports database records and records from other sources separately, as the template requires.

## 5. Search strategy

### 5.1 Draft PubMed strategy (v0.1)

Three concept blocks combined with AND:

```
#1 Platform
("Organoids"[MeSH] OR organoid*[tiab] OR "Lab-On-A-Chip Devices"[MeSH] OR "Microphysiological Systems"[MeSH]
 OR "organ-on-a-chip"[tiab] OR "organ on chip"[tiab] OR "organs-on-chips"[tiab] OR "organ-chip*"[tiab]
 OR microphysiolog*[tiab] OR "tissue chip*"[tiab] OR "Spheroids, Cellular"[MeSH] OR spheroid*[tiab]
 OR "3D culture*"[tiab] OR "three-dimensional culture*"[tiab] OR "iPSC-derived"[tiab]
 OR "new approach methodolog*"[tiab])

#2 Quantitative model
("physiologically based"[tiab] OR PBPK[tiab] OR "quantitative systems pharmacology"[tiab]
 OR "quantitative systems toxicology"[tiab] OR "Models, Biological"[MeSH] OR "pharmacokinetic-pharmacodynamic"[tiab]
 OR "PK/PD"[tiab] OR PKPD[tiab] OR "in vitro-in vivo extrapolation"[tiab] OR "in vitro to in vivo"[tiab] OR IVIVE[tiab]
 OR "mechanistic model*"[tiab] OR "mathematical model*"[tiab] OR "computational model*"[tiab]
 OR "Machine Learning"[MeSH] OR "machine learning"[tiab] OR "digital twin*"[tiab])

#3 Drug context
(drug*[tiab] OR pharmac*[tiab] OR toxicit*[tiab] OR dose[tiab] OR dosing[tiab] OR clearance[tiab]
 OR efficacy[tiab] OR "Pharmacokinetics"[MeSH] OR "Drug Evaluation, Preclinical"[MeSH])

#4 = #1 AND #2 AND #3 AND ("2010/01/01"[dp] : "3000"[dp]) AND English[la]
```

Notes:

- Confirm each MeSH heading exists and check its entry date in the MeSH browser. "Microphysiological Systems" is newer than the others, so its free-text synonyms are what catch older records.
- `"Models, Biological"[MeSH]` is broad and may inflate hits. Test the search with and without it.
- Translate the strategy for Embase (Emtree, `/exp`, `:ti,ab,kw`) and Scopus (`TITLE-ABS-KEY`), and save each version verbatim in `search/strings/`.

### 5.2 Testing against the seed set

- The strategy is tuned until it retrieves **≥ 90%** of the seed set (Appendix A: the 14 hybrid in vitro + model studies already in the log, plus about 10 further known-relevant studies the WG nominates).
- For each missed seed paper, record why it was missed (terms used, indexing) and the change made. Log every iteration in `search/search_log.csv`.

### 5.3 Execution

- Run all databases within one week. Record the date, interface, string version and hit count per database in `search/search_log.csv`, and save the raw exports (RIS) in `search/exports/YYYY-MM-DD_<database>.ris`.
- Re-run the search before submission for an update. Screen new records the same way and report them as a separate PRISMA box.

## 6. Evidence selection

1. **Deduplication:** import all exports into the WG Zotero group library, deduplicate, and export one combined RIS file to the screening tool. Record counts before and after.
2. **Screening tool:** Rayyan (free) or Covidence (if a member institution has a licence) **[DECIDE]**.
3. **Calibration:** all screeners independently screen the same 100 randomly sampled records against a screening guide (`protocol/screening_guide.md`). Compute Cohen's κ for each pair. Below 0.7, discuss, refine the guide and repeat with 50 new records.
4. **Title/abstract screening:** two independent reviewers per record, with reviewers paired across organizations where possible. When unsure, include. Co-chairs (or a third member) resolve conflicts.
5. **Full-text screening:** two independent reviewers, recording one exclusion reason per excluded record from a fixed list: wrong population, wrong concept (no model or no translation), wrong context, wrong study type, duplicate or companion report, full text unavailable.
6. **AI-assisted screening (optional) [DECIDE]:** active-learning prioritization (ASReview) or an LLM may act as an additional screener or rank records. A human must make every final include/exclude decision, and a human must check at least 10% of AI-suggested exclusions. Report the tool, version, prompt and settings in the methods.
7. **Seed set (the existing 23 log entries):** re-screen against Section 3. Mark eligible primary studies `source = Seed`. Charted entries not retrieved by the database search stay in, flagged as `source = Seed`, and are reported as "records identified from other methods" in the PRISMA diagram.

## 7. Data charting: updating the literature log

The literature log is the **charting table**. Each row is one included report: a primary study that passed full-text screening, or a context reference (review, guidance, regulatory or workshop document).

**Record lifecycle**

```
database exports (search/exports/)
  → deduplicated library (Zotero)
  → screening decisions (screening/ : tool export + full-text exclusion reasons)
  → INCLUDED reports → one row each in References_Log/NAM_WG_landscape_literature_log.csv
  → analysis/ (evidence-map figures, PRISMA flow) built from the log + screening counts
```

**Rules**

- Every row has a unique `record_id` (e.g., `NAMWG-0001`) that links it to its screening record.
- Fields follow the data dictionary v1.0 (Appendix B) with controlled vocabularies. Put free-text detail only in the designated detail or comment fields.
- **Two-person charting:** one member charts the row, and a second member checks it against the full text and fills `verified_by`. A row isn't used in the analysis until `charting_status = verified`.
- The charting form is piloted on 5 studies by all chargers before the main round. Revise the dictionary if fields are ambiguous.
- Context references (`article_type` other than Primary research) stay in the same log but are not counted in the evidence map, which uses primary research only.
- **Version control:** changes go in as pull requests in batches of about 10–20 rows per contributor. An automated check validates columns and controlled vocabulary on each PR. Tag releases (`v1.0-charting-complete`), and deposit the release on Zenodo for a DOI.

## 8. Data items

See Appendix B for the full v1.0 field list. The main additions to the current log are article type, source, workstream, development stage and decision informed, translation method, number of compounds, benchmark metric, the FDA NAM principles addressed, 3Rs impact, platform/vendor, data and code availability, and charting quality-control fields.

## 9. Critical appraisal

In line with PRISMA-ScR and JBI guidance, we won't do a formal risk-of-bias assessment. Instead, the **credibility evidence** each study reports is charted as data (RQ4) and summarized against the FDA NAM validation principles and ICH M15 credibility elements.

## 10. Synthesis and presentation

- PRISMA-ScR flow diagram (PRISMA2020 R package, built from the logged counts)
- Descriptive counts by year, platform, model type, organ system, therapeutic area, modality and context of use
- **Evidence map:** a heatmap of COU × platform × model type
- **Maturity ladder:** proof of concept → retrospective benchmark against clinical data → prospective decision → regulatory interaction or acceptance
- **Translation-method summary:** how the in vitro readout reaches a human prediction, by platform
- **Credibility-gap table:** studies addressing each FDA principle and ICH M15 element
- Narrative synthesis of gaps and research priorities, plus proposed minimum reporting elements for hybrid in vitro + model studies

All analysis code lives in `analysis/` and runs directly from the log.

## 11. Consultation (optional) [DECIDE]

A short practitioner survey (ISoP QSP SIG, IQ MPS Affiliate, SPS) and the planned webinar serve as the optional consultation stage of a scoping review. If done, the survey gets its own short protocol and ethics or exemption check.

## 12. Data management and repository structure

```
NAMs-landscape-analysis/
├── protocol/            protocol (this file), screening guide, amendments log
├── search/
│   ├── strings/         final search strings per database (verbatim)
│   ├── exports/         raw RIS exports (consider .gitignore if large; keep counts in search_log)
│   └── search_log.csv   date, database, interface, string version, hits
├── screening/           tool exports, calibration κ, full-text exclusion reasons
├── References_Log/      literature log (charting table), data dictionary, template
├── analysis/            scripts + figures (evidence map, PRISMA flow)
└── .github/workflows/   log validation check
```

## 13. Timeline (proposed)

| Step | Dates |
| --- | --- |
| Protocol finalized; scope decisions; OSF registration | Dec 2026 |
| Search tested against the seed set; charting pilot | Dec 2026 – early Jan 2027 |
| Searches run; deduplication; calibration; title/abstract screening | Jan – mid-Feb 2027 |
| Full-text screening and charting with verification | Feb – Mar 2027 |
| Analysis, figures, drafting | Apr – May 2027 |
| Search update; manuscript submission | Jun 2027 |

## 14. Roles **[DECIDE]**

| Role | Proposed |
| --- | --- |
| Protocol lead / guarantor | Co-chairs (Krina Mehta, Khem Raj Ghusinga) |
| Search lead (strings, execution, search log) | TBD |
| Screening pairs | All members, paired across organizations |
| Conflict resolution | Co-chairs, or a third member if a co-chair is in the pair |
| Charting leads | WS2: Jason, Khem, Ben, Lara, Christian · WS3: Krina, Celeste, Christina · WS4: all |
| Analysis and figures | TBD |

## 15. Amendments

Record any deviation from the registered protocol in `protocol/amendments.md` (date, change, reason, effect on results), and report it in the manuscript.

---

## Appendix A. Seed set (search validation)

The 14 hybrid (in vitro + in silico) studies already in the log. The search must retrieve at least 90% of these plus the WG-nominated additions.

| Identifier | Year | Title |
| --- | --- | --- |
| DOI: 10.1111/cts.70774 | 2026 | An In Silico-In Vitro Framework for Model-Informed Precision Dosing in Oncology: Proof-of-Principle for Doxorubicin in Patient-Derived Sarcoma Spheroids |
| PMID: 34462909 | 2021 | A Model-Based Workflow to Benchmark the Clinical Cholestasis Risk of Drugs |
| PMID: 41540842 | 2026 | Quantitative Systems Toxicology Modeling with DILIsym to Support Phase 3 Dose Selection for Fezolinetant |
| PMID: 30869201 | 2019 | Translational Assessment of Drug-Induced Proximal Tubule Injury Using a Kidney Microphysiological System |
| PMID: 31988459 | 2020 | Quantitative prediction of human pharmacokinetic responses to drugs via fluidically coupled vascularized organ chips |
| PMID: 40829518 | 2025 | A primary human Gut/Liver microphysiological system to estimate human oral bioavailability |
| PMID: 27760784 | 2017 | Quantitative Assessment of Population Variability in Hepatic Drug Metabolism Using a Perfused Three-Dimensional Human Liver Microphysiological System |
| PMID: 41368576 | 2025 | Combining mechanistic quantitative systems pharmacology modeling and patient-derived organoid testing in MET-aberrant non-small cell lung cancer for high-throughput combination efficacy analysis and personalized treatment design |
| PMID: 37765243 | 2023 | Translational Pharmacokinetic/Pharmacodynamic Modeling and Simulation of Oxaliplatin and Irinotecan in Colorectal Cancer |
| PMID: 34151400 | 2021 | New insights into the mechanisms underlying 5-fluorouracil-induced intestinal toxicity based on transcriptomic and metabolomic responses in human intestinal organoids |
| PMID: 37013646 | 2023 | Platform combining statistical modeling and patient-derived organoids to facilitate personalized treatment of colorectal carcinoma |
| PMID: 33287759 | 2020 | Emergence of spatio-temporal variations in chemotherapeutic drug efficacy: in-vitro and in-Silico 3D tumour spheroid studies |
| PMID: 34992705 | 2020 | A pharmacokinetic-pharmacodynamic model based on multi-organ-on-a-chip for drug-drug interaction studies |
| PMID: 33385970 | 2021 | Quantifying ADC bystander payload penetration with cellular resolution using pharmacodynamic mapping |

Note: PMID 34462909 (cholestasis workflow) may fail the "complex in vitro system" criterion if its assay turns out to be standard culture. Confirm this from the full text.

## Appendix B. Data dictionary v1.0 (proposed changes to the current log)

Existing fields are kept (with `pmid` renamed `identifier` to match the log header). **New** fields are marked.

| Field | Req. | Allowed values / format | Change |
| --- | --- | --- | --- |
| `record_id` | Y | `NAMWG-####` | **New** |
| `identifier` | Y | `PMID: <digits>` · `DOI: <doi>` · URL | Renamed from `pmid` |
| `contributor` | Y | WG member name; Other | Existing |
| `title` | Y | free text | Existing |
| `year` | Y | YYYY | Existing |
| `article_type` | Y | Primary research; Review; Perspective; Guidance/regulatory; Workshop report; Database/resource | **New** |
| `source` | Y | Database search; Seed; Citation search; Member nomination; Grey literature | **New** |
| `workstream` | Y | WS2; WS3; WS4 (multiple allowed) | **New** |
| `nam_category` | Y | In vitro; In silico; In chemico; Hybrid (in vitro + in silico); Policy/Framework; Other | Adds Policy/Framework (as in the local edit) |
| `nam_sub_category` | Y | Controlled terms only (current list), `;`-separated; **no parenthetical text** | Tightened |
| `system_details` | N | free text: cell sources, platform specifics, readouts | **New** (takes the parenthetical detail) |
| `platform_vendor` | N | Emulate; CN Bio; Mimetas; InSphero; TissUse; Academic/custom; Other; Not reported | **New** |
| `organ_system` | N | free text (Multi-organ / Not organ-specific allowed) | Existing |
| `cou` | Y | `<category>: <statement>`; categories as current plus Policy/Framework | Adds Policy/Framework |
| `development_stage` | Y | Discovery; Lead optimization; IND-enabling; FIH; Phase 2/3; Post-marketing; Regulatory review; Not applicable | **New** |
| `decision_informed` | Y | Prospective decision; Retrospective/benchmark only; Regulatory interaction; None/not reported | **New** |
| `translation_method` | Y (primary research) | Direct/physiological scaling; IVIVE; PBPK-linked exposure; QSP/QST calibration; PK/PD linkage; ML/statistical; Other | **New** |
| `therapeutic_area` | N | current list plus Agnostic | Adds Agnostic |
| `drug_modality` | N | current list | Existing |
| `n_compounds` | N | integer | **New** |
| `credibility` | N | current list | Existing |
| `benchmark_metric` | N | e.g., AFE; % within 2-fold; R²; AUROC; HR/OR; Qualitative | **New** |
| `fda_principles_addressed` | N | Context of use; Human biological relevance; Technical characterization; Fit-for-purpose; None stated | **New** |
| `three_rs_impact` | N | Replace; Reduce; Refine; None; Not discussed | **New** |
| `data_code_available` | N | Data; Code; Both; Neither | **New** |
| `full_text_reviewed` | Y | Y; N | **New** |
| `charting_status` | Y | Draft; Verified | **New** |
| `verified_by` | Y (to verify) | WG member name | **New** |
| `contributor_comments` | N | free text | Existing |
