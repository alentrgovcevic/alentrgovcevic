# Alen Trgovcevic

I run a lab’s operations, manage its data and build the software it runs on. Bioinformatics engineer and full-stack builder at Aarhus University: native iOS and Android apps, production backends, ML/CV pipelines, offline LLM systems, lab infrastructure and HPC bioinformatics — designed, built and operated end to end.

**4** apps in production · **2,000+** users on TankBilligt · **3** payment rails live · **2** peer-reviewed publications

Portfolio: [alentrgovcevic.github.io](https://alentrgovcevic.github.io/) · [LinkedIn](https://www.linkedin.com/in/alen-trgovcevic/) · [ORCID 0000-0001-7709-6803](https://orcid.org/0000-0001-7709-6803)

Most project links go to a public architecture overview (stack, design and engineering decisions)

---

### Products & mobile apps
Four in production. TankBilligt, Bliv Klar and LabCompanion on both stores, Lynkort on iOS.

| Project | What it is | Stack | Status |
|---|---|---|---|
| [TankBilligt](https://github.com/alentrgovcevic/TankBilligt-overview) · [App Store](https://apps.apple.com/dk/app/tankbilligt-benzinpriser/id6757086573) · [Google Play](https://play.google.com/store/apps/details?id=dk.tankbilligt.android) | Denmark's cheapest-fuel app — 2,000+ users. iOS + Android + a Node/TS backend with server-side IAP validation and cron price-scraping. | SwiftUI · Compose · Express/TS · PostgreSQL | Production |
| [Bliv Klar](https://github.com/alentrgovcevic/BlivKlar) · [App Store](https://apps.apple.com/dk/app/bliv-klar-indf%C3%B8dsretspr%C3%B8ven/id6758513536) · [Google Play](https://play.google.com/store/apps/details?id=dk.atproductions.blivklar) | Danish citizenship exam prep on iOS, Android and web — the web flow takes real money through Stripe, with the receipt, right-of-withdrawal and terms pages Danish consumer law requires. | SwiftUI · Compose · Play Billing · Stripe/PHP | Production |
| [Lynkort](https://github.com/alentrgovcevic/Lynkort) · [App Store](https://apps.apple.com/dk/app/lynkort-flashcards/id6760855261) | Danish flashcards with a Leitner spaced-repetition engine, lock-screen widget, and zero external dependencies. Live on iOS; the Android build is unreleased. | SwiftUI · SwiftData · CloudKit | App Store |
| [LabCompanion](https://github.com/alentrgovcevic/LabCompanion-overview) · [App Store](https://apps.apple.com/dk/app/labcompanion-lab-calculator/id6770509131) · [Google Play](https://play.google.com/store/apps/details?id=dk.ATproductions.labcompanion) | Lab calculators and protocol timers for bench scientists, on iOS and Android — Lock Screen Live Activities and iCloud sync on iOS. | SwiftUI · ActivityKit · CloudKit · Compose · Play Billing | Production |

### Lab systems & infrastructure
The software a molecular biology section runs on, built and operated in-house.

| Project | What it is | Stack | Status |
|---|---|---|---|
| Lab server · [code (MIT template)](https://github.com/alentrgovcevic/lab_server_template) | The section’s shared web server: a map bank of 5,900+ plasmids (11,700+ map files) with bench tools — clone verification against Sanger reads, primer design, Golden Gate assembly with overhang diagnosis, Gibson assembly, BLAST — and a genome browser for any genome. Auto-deploy, and load tests that found the bottleneck; a cache then took browsing at 16 simultaneous users from 4.8 to 109 requests a second. The lab's instance is internal; the code is public as a reusable template. | FastAPI · SQLite · Docker · Caddy · Biopython | In service |
| Sequencing databases | Scattered RNA-seq studies consolidated for the section: barley (535 samples across 19 studies, harmonised matrix for the first 8, DE contrasts, a browsable results page) and Lotus japonicus (535 samples against two reference genomes). Plus a bacterial whole-genome pipeline built for about 96 isolates, validated on the first six against earlier CheckM values. | gwf · SLURM · STAR · DESeq2 · CheckM | In progress |
| [BREEDOME LIMS](https://github.com/alentrgovcevic/BREEDOME_LIMS) | A laboratory information system for a 4-node genome-editing facility. Ordering, oligos and personnel/permissions are built; consolidating four standalone databases into one is roughly half done. | FileMaker 2025 · RBAC · OAuth/OIDC | In build |

### AI & automation
On-prem LLMs, local-first pipelines, autonomous agents — and the tooling around them.

| Project | What it is | Stack | Status |
|---|---|---|---|
| [labRAG](https://github.com/alentrgovcevic/labRAG-overview) · [code](https://github.com/alentrgovcevic/labrag-portable) | A fully offline RAG assistant over lab protocols and safety documents — no cloud LLM ever sees the data. It cites a source on every answer, and says a protocol is not in the indexed set rather than inventing one. | Ollama · Python · local embeddings | Production |
| [Photo Pipeline](https://github.com/alentrgovcevic/PhotoPipeline) | A photographer's cull-to-stock automation: RAW culling, a three-axis local-AI scorer, and multi-agency submission. | OpenCV · Ollama · NIMA | Production |
| [cmdlog](https://github.com/alentrgovcevic/claude-code-cmdlog) | Reads Claude Code’s own session transcripts and builds one local page of every command the agent ran — by day and repository, with its output and a search over it. No hook, no daemon, no dependencies. | Python · SQLite FTS5 · stdlib-only · MIT | Open source |
| [Marketing Agent](https://github.com/alentrgovcevic/MarketingAgent) | Autonomous social-content pipeline designed to give retired hardware new life — data → generation → media → posting. | Docker · Gemini · Playwright · moviepy | Concept |

### Bioinformatics & scientific computing
HPC pipelines and rigorous, reproducible analysis.

| Project | What it is | Stack | Status |
|---|---|---|---|
| [genome-decoded](https://github.com/alentrgovcevic/genome-decoded) · [demo report](https://alentrgovcevic.github.io/genome-decoded/) | Turns a consumer DNA download into a readable, honest report — ancestry, drug response, HLA type, polygenic scores and ClinVar variants — without the genome leaving your machine. On NA12878: HLA 10 of 10 alleles; drug-gene calls exactly match the CDC GeT-RM consensus for 10 of 12 genes, the other two in part. | Snakemake · Beagle · PharmCAT · SLURM · MIT | Open source |
| [PhenoVision](https://github.com/alentrgovcevic/PhenoVision-overview) | A CV pipeline turning messy lab photos into publication-grade plant phenotype data with YOLOv8/11 + geometry. | YOLOv8/11 · OpenCV · skan | Production |
| [WA Pipelines](https://github.com/alentrgovcevic/WA_pipelines-overview) | HPC shotgun metagenomics of the wheat rhizoplane microbiome — gwf/SLURM, dual host-reference removal, Kraken2 + HUMAnN3. | gwf · SLURM · Kraken2 · R | Production |
| [Barley Root RNA-seq](https://github.com/alentrgovcevic/barley_root_rnaseq) | RNA-seq differential expression testing whether transgenes alter the barley root response to AMF — STAR + DESeq2 interaction model. | STAR · DESeq2 · R | Production |

### Independent research
Done on my own time. The method is the point; the subject is incidental.

| Project | What it is | Stack | Status |
|---|---|---|---|
| dmi-capture | A storm-surge forecast archive that nobody else keeps: DMI holds only a day or two of ocean forecasts and publishes no history. A capture-and-evaluation pipeline on an always-on box, with questions about the data put to DMI’s scientists and their answers kept on record. | Python · scheduling · forecast verification | Ongoing |
| aurora-watch | An aurora and cloud image classifier study with an external all-sky camera network. In a first test of 46 frames, two raters agreed on 97.8 % yet κ was only 0.657, because chance agreement was already 93.7 %. Solar geometry from scratch, matching the camera’s overlay to 0.007° in elevation. | Python · computer vision · inter-rater statistics | Research |

### Systems & security

| Project | What it is | Stack | Status |
|---|---|---|---|
| [Cybersecurity Toolkit](https://github.com/alentrgovcevic/CybersecurityToolkit) | Password entropy analyzer with privacy-preserving HIBP k-anonymity breach checks, plus a class-based port scanner. | Python · SHA-256 · HIBP | Toolkit |

### Publications
- **Signatures of Antagonistic Pleiotropy in a Bacterial Flagellin Epitope** — Cell Host & Microbe, 2021 — [10.1016/j.chom.2021.02.006](https://doi.org/10.1016/j.chom.2021.02.006)
- **A Conserved Juxtamembrane Motif in Plant NFR5 Receptors** — PNAS, 2021 — [10.1073/pnas.2101526118](https://doi.org/10.1073/pnas.2101526118)

---

Native mobile · production backends · payments and consumer-law compliance · ML/CV · offline LLM/RAG · lab infrastructure · HPC bioinformatics · laboratory data architecture.

[alen.trgovcevic@gmail.com](mailto:alen.trgovcevic@gmail.com) · AT Productions (CVR 46159640)
