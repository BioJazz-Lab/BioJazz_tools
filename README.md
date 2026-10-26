# AI Models and Modeling Tools for BioJazz Lab

**Maintained by:** BioJazz Lab, Department of Biology, Baylor University  
**Last updated:** 2026-10-26  
**Purpose:** Track AI/ML models relevant to BioJazz Lab research — phage-host interactions, genome-scale metabolic modeling, PTM-driven biomolecular assembly, and multi-scale eco-evolutionary dynamics.

---

## Table of Contents

1. [Virtual Cell & Cell Simulation](#virtual-cell--cell-simulation)
2. [Protein Structure Prediction](#protein-structure-prediction)
3. [Molecular Dynamics & Conformational Sampling](#molecular-dynamics--conformational-sampling)
4. [Protein-Ligand Docking & Binding Affinity](#protein-ligand-docking--binding-affinity)
5. [Genomics & Metagenomics](#genomics--metagenomics)
6. [Metabolic Modeling & Systems Biology](#metabolic-modeling--systems-biology)
7. [Phage Biology & Viromics](#phage-biology--viromics)
8. [Multi-omics & Proteomics](#multi-omics--proteomics)
9. [Scientific Literature & Knowledge Retrieval](#scientific-literature--knowledge-retrieval)
10. [General-Purpose LLMs for Biology](#general-purpose-llms-for-biology)
11. [Computational Tools & Algorithms](#computational-tools--algorithms)

---

## Virtual Cell & Cell Simulation

| Model | Description | Access | Notes |
|-------|-------------|--------|-------|
| **scGPT** | Single-cell foundation model (33M cells pre-trained); cell type annotation, perturbation prediction, GRN inference | [GitHub](https://github.com/bowang-lab/scGPT) | Strong zero-shot generalization across tissues |
| **Geneformer** | Transformer pre-trained on 30M single-cell profiles; in silico gene perturbations | [HuggingFace](https://huggingface.co/ctheodoris/Geneformer) | Predicts knockout effects without experiments |
| **scFoundation** | Large-scale single-cell foundation model (100M+ cells) | [GitHub](https://github.com/biomap-research/scFoundation) | Strong cross-tissue and cross-condition generalization |
| **UCE (Universal Cell Embeddings)** | Zero-shot single-cell embeddings; works across species without fine-tuning | [GitHub](https://github.com/snap-stanford/UCE) | Useful for cross-organism eco-evolutionary comparisons |
| **GEARS** | Graph-based model for predicting single and combinatorial genetic perturbations | [GitHub](https://github.com/snap-stanford/GEARS) | Predicts unseen perturbation outcomes from sc data |
| **CellOracle** | GRN inference + TF perturbation simulation from scRNA/scATAC | [GitHub](https://github.com/morris-lab/CellOracle) | Simulates cell fate changes; links GRN to cell identity |
| **SCENIC / SCENIC+** | Gene regulatory network inference from scRNA-seq and scATAC-seq | [GitHub](https://github.com/aertslab/scenicplus) | SCENIC+ integrates chromatin accessibility for GRN |
| **NicheNet** | Cell–cell communication via ligand–target inference | [GitHub](https://github.com/saeyslab/nichenetr) | Predicts intercellular signaling; relevant for phage-host and host–microbe contexts |
| **CellChat** | Quantitative inference of cell–cell signaling networks at pathway level | [GitHub](https://github.com/sqjin/CellChat) | Complements NicheNet; good for microbial community signaling |
| **scBERT** | BERT-based model for single-cell cell type annotation | [GitHub](https://github.com/TencentAILabHealthcare/scBERT) | Pre-trained on PanglaoDB |
| **CellTypist** | Automated cell type classification with curated model zoo | [GitHub](https://github.com/Teichlab/celltypist) | Fast inference; many pre-built tissue models |
| **AIDO.Cell** | AI-driven cell foundation model for multi-modal sequence-to-cell prediction | [GitHub](https://github.com/genbio-ai/AIDO) | Emerging; multi-task model spanning sequence to phenotype |
| **Cell2Sentence** | Translates single-cell expression data to/from natural language via LLMs | [GitHub](https://github.com/vandijklab/cell2sentence-ft) | Bridges LLM reasoning with single-cell biology |
| **Cellpose** | Deep learning segmentation of cells in 2D/3D images | [GitHub](https://github.com/MouseLand/cellpose) | Core tool for imaging-based phenomics and spatial omics |
| **PhysiCell** | Agent-based multicellular simulation (mechanistic, not ML) | [GitHub](https://github.com/MathCancer/PhysiCell) | Integrates with ML outputs for whole-tissue spatial modeling |
| **Virtual Cell (VCell)** | ODE/PDE/stochastic simulation of intracellular dynamics with spatial support | [vcell.org](https://vcell.org) | NRBSC platform; useful for mechanistic signaling models |
| **BioNetGen / PyBNG** | Rule-based modeling of biochemical reaction networks | [GitHub](https://github.com/RuleWorld/bionetgen) | Signaling network simulation; pairs well with parameter estimation tools (cf. pyModEst) |

---

## Protein Structure Prediction

| Model | Description | Access | Notes |
|-------|-------------|--------|-------|
| **AlphaFold3** | Structure prediction for proteins, DNA, RNA, ligands, ions | [AlphaFold Server](https://alphafoldserver.com) / [GitHub](https://github.com/google-deepmind/alphafold3) | Best for single-chain and complex structures; supports PTMs |
| **AlphaFold2** | Protein monomer/multimer structure prediction | [ColabFold](https://colab.research.google.com/github/sokrypton/ColabFold/) / [GitHub](https://github.com/google-deepmind/alphafold) | Production-grade; ColabFold is fast alternative |
| **OpenFold3** | Open-source community reimplementation of AlphaFold3 (permissive license) | [GitHub](https://github.com/aqlaboratory/openfold) | Enables training and fine-tuning; basis for AQAffinity |
| **RomeroLab/lightning-boltz** | PyTorch Lightning training framework for Boltz-1/2; biomolecular structure prediction | [GitHub](https://github.com/RomeroLab/lightning-boltz) | MIT-licensed; strong AlphaFold3 alternative for proteins, DNA, RNA, small molecules |
| **ESM-2 / ESMFold** | Protein language model (650M–15B params); fast structure prediction | [GitHub](https://github.com/facebookresearch/esm) / [ESM Metagenomic Atlas](https://esmatlas.com) | Great for large-scale screening; no MSA needed |
| **ESM-3** | Multimodal protein model (sequence, structure, function) | [GitHub](https://github.com/evolutionaryscale/esm) | Supports conditional generation; useful for design |
| **ProtTrans (ProtBERT, ProtT5)** | Protein sequence embeddings via transformer | [GitHub](https://github.com/ProtTrans/ProtTrans) / [HuggingFace](https://huggingface.co/Rostlab) | Good for representation learning; classification tasks |
| **RoseTTAFold2 / RoseTTAFold-All-Atom** | Structure prediction; supports small molecules | [GitHub](https://github.com/uw-ipd/RoseTTAFold2) | Handles non-protein atoms well |
| **ProteinMPNN** | Inverse folding / sequence design from backbone | [GitHub](https://github.com/dauparas/ProteinMPNN) | Useful for engineering phage tail fibers or enzymes |
| **SaProt** | Structure-aware protein language model | [GitHub](https://github.com/westlake-realerc/SaProt) | Combines sequence + structure tokens |
| **RFD4-Proteina** | Generative diffusion model for de novo protein design (NVIDIA + UW Institute for Protein Design; successor to RFDiffusion) | [HuggingFace](https://huggingface.co/nvidia/RFD4-Proteina) / [NVIDIA NIM](https://build.nvidia.com/ipd/rfd4-proteina) | 2026; open-weight; state-of-the-art backbone design |
| **se3_diffusion (FrameDiff)** | SE(3) diffusion model for de novo protein backbone generation | [GitHub](https://github.com/jasonkyuyim/se3_diffusion) | Generates diverse backbone scaffolds; ICML 2023 |
| **RigidSSL** | Rigidity-aware geometric pretraining for protein design and conformational ensembles | [GitHub](https://github.com/ZhanghanNi/RigidSSL) / [ICLR 2026](https://iclr.cc/virtual/2026/poster/10008912) | SSL using rigid body augmentation; improves design and ensemble prediction |
| **FoldDisco** | Ultra-fast discontinuous structural motif search across the protein universe | [GitHub](https://github.com/steineggerlab/folddisco) | From Steinegger lab; indexes and queries billions of structures |
| **PhosphoSitePlus ML tools** | PTM site prediction | [PhosphoSitePlus](https://www.phosphosite.org) | Relevant for PTM-driven assembly project |
| **DeepPhos / NetPhos** | Phosphorylation site prediction | [NetPhos](https://services.healthtech.dtu.dk/services/NetPhos-3.1/) | Classical PTM prediction |

---

## Molecular Dynamics & Conformational Sampling

| Model | Description | Access | Notes |
|-------|-------------|--------|-------|
| **ConforNets** | Latent-based conformational control built on OpenFold3; generates and steers protein conformational ensembles | [GitHub](https://github.com/aqlaboratory/confornets) / [arXiv](https://arxiv.org/abs/2604.18559) | From aqlaboratory (OpenFold3 team); 2026 |
| **BioEmu2** | Microsoft generative model for protein equilibrium conformational ensemble emulation | [GitHub](https://github.com/microsoft/bioemu) / [HuggingFace](https://huggingface.co/microsoft/bioemu2) | Replaces costly MD simulations for ensemble generation; thermodynamically grounded |
| **yesint/molar** | Rust + Python library for high-performance reading and analysis of MD trajectories | [GitHub](https://github.com/yesint/molar) / [Docs](https://docs.rs/molar) | Supports GROMACS, AMBER formats; fast alternative to MDAnalysis for large trajectories |
| **David-OConnor/dynamics** | Rust-based molecular dynamics simulation engine | [GitHub](https://github.com/David-OConnor/dynamics) / [Docs](https://docs.rs/dynamics) | Lightweight MD library; useful for custom simulation workflows |

---

## Protein-Ligand Docking & Binding Affinity

| Model | Description | Access | Notes |
|-------|-------------|--------|-------|
| **DiffDock** | Diffusion-based protein–ligand docking | [GitHub](https://github.com/gcorso/DiffDock) | State-of-the-art blind docking; relevant for enzyme–metabolite interactions |
| **DiffDock-Glide** | DiffDock pose sampling combined with Schrödinger Glide scoring for improved accuracy | [GitHub](https://github.com/gcorso/DiffDock) | Hybrid approach; Glide rescoring improves pose selection |
| **AQAffinity** | Structure-free binding affinity prediction built on OpenFold3 (SandboxAQ) | [SandboxAQ](https://www.sandboxaq.com/aqaffinity) / [Docs](https://docs.aisim.sandboxaq.com/aqaffinity) | High-speed drug potency prediction without requiring a solved structure; 2026 |

---

## Genomics & Metagenomics

| Model | Description | Access | Notes |
|-------|-------------|--------|-------|
| **Nucleotide Transformer (NT)** | DNA language models (500M–2.5B) for genomic sequences | [GitHub](https://github.com/instadeepai/nucleotide-transformer) / [HuggingFace](https://huggingface.co/InstaDeepAI) | Broad genomic tasks: variant effect, regulatory elements |
| **DNABERT-2** | Multi-species DNA foundation model | [GitHub](https://github.com/Zhihan1996/DNABERT-2) | Better than DNABERT-1; tokenization improvements |
| **Evo** | DNA language model trained on prokaryote/phage genomes | [GitHub](https://github.com/EvolutionaryScale/evo) | Particularly relevant for phage-host research |
| **HyenaDNA** | Long-range DNA model (up to 1M context) | [GitHub](https://github.com/HazyResearch/hyena-dna) | Long genomic context; efficient architecture |
| **Caduceus** | Bidirectional, long-range DNA model | [GitHub](https://github.com/kuleshov-group/caduceus) | State-space model; strong on genomic benchmarks |
| **MMseqs2** | Ultra-fast many-against-many protein/nucleotide sequence search and clustering | [GitHub](https://github.com/soedinglab/MMseqs2) | Essential for large-scale homology search and metagenomic annotation; orders of magnitude faster than BLAST |
| **GenoME** | Metagenomic classification and embedding | — | Useful for microbiome studies |
| **DeepMicro** | Deep learning for microbiome phenotype prediction | [GitHub](https://github.com/minoh0201/DeepMicro) | Relevant for eco-evolutionary microbiome work |

---

## Metabolic Modeling & Systems Biology

| Model | Description | Access | Notes |
|-------|-------------|--------|-------|
| **MICOM** | Community metabolic modeling (flux balance) | [GitHub](https://github.com/micom-dev/micom) | Multi-species FBA; relevant for microbial community metabolism |
| **DLKcat** | Deep learning–based kcat (enzyme turnover) prediction | [GitHub](https://github.com/SysBioChalmers/DLKcat) | Useful for parameterizing GEMs |
| **UniKP** | Unified enzyme kinetics prediction (kcat, Km, Ki) | [GitHub](https://github.com/Luo-SynBioLab/UniKP) | Broader than DLKcat |
| **TurNuP / NNKD** | kcat/Km prediction from sequence + substrate | — | Alternative kinetics tools |
| **FluxML / COBRA.py** | Constraint-based metabolic modeling frameworks | [GitHub](https://github.com/opencobra/cobrapy) | Core tools for genome-scale metabolic models |
| **GEM-PRO** | Structure-aware GEM construction | [GitHub](https://github.com/SBRG/GEM-PRO) | Links protein structure to metabolic models |
| **AutoML-GEM** | ML-guided GEM refinement | — | Gap-filling and curation |
| **DeepEC** | EC number prediction from sequence | [GitHub](https://github.com/kaistsystemsbiology/DeepEC) | Useful for annotating metabolic genes |
| **ECRECer** | Enzyme commission number prediction | [GitHub](https://github.com/zhangjlab/ECRECer) | Alternative to DeepEC |

---

## Phage Biology & Viromics

| Model | Description | Access | Notes |
|-------|-------------|--------|-------|
| **PhaTYP** | Phage lifestyle (lytic/lysogenic) prediction | [GitHub](https://github.com/KennthShang/PhaTYP) | Relevant for phage-host interaction studies |
| **CHERRY** | Phage-host interaction prediction | [GitHub](https://github.com/KennthShang/CHERRY) | Direct phage-host linkage from sequence |
| **iPHoP** | Integrated phage-host prediction | [GitHub](https://github.com/marbl/iPHoP) | Ensemble approach; recommended for metagenomics |
| **DeepHost** | Deep learning phage host range prediction | [GitHub](https://github.com/deephost) | Sequence-based host prediction |
| **VirSorter2** | Virus identification in metagenomic data | [GitHub](https://github.com/jiarong/VirSorter2) | Standard virome discovery tool |
| **VIBRANT** | Virus identification and annotation | [GitHub](https://github.com/AnantharamanLab/VIBRANT) | Good for viral metabolic annotation |
| **CheckV** | Quality assessment of viral genomes | [GitHub](https://github.com/apcamargo/checkv) | Essential QC before downstream analysis |
| **PhageAI** | Phage lifecycle AI platform | [PhageAI](https://phage.ai) | Commercial; useful for classification |
| **Evo (phage-tuned)** | Generative model for phage sequence design | [GitHub](https://github.com/EvolutionaryScale/evo) | Novel phage protein design |

---

## Multi-omics & Proteomics

| Model | Description | Access | Notes |
|-------|-------------|--------|-------|
| **Prosit** | Peptide fragmentation and retention time prediction | [GitHub](https://github.com/kusterlab/prosit) / [Prosit Server](https://www.proteomicsdb.org/prosit/) | Enhances MS/MS database search |
| **AlphaPeptStats** | Statistical analysis of proteomics data | [GitHub](https://github.com/MannLabs/alphapeptstats) | From Mann lab; PTM-aware |
| **MSBooster** | Deep learning–rescoring for proteomics | [GitHub](https://github.com/Nesvilab/MSBooster) | Integrates with FragPipe pipeline |
| **DeepMass:Prism** | Deep learning for proteomics data analysis | — | Spectral library generation |
| **MOFA+** | Multi-omics factor analysis | [GitHub](https://github.com/bioFAM/MOFA2) | Integrates transcriptomics, proteomics, metabolomics |
| **scVI / scANVI** | Single-cell multi-omics integration | [GitHub](https://github.com/scverse/scvi-tools) | Latent variable models for sc data |
| **totalVI** | Protein + RNA joint modeling (CITE-seq) | [scvi-tools](https://github.com/scverse/scvi-tools) | Part of scvi-tools ecosystem |
| **UnitedNet** | Multi-modal single-cell data integration | [GitHub](https://github.com/LiuLab-Bioelectronics-Harvard/UnitedNet) | Transfer between modalities |

---

## Scientific Literature & Knowledge Retrieval

| Model | Description | Access | Notes |
|-------|-------------|--------|-------|
| **PubMedBERT** | BERT pre-trained on PubMed abstracts | [HuggingFace](https://huggingface.co/microsoft/BiomedNLP-BiomedBERT-base-uncased-abstract) | Strong for biomedical NLP tasks |
| **BioGPT** | Generative model for biomedical text | [GitHub](https://github.com/microsoft/BioGPT) | Relation extraction, QA |
| **BioMedLM (PubMedGPT)** | 2.7B GPT model on PubMed | [HuggingFace](https://huggingface.co/stanford-crfm/BioMedLM) | Smaller, biomedically-focused |
| **SciSpace / Semantic Scholar API** | Literature discovery and summarization | [SciSpace](https://typeset.io) / [S2 API](https://api.semanticscholar.org) | Useful for literature mining workflows |
| **Elicit** | AI-powered systematic review assistant | [Elicit](https://elicit.com) | Efficient for literature review |
| **Galactica** | Scientific text and formula model (Meta) | [GitHub](https://github.com/paperswithcode/galai) | Knowledge retrieval; use with caution |

---

## General-Purpose LLMs for Biology

| Model | Description | Access | Notes |
|-------|-------------|--------|-------|
| **Claude (Anthropic)** | Reasoning, writing, code generation | [claude.ai](https://claude.ai) / [API](https://docs.anthropic.com) | Strong for scientific writing, code, analysis workflows |
| **GPT-4o / o1 (OpenAI)** | Multimodal reasoning and code | [API](https://platform.openai.com) | Vision useful for figure analysis |
| **Gemini 1.5 Pro / 2.0** | Long-context multimodal model | [Google AI](https://ai.google.dev) | 1M token context; good for long documents |
| **Llama 3.x (Meta)** | Open-weight LLM for local deployment | [GitHub](https://github.com/meta-llama/llama3) | Self-host for sensitive data |
| **Mistral / Mixtral** | Efficient open-weight models | [GitHub](https://github.com/mistralai/mistral-src) | Good for local/HPC deployment |
| **BioMistral** | Mistral fine-tuned on biomedical literature | [HuggingFace](https://huggingface.co/BioMistral) | Biomedical QA and summarization |
| **Med-PaLM 2** | Google's medical reasoning model | Research access only | Clinical reasoning benchmark leader |

---

## Computational Tools & Algorithms

| Tool | Description | Access | Notes |
|------|-------------|--------|-------|
| **bigraph-rs** | Rust implementation of bigraph data structures (bigraphical reactive systems) | [GitHub](https://github.com/sebschmi/bigraph-rs) / [Docs](https://docs.rs/bigraph) | Formal graph model for concurrent biological systems; useful for network topology analysis |

---

## Contributing & Conventions

- Add a new row to the relevant table; include model name (bold), a brief description, an access link, and notes specific to BioJazz Lab use cases.
- Mark deprecated or superseded models with ~~strikethrough~~.
- For models actively in use in the lab, add a ✅ to the **Notes** column.
- Update the `Last updated` date at the top when making changes.

---

*For questions or suggestions, contact Song Feng (song.zhimu.feng@gmail.com).*
