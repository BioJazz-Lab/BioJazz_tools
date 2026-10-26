# AI Models for BioJazz Lab

**Maintained by:** Song Feng Lab, Department of Biology, Baylor University  
**Last updated:** 2026-10-26  
**Purpose:** Track AI/ML models relevant to BioJazz Lab research — phage-host interactions, genome-scale metabolic modeling, PTM-driven biomolecular assembly, and multi-scale eco-evolutionary dynamics.

---

## Table of Contents

1. [Protein Structure & Function](#protein-structure--function)
2. [Genomics & Metagenomics](#genomics--metagenomics)
3. [Metabolic Modeling & Systems Biology](#metabolic-modeling--systems-biology)
4. [Phage Biology & Viromics](#phage-biology--viromics)
5. [Multi-omics & Proteomics](#multi-omics--proteomics)
6. [Scientific Literature & Knowledge Retrieval](#scientific-literature--knowledge-retrieval)
7. [General-Purpose LLMs for Biology](#general-purpose-llms-for-biology)

---

## Protein Structure & Function

| Model | Description | Access | Notes |
|-------|-------------|--------|-------|
| **AlphaFold3** | Structure prediction for proteins, DNA, RNA, ligands, ions | [AlphaFold Server](https://alphafoldserver.com) / [GitHub](https://github.com/google-deepmind/alphafold3) | Best for single-chain and complex structures; supports PTMs |
| **AlphaFold2** | Protein monomer/multimer structure prediction | [ColabFold](https://colab.research.google.com/github/sokrypton/ColabFold/) / [GitHub](https://github.com/google-deepmind/alphafold) | Production-grade; ColabFold is fast alternative |
| **ESM-2 / ESMFold** | Protein language model (650M–15B params); fast structure prediction | [GitHub](https://github.com/facebookresearch/esm) / [ESM Metagenomic Atlas](https://esmatlas.com) | Great for large-scale screening; no MSA needed |
| **ESM-3** | Multimodal protein model (sequence, structure, function) | [GitHub](https://github.com/evolutionaryscale/esm) | Supports conditional generation; useful for design |
| **ProtTrans (ProtBERT, ProtT5)** | Protein sequence embeddings via transformer | [GitHub](https://github.com/ProtTrans/ProtTrans) / [HuggingFace](https://huggingface.co/Rostlab) | Good for representation learning; classification tasks |
| **RoseTTAFold2 / RoseTTAFold-All-Atom** | Structure prediction; supports small molecules | [GitHub](https://github.com/uw-ipd/RoseTTAFold2) | Handles non-protein atoms well |
| **DiffDock** | Diffusion-based protein–ligand docking | [GitHub](https://github.com/gcorso/DiffDock) | Relevant for enzyme–metabolite interactions |
| **ProteinMPNN** | Inverse folding / sequence design from backbone | [GitHub](https://github.com/dauparas/ProteinMPNN) | Useful for engineering phage tail fibers or enzymes |
| **SaProt** | Structure-aware protein language model | [GitHub](https://github.com/westlake-realerc/SaProt) | Combines sequence + structure tokens |
| **PhosphoSitePlus ML tools** | PTM site prediction | [PhosphoSitePlus](https://www.phosphosite.org) | Relevant for PTM-driven assembly project |
| **DeepPhos / NetPhos** | Phosphorylation site prediction | [NetPhos](https://services.healthtech.dtu.dk/services/NetPhos-3.1/) | Classical PTM prediction |

---

## Genomics & Metagenomics

| Model | Description | Access | Notes |
|-------|-------------|--------|-------|
| **Nucleotide Transformer (NT)** | DNA language models (500M–2.5B) for genomic sequences | [GitHub](https://github.com/instadeepai/nucleotide-transformer) / [HuggingFace](https://huggingface.co/InstaDeepAI) | Broad genomic tasks: variant effect, regulatory elements |
| **DNABERT-2** | Multi-species DNA foundation model | [GitHub](https://github.com/Zhihan1996/DNABERT-2) | Better than DNABERT-1; tokenization improvements |
| **Evo** | DNA language model trained on prokaryote/phage genomes | [GitHub](https://github.com/EvolutionaryScale/evo) | Particularly relevant for phage-host research |
| **HyenaDNA** | Long-range DNA model (up to 1M context) | [GitHub](https://github.com/HazyResearch/hyena-dna) | Long genomic context; efficient architecture |
| **Caduceus** | Bidirectional, long-range DNA model | [GitHub](https://github.com/kuleshov-group/caduceus) | State-space model; strong on genomic benchmarks |
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

## Contributing & Conventions

- Add a new row to the relevant table; include model name (bold), a brief description, an access link, and notes specific to BioJazz Lab use cases.
- Mark deprecated or superseded models with ~~strikethrough~~.
- For models actively in use in the lab, add a ✅ to the **Notes** column.
- Update the `Last updated` date at the top when making changes.

---

*For questions or suggestions, contact Song Feng (song.zhimu.feng@gmail.com).*
