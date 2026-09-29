# Awesome-Clinical-Trial-Matching

# Top Clinical Trial Matching Platforms Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**
*Focused on Patient-to-Trial Matching, Eligibility Screening, Biomarker Alignment & Recruitment Automation*
**Last updated: September 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Clinical Trial Matching**. These tools help research institutions, CROs, and sponsors identify eligible patients for clinical trials by matching patient profiles—clinical, genomic, and demographic—against complex trial eligibility criteria.

**Examples** include Deep 6 AI, TriNetX, Tempus, Flatiron Health, Massive Bio, Mendel AI, Inato, TrialJectory, Curebase, and Medable (the category leaders).

**Open-source emphasis**: Clinical trial matching has a **vibrant open-source research ecosystem**—particularly in oncology. **MatchMiner** (Dana-Farber) and **CancerTrialMatch** (Avera) are production-deployed at major cancer centers . **TrialMatchAI** represents the state of the art in AI-powered matching, achieving >90% recall of relevant trials . **recruIT** (MIRACUM/NUM) is deployed across five German university hospitals with a usability score of 79.9/100 . This section documents these self-hostable, production-grade solutions.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Deep 6 AI](https://deep6.ai/)**  
  AI-powered clinical trial matching platform. Acquired by Tempus in 2023, combining genomic testing capabilities with EHR-based trial matching .

- **[TriNetX](https://www.trinetx.com/)**  
  Global health research network providing real-world data and clinical trial matching. Federated RWD analytics across multi-therapeutic areas .

- **[Tempus](https://www.tempus.com/)**  
  Precision medicine platform combining molecular data with clinical records for oncology trial matching. Acquired Deep 6 AI in 2023 . Partnered with BMS in 2026 to optimize clinical trial design using AI and multimodal RWD .

- **[Flatiron Health](https://flatiron.com/)**  
  Oncology real-world data provider (part of Roche). Launched six new hematology AI longitudinal datasets in 2025 using LLM-supported data extraction .

- **[Massive Bio](https://www.massivebio.com/)**  
  AI-driven clinical trial matching platform focused on oncology patient recruitment.

- **[Mendel AI](https://www.mendel.ai/)**  
  Clinical data curation and trial matching platform using NLP to extract structured data from unstructured clinical notes.

- **[Inato](https://www.inato.com/)**  
  Clinical trial site and patient matching platform connecting sponsors with community sites.

- **[TrialJectory](https://www.trialjectory.com/)**  
  Patient-facing AI platform that matches cancer patients to clinical trials based on their medical history.

- **[Curebase](https://www.curebase.com/)**  
  Decentralized clinical trial platform with patient matching and recruitment capabilities.

- **[Medable](https://www.medable.com/)**  
  Decentralized clinical trial platform with eConsent, ePRO, and patient recruitment tools.

## Open-Source GitHub Projects

- **[MatchMiner](https://github.com/matchminer/matchminer)**  
  **The most established open-source clinical trial matching platform, deployed in production at Dana-Farber Cancer Institute.** Open-source, AI-powered platform matching patients to precision oncology trials based on clinical and genomic profiles . Originally a rules-based engine (launched 2016) matching structured genomic data to trials; the latest version incorporates **AI to analyze unstructured EHR data** (clinical notes) to extract prior treatments, disease stage, and other trial-relevant features . Supports **all patients** at an institution (not just those with genomic sequencing). Already in use at **Princess Margaret Cancer Centre** (Ontario) . Has supported **400+ patient enrollments** at Dana-Farber, with patients matched through MatchMiner enrolling **22% faster** than traditional methods . **Open source** .

- **[TrialMatchAI](https://github.com/cbib/TrialMatchAI)**  
  **State-of-the-art end-to-end AI-powered clinical trial recommendation system.** Published in *Nature Communications* (2026) . Leverages fine-tuned open-source LLMs within a RAG framework for privacy-preserving, local deployment. Handles heterogeneous clinical data (structured + unstructured) via **Phenopackets** exchange format. Uses **hybrid search** (lexical + vector) with **multi-channel query fusion**, **criterion-level reranking**, and **medical Chain-of-Thought (CoT) reasoning** . **Performance**: retrieves **>90% of relevant trials within top-ranked 3%** of search space containing **>26,000 trials**; **92% of real cancer patients** had relevant trial in top 20 recommendations; **>90% criterion-level classification accuracy** . Outperforms GPT-4-based tools. **37 GitHub stars, 16 forks** . Available on PyPI as `trialmatchai` . **Open source** .

- **[recruIT](https://gitlab.ukdd.de/pub/num-sn/recruit)**  
  **Cloud-native clinical trial recruitment support system deployed across 5 German university hospitals.** Developed under MIRACUM and maintained by NUM Study Network . Based on **OMOP CDM** for patient data and **HL7 FHIR** for interoperability. Uses **OHDSI Atlas** for defining trial eligibility criteria as cohort definitions. Architecture: **Query Module** (queries OMOP via OHDSI WebAPI), **List Module** (screening list UI), **Notification Module** (email alerts for new candidates) . All modules communicate via FHIR resources (ResearchStudy, ResearchSubject, Patient, Encounter, Location). **Usability**: SUS score **79.9/100** from 19 end-users across 5 hospitals . Container-based deployment (Docker/Kubernetes). **Open source** .

- **[CancerTrialMatch](https://github.com/AveraSD/CancerTrialMatch)**  
  **Open-source biomarker-based trial matching application developed at Avera Cancer Institute.** Published in *Bioinformatics* (2025) . Captures structured clinical trial data and matches patients based on **disease characteristics and sequencing profiles**. Uses **OncoTree classification** for disease types and captures biomarker details (mutations, copy numbers, fusions) . Retrieves trial data via **ClinicalTrials.gov API** with manual entry for biomarkers. Semi-automated interface built with **R Shiny, MongoDB, and Docker**. Deployed on Windows 11/WSL2 with Docker Compose . Reduces institutional trial management time and supports precision oncology enrollment. **Open source** .

- **[TrialGPT Agent (BioDSA)](https://github.com/RyanWangZf/BioDSA)**  
  Agent implementation based on the **TrialGPT framework** (Jin et al., *Nature Communications* 2024) . Extracts key clinical information from patient notes, searches ClinicalTrials.gov for actively recruiting trials, evaluates patient eligibility against criteria, and produces **ranked list of suitable trials with rationales**. Integrates with **GPT-4o** via API . **Open source** .

- **[Criteria-AI (clinicaltrials-multiagent)](https://github.com/adityashukla8/clinicaltrials-multiagent)**  
  Multi-agent, LLM-powered system for **clinical trial matching and protocol optimization**. Agent 1 evaluates patient eligibility against trial criteria; Agent 2 enriches matched trials via **Tavily web search**; Agents 3-5 perform **protocol optimization** (age gap analysis, biomarker threshold simulation) . Fetches real-world trials from **ClinicalTrials.gov**. Docker/CloudRun deployment. **Open source** .

### Additional Strong Open-Source Options

- **Production-Deployed**: **MatchMiner** (Dana-Farber, Princess Margaret) , **recruIT** (5 German university hospitals) , **CancerTrialMatch** (Avera) .
- **AI/LLM-Powered**: **TrialMatchAI** (Nature Comms, >90% recall) , **TrialGPT** (BioDSA agent) , **PTM-LLM** (IEEE, outperforms TrialGPT and GPT-4) , **Criteria-AI** (multi-agent protocol optimization) .
- **Blockchain + LLM**: Research frameworks combining blockchain for audit trails with LLM consensus for eligibility decisions .
- **HL7 FHIR Integration**: **HL7 Trial Matching** initiative with wrappers for BreastCancerTrials.org, TrialScope, and TrialJectory .

**Frameworks for building custom systems**: Combine **TrialMatchAI** for the AI-powered matching engine (local LLM deployment, Phenopackets support), **MatchMiner** for production-proven oncology matching with AI-enhanced EHR analysis, **recruIT** for OMOP/FHIR-based population screening, and **CancerTrialMatch** for biomarker-focused matching. Add **PostgreSQL/MongoDB** for persistence and **Docker** for deployment.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Clinical trial matching platforms handle sensitive patient health and genomic data; ensure compliance with HIPAA, GDPR, and applicable research regulations.
- **Open-source reality**: The open-source ecosystem for clinical trial matching is **mature and production-proven**, particularly in oncology. **MatchMiner** and **recruIT** are deployed at major institutions with measurable enrollment improvements . **TrialMatchAI** represents the state of the art in AI-powered matching with >90% recall . However, **commercial platforms** (Tempus, TriNetX, Flatiron) offer broader data networks, multi-therapeutic coverage, and enterprise support that open-source alternatives cannot match without significant institutional investment.

---

**Made for clinical research informaticists, oncology trial coordinators, precision medicine teams, and clinical data scientists.**
Let's make clinical trial matching more open, transparent, and patient-centered.
