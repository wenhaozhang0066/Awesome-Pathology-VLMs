# Awesome-Pathology-VLMs

**A curated awesome list of pathology vision-language models, datasets, benchmarks, and related resources.**

## News & Updates

- [Ongoing] This repository is being actively curated for pathology VLMs, datasets, benchmarks, and related resources.
- [Contributions Welcome] PRs for missing papers, code, project websites, datasets, benchmarks, venue updates, or metadata corrections are welcome.

## Table of Contents

- [1. Aim of the Project](#1-aim-of-the-project)
- [2. Pathology VLMs](#2-pathology-vlms)
  - [2.1 Contrastive / Dual-Encoder](#21-contrastive--dual-encoder)
  - [2.2 Generative / Instruction-Tuned](#22-generative--instruction-tuned)
  - [2.3 Reasoning / RL-Enhanced](#23-reasoning--rl-enhanced)
  - [2.4 Agent-Based Systems](#24-agent-based-systems)
  - [2.5 VLM-Augmented MIL](#25-vlm-augmented-mil)
- [3. Datasets and Benchmarks](#3-datasets-and-benchmarks)
- [4. Acknowledgements](#4-acknowledgements)
- [5. Citation](#5-citation)

## 1. Aim of the Project

This project aims to:

- **Curate** representative papers, datasets, and benchmarks in the field of pathology VLMs.
- **Organize** the related works by model paradigm and input granularity, including patch-level, ROI-level, and whole-slide-level methods.
- **Track** progress of open-source works in the field of pathology VLMs.
- **Help** researchers follow recent progress and identify open challenges in pathology VLMs.

## 2. Pathology VLMs

Use the **Granularity** column to mark where each system operates:

- `G1` = Patch / Tile
- `G2` = Region of interest (ROI)
- `G3` = Whole-slide image (WSI)

For systems spanning multiple levels, use combined labels such as `G1/G3` or `G2/G3`.

### 2.1 Contrastive / Dual-Encoder

Pathology VLMs trained with image-text contrastive alignment or related dual-encoder objectives.

| Model Name | Paper Title | Granularity | Venue | Resources | Summary |
| ---------- | ----------- | ----------- | ----- | --------- | ------- |
| PLIP | A Visual-Language Foundation Model for Pathology Image Analysis Using Medical Twitter | G1 | Nature Medicine 2023 | [Paper](https://doi.org/10.1038/s41591-023-02504-3) [Code](https://github.com/PathologyFoundation/plip) [Website](https://huggingface.co/spaces/vinid/webplip) | Introduces PLIP, a CLIP-style pathology VLM trained on OpenPath image-caption pairs for zero-shot classification and retrieval. |
| CONCH | A Visual-Language Foundation Model for Computational Pathology | G1/G2/G3 | Nature Medicine 2024 | [Paper](https://doi.org/10.1038/s41591-024-02856-4) [Code](https://github.com/mahmoodlab/CONCH) | Introduces CONCH, a large-scale CoCa-trained pathology VLM used for zero-shot classification, retrieval, captioning, and as a backbone for later systems. |
| MR-PLIP | Multi-Resolution Pathology-Language Pre-training Model with Text-Guided Visual Representation | G1/G2/G3 | CVPR 2025 | [Paper](https://arxiv.org/abs/2504.18856) [Code](https://github.com/BasitAlawode/MR-PLIP) | Scales pathology-language pretraining to multi-resolution TCGA-derived image-text pairs with text-guided visual representation learning. |
| MUSK | A Vision-Language Foundation Model for Precision Oncology | G1/G2/G3 | Nature 2025 | [Paper](https://doi.org/10.1038/s41586-024-08378-w) [Code](https://github.com/lilab-stanford/MUSK) | Introduces MUSK, a BEiT-3-style pathology VLM pretrained on large-scale image and text tokens for visual, text, multimodal, and prognosis tasks. |
| TITAN | Multimodal Whole Slide Foundation Model for Pathology | G1/G2/G3 | Nature Medicine 2025 | [Paper](https://doi.org/10.1038/s41591-025-03982-3) [Code](https://github.com/mahmoodlab/TITAN) | Introduces TITAN, a three-stage WSI foundation model aligning ROI captions and whole-slide reports for slide-level downstream tasks. |
| PRISM | PRISM: A Multi-Modal Generative Foundation Model for Slide-Level Histopathology | G2/G3 | arXiv 2024 | [Paper](https://arxiv.org/abs/2405.10254) | Combines a Virchow tile encoder, slide aggregator, and BioGPT-style decoder for slide-level histopathology modeling. |
| PRISM2 | PRISM2: Unlocking Multi-Modal General Pathology AI with Clinical Dialogue | G2/G3 | arXiv 2025 | [Paper](https://arxiv.org/abs/2506.13063) | Scales PRISM with substantially more WSIs and QA pairs and adds clinical-dialogue-style WSI interrogation. |
| HiPath | HiPath: Hierarchical Vision-Language Alignment for Structured Pathology Report Prediction | G2/G3 | arXiv 2026 | [Paper](https://arxiv.org/abs/2603.19957) | Uses hierarchical VL alignment over pathologist-selected ROIs for structured pathology report prediction with frozen UNI2 and Qwen3 backbones. |
| PathFLIP | PathFLIP: Fine-grained Language-Image Pretraining for Versatile Computational Pathology | G1/G2/G3 | AAAI 2026 | [Paper](https://doi.org/10.1609/aaai.v40i9.37649) | Extends contrastive language-image pretraining to WSI-level pathology using a small curated WSI-caption corpus. |

### 2.2 Generative / Instruction-Tuned

Pathology MLLMs that connect pathology visual encoders to language models and are trained or instruction-tuned for generation, dialogue, VQA, or report-style outputs.

| Model Name | Paper Title | Granularity | Venue | Resources | Summary |
| ---------- | ----------- | ----------- | ----- | --------- | ------- |
| LLaVA-Med | LLaVA-Med: Training a Large Language-and-Vision Assistant for Biomedicine in One Day | G1 | NeurIPS D&B 2023 | [Paper](https://arxiv.org/abs/2306.00890) [Code](https://github.com/microsoft/LLaVA-Med) | Establishes the biomedical visual-instruction-tuned VLM template using BiomedCLIP, Vicuna, and GPT-4-synthesized biomedical instructions. |
| Quilt-LLaVA | Quilt-LLaVA: Visual Instruction Tuning by Extracting Localized Narratives from Open-Source Histopathology Videos | G1 | CVPR 2024 | [Paper](https://arxiv.org/abs/2312.04746) [Code](https://github.com/aldraus/quilt-llava) [Website](https://quilt-llava.github.io/) | Builds a histopathology instruction-tuned assistant from localized narratives mined from YouTube pathology lectures. |
| PathAsst | PathAsst: A Generative Foundation AI Assistant Towards Artificial General Intelligence of Pathology | G1 | AAAI 2024 | [Paper](https://arxiv.org/abs/2305.15072) [Code](https://github.com/superjamessyx/Generative-Foundation-AI-Assistant-for-Pathology) | Introduces a pathology assistant and the PathCap and PathInstruct datasets for captioning and VQA-style instruction tuning. |
| PathChat | A Multimodal Generative AI Copilot for Human Pathology | G1/G2 | Nature 2024 | [Paper](https://doi.org/10.1038/s41586-024-07618-3) [Code](https://github.com/fedshyvana/pathology_mllm_training) | Introduces PathChat, a CONCH-based multimodal generative pathology copilot evaluated on expert diagnostic challenges. |
| PA-LLaVA | PA-LLaVA: A Large Language-Vision Assistant for Human Pathology Image Understanding | G1 | IEEE BIBM 2024 | [Paper](https://doi.org/10.1109/BIBM62325.2024.10821785) [Code](https://github.com/ddw2AIGROUP2CQUPT/PA-LLaVA) [Model](https://huggingface.co/OpenFace-CQUPT/Pathology-LLaVA) | Develops a pathology-focused LLaVA-style assistant with domain-aligned pathology image-text data and strong PathVQA results. |
| PathInsight | PathInsight: Instruction Tuning of Multimodal Datasets and Models for Intelligence Assisted Diagnosis in Histopathology | G1 | arXiv 2024 | [Paper](https://arxiv.org/abs/2408.07037) | Fine-tunes generic VLMs with PathEnhanceDS to improve histopathology classification and captioning performance. |
| Dr-LLaVA | Dr-LLaVA: Visual Instruction Tuning with Symbolic Clinical Grounding | G1 | NeurIPS MAR Workshop 2024 | [Paper](https://arxiv.org/abs/2405.19567) | Adds symbolic clinical grounding and PPO to a pathology VLM, reporting improved bone-marrow VQA and reduced hallucination. |
| PathGen | PathGen-1.6M: 1.6 Million Pathology Image-Text Pairs Generation through Multi-Agent Collaboration | G1 | arXiv 2024 | [Paper](https://arxiv.org/abs/2407.00203) [Dataset](https://huggingface.co/datasets/jamessyx/PathGen) | Uses a multi-agent pipeline to generate PathGen-1.6M and train PathGen-CLIP/PathGen-LLaVA for pathology VLM pretraining and instruction tuning. |
| PathologyVLM | PathologyVLM: A Large Vision-Language Model for Pathology Image Understanding | G1 | Artificial Intelligence Review 2025 | [Paper](https://doi.org/10.1007/s10462-025-11190-1) [Code](https://github.com/ddw2AIGROUP2CQUPT/PA-LLaVA) | Extends PA-LLaVA with domain-balanced curation and evaluates pathology VQA, classification, and human comparison settings. |
| SlideChat | SlideChat: A Large Vision-Language Assistant for Whole-Slide Pathology Image Understanding | G3 | CVPR 2025 | [Paper](https://arxiv.org/abs/2410.11761) [Code](https://github.com/uni-medical/SlideChat) [Website](https://uni-medical.github.io/SlideChat.github.io/) | Builds a WSI-level assistant using CONCH, LongNet, Qwen2.5, and Slide-Instruction for gigapixel slide VQA. |
| CPath-Omni | CPath-Omni: A Unified Multimodal Foundation Model for Patch and Whole Slide Image Analysis in Computational Pathology | G1/G2/G3 | CVPR 2025 | [Paper](https://arxiv.org/abs/2412.12077) [Code](https://github.com/PathFoundation/CPath-Omni) | Unifies patch- and WSI-level pathology analysis with a large multimodal model based on CPath-CLIP and Qwen2.5. |
| WSI-LLaVA | WSI-LLaVA: A Multimodal Large Language Model for Whole Slide Image | G2/G3 | ICCV 2025 | [Paper](https://arxiv.org/abs/2412.02141) [Dataset](https://huggingface.co/datasets/LyuLucas/WSI-Bench) [Website](https://wsi-llava.github.io/) | Trains a WSI-level LLaVA-style assistant on WSI-Bench for whole-slide visual question answering. |
| ANTONI-alpha | Democratising Pathology Co-Pilots: An Open Pipeline and Dataset for Whole-Slide Vision-Language Modelling | G3 | arXiv 2026 | [Paper](https://arxiv.org/abs/2512.17326) [Dataset](https://huggingface.co/datasets/SaltySander/HISTAI-Instruct) | Introduces Polysome and HISTAI-Instruct, then trains ANTONI-alpha as an open WSI-level pathology VQA co-pilot. |
| MLLM-HWSI | MLLM-HWSI: A Multimodal Large Language Model for Hierarchical Whole Slide Image Understanding | G1/G2/G3 | arXiv 2026 | [Paper](https://arxiv.org/abs/2603.23067) [Code](https://github.com/BasitAlawode/HWSI-MLLM) | Aligns pathology language with cell, patch, region, and WSI representations for hierarchical evidence-grounded WSI understanding. |

### 2.3 Reasoning / RL-Enhanced

Pathology VLMs or MLLMs that add explicit reasoning, chain-of-thought-style supervision, RLVR, preference optimization, structured memory, or reference-free evaluation.

| Model Name | Paper Title | Granularity | Venue | Resources | Summary |
| ---------- | ----------- | ----------- | ----- | --------- | ------- |
| EAGLE | EAGLE: Expert-Guided Self-Enhancement for Preference Alignment in Pathology Large Vision-Language Model | G1 | ACL 2025 | [Paper](https://doi.org/10.18653/v1/2025.acl-long.711) [Code](https://github.com/meidandz/EAGLE) | Uses expert-guided iterative DPO preference alignment to improve pathology VQA recall and visual-prompt robustness. |
| PathVLM-R1 | PathVLM-R1: A Reinforcement Learning-Driven Reasoning Model for Pathology Visual-Language Tasks | G1 | arXiv 2025 | [Paper](https://arxiv.org/abs/2504.09258) | Applies GRPO with format and accuracy rewards to Qwen2.5-VL using a small pathology RL set. |
| SmartPath-R1 | SmartPath-R1: A MoE-Based Multimodal Reasoner Unifying ROI and WSI Pathology Tasks | G1/G2/G3 | arXiv 2025 | [Paper](https://arxiv.org/abs/2507.17303) | Introduces a mixture-of-experts multimodal reasoner that spans patch, ROI, and WSI pathology tasks. |
| PathReasoner-R1 | PathReasoner-R1: Instilling Structured Reasoning into Pathology Vision-Language Model via Knowledge-Guided Policy Optimization | G1/G3 | arXiv 2026 | [Paper](https://arxiv.org/abs/2601.21617) | Uses WSI CoT data, trajectory-masked SFT, and entity-reward RL for structured WSI-level pathology reasoning. |
| PathMem | PathMem: Toward Cognition-Aligned Memory Transformation for Pathology MLLMs | G3 | arXiv 2026 | [Paper](https://arxiv.org/abs/2603.09943) | Adds a long-term to working-memory transformation mechanism so pathology MLLMs can ground reasoning in structured diagnostic knowledge. |
| PathGLS | PathGLS: Evaluating Pathology Vision-Language Models without Ground Truth through Multi-Dimensional Consistency | G1/G3 | arXiv 2026 | [Paper](https://arxiv.org/abs/2603.16113) [Code](https://github.com/My13ad/PathGLS) | Provides a reference-free pathology VLM evaluation framework for grounding, logic, and stability consistency. |
| Patho-R1 | Patho-R1: A Multimodal Reinforcement Learning-Based Pathology Expert Reasoner | G1 | AAAI 2026 | [Paper](https://doi.org/10.1609/aaai.v40i33.40071) [Code](https://github.com/Wenchuan-Zhang/Patho-R1) | Builds a Qwen2.5-VL pathology reasoner with CPT, CoT SFT on PathCoT, and GRPO/DAPO-style RL. |

### 2.4 Agent-Based Systems

Pathology systems where an LLM or MLLM orchestrates perception, slide navigation, retrieval, tool use, multi-scale inspection, or external domain-specific modules.

| Model Name | Paper Title | Granularity | Venue | Resources | Summary |
| ---------- | ----------- | ----------- | ----- | --------- | ------- |
| CPathAgent | CPathAgent: An Agent-based Foundation Model for Interpretable High-Resolution Pathology Image Analysis Mimicking Pathologists' Diagnostic Logic | G2/G3 | NeurIPS 2025 | [Paper](https://arxiv.org/abs/2505.20510) | Recasts WSI analysis as pathologist-like zoom-and-scan trajectories and introduces PathMMU-HR2 for ROI-scale VQA. |
| PathAgent | PathAgent: Toward Interpretable Analysis of Whole-slide Pathology Images via Large Language Model-based Agentic Reasoning | G1/G2/G3 | arXiv 2025 | [Paper](https://arxiv.org/abs/2511.17052) | Composes PLIP, Patho-R1, and Qwen3 in a training-free agent for whole-slide reasoning. |
| LAMMI-Pathology | LAMMI-Pathology: A Tool-Centric Bottom-Up LVLM-Agent Framework for Molecularly Informed Medical Intelligence in Pathology | G1/G2/G3 | arXiv 2026 | [Paper](https://arxiv.org/abs/2602.18773) | Builds a tool-centric LVLM-agent with trajectory-aware fine-tuning and a callable spatial-transcriptomics tool. |
| Patho-AgenticRAG | Patho-AgenticRAG: Towards Multimodal Agentic Retrieval-Augmented Generation for Pathology VLMs via Reinforcement Learning | G1 | AAAI 2026 | [Paper](https://doi.org/10.1609/aaai.v40i35.40239) [Code](https://github.com/Wenchuan-Zhang/Patho-AgenticRAG) | Combines multimodal retrieval, textbook vector search, and Patho-R1-based reasoning for agentic pathology RAG. |

### 2.5 VLM-Augmented MIL

Slide-level MIL methods that use frozen VLMs, text embeddings, prompts, or language-derived priors to improve WSI aggregation.

| Model Name | Paper Title | Granularity | Venue | Resources | Summary |
| ---------- | ----------- | ----------- | ----- | --------- | ------- |
| ViLa-MIL | ViLa-MIL: Dual-scale Vision-Language Multiple Instance Learning for Whole Slide Image Classification | G3 | CVPR 2024 | [Paper](https://doi.org/10.1109/CVPR52733.2024.01069) [Code](https://github.com/Jiangbo-Shi/ViLa-MIL) | Uses frozen CLIP and GPT-3.5-derived textual prompts with prototype-guided MIL for few-shot WSI classification. |
| VLEER | VLEER: Vision and Language Embeddings for Explainable Whole Slide Image Representation | G3 | MICCAI-W 2025 | [Paper](https://arxiv.org/abs/2502.20850) | Injects task-keyword text embeddings from frozen CONCH into WSI MIL aggregators for explainable slide representation. |
| SLIP | Slide-Level Prompt Learning with Vision Language Models for Few-Shot Multiple Instance Learning in Histopathology | G3 | ISBI 2025 | [Paper](https://arxiv.org/abs/2503.17238) [Code](https://github.com/LTS5/SLIP) | Learns slide-level prompts on top of a frozen CLIP VLM for few-shot histopathology MIL. |
| GMAT | GMAT: Grounded Multi-Agent Clinical Description Generation for Text Encoder in Vision-Language MIL for Whole Slide Image Classification | G3 | MICCAI-W 2025 | [Paper](https://arxiv.org/abs/2508.01293) | Generates grounded multi-agent clinical descriptors for a CONCH-MIL text encoder and trains only the MIL aggregator. |
| HistoSelect | Act Like a Pathologist: Tissue-Aware Whole Slide Image Reasoning | G2/G3 | CVPR 2026 | [Paper](https://arxiv.org/abs/2603.00667) [Code](https://github.com/winston52/HistoSelect) | Uses training-free question-guided tissue-aware coarse-to-fine patch retrieval for WSI reasoning with fewer visual tokens. |

## 3. Datasets and Benchmarks

This section tracks public or application-accessible datasets, benchmarks, and evaluation resources. Internal/private pretraining corpora without a public or request-access route are intentionally omitted.

| Dataset/Benchmark Name | Resources | Description |
| ---------------------- | --------- | ----------- |
| OpenPath | [Paper](https://doi.org/10.1038/s41591-023-02504-3) [Code](https://github.com/PathologyFoundation/plip) [Website](https://huggingface.co/spaces/vinid/webplip) | G1 pathology image-text pairs curated from public medical Twitter for PLIP training and retrieval. |
| Quilt-1M | [Paper](https://arxiv.org/abs/2306.11207) [Dataset](https://zenodo.org/records/8239942) [Code](https://github.com/wisdomikezogwo/quilt1m) [Website](https://quilt1m.github.io/) | Public histopathology image-caption corpus mined from educational videos; 437,878 images and roughly 802K captions. |
| Quilt-Instruct | [Paper](https://arxiv.org/abs/2312.04746) [Dataset](https://huggingface.co/datasets/wisdomik/QUILT-LLaVA-Instruct-107K) [Code](https://github.com/aldraus/quilt-llava) [Website](https://quilt-llava.github.io/) | G1 histopathology visual-instruction dataset with 107K QA pairs for Quilt-LLaVA. |
| Quilt-VQA | [Paper](https://arxiv.org/abs/2312.04746) [Dataset](https://huggingface.co/datasets/wisdomik/Quilt_VQA) [Code](https://github.com/aldraus/quilt-llava) [Website](https://quilt-llava.github.io/) | G1 patch-level histopathology VQA benchmark with 985 images and 1,283 QA pairs. |
| PathCap | [Paper](https://arxiv.org/abs/2305.15072) [Dataset](https://huggingface.co/datasets/jamessyx/PathCap) [Code](https://github.com/superjamessyx/Generative-Foundation-AI-Assistant-for-Pathology) | Public pathology image-text caption dataset with roughly 207K image-text pairs. |
| PathInstruct | [Paper](https://arxiv.org/abs/2305.15072) [Dataset](https://huggingface.co/datasets/jamessyx/PathInstruct) [Code](https://github.com/superjamessyx/Generative-Foundation-AI-Assistant-for-Pathology) | Public pathology instruction-tuning dataset with roughly 180K instructions. |
| LLaVA-Med-60K | [Paper](https://arxiv.org/abs/2306.00890) [Code](https://github.com/microsoft/LLaVA-Med) | Biomedical visual-instruction data released with LLaVA-Med, including the 60K instruction-tuning split. |
| PCaption-0.5M | [Paper](https://doi.org/10.1109/BIBM62325.2024.10821785) [Code](https://github.com/ddw2AIGROUP2CQUPT/PA-LLaVA) [Model](https://huggingface.co/OpenFace-CQUPT/Pathology-LLaVA) | Human pathology image-text corpus used by PA-LLaVA/PathologyVLM for domain alignment. |
| PathGen-1.6M | [Paper](https://arxiv.org/abs/2407.00203) [Dataset](https://huggingface.co/datasets/jamessyx/PathGen) | Public synthetic pathology corpus with 1.6M image-text pairs plus instruction data generated through multi-agent collaboration. |
| HISTAI-Instruct | [Paper](https://arxiv.org/abs/2512.17326) [Dataset](https://huggingface.co/datasets/SaltySander/HISTAI-Instruct) | Public WSI instruction-tuning dataset generated from HISTAI with 24,259 WSIs and more than 1.1M QA pairs. |
| Slide-Instruction / SlideBench-VQA | [Paper](https://arxiv.org/abs/2410.11761) [Dataset](https://huggingface.co/datasets/General-Medical-AI/SlideChat) [Code](https://github.com/uni-medical/SlideChat) [Website](https://uni-medical.github.io/SlideChat.github.io/) | Public WSI instruction and benchmark resource for SlideChat; includes TCGA and BCNB WSI VQA splits. |
| WSI-Bench | [Paper](https://arxiv.org/abs/2412.02141) [Dataset](https://huggingface.co/datasets/LyuLucas/WSI-Bench) [Website](https://wsi-llava.github.io/) | G3 WSI VQA benchmark with 179,569 QA pairs across 3 major categories and 11 task types. |
| PathCoT | [Paper](https://doi.org/10.1609/aaai.v40i33.40071) [Code](https://github.com/Wenchuan-Zhang/Patho-R1) | Reasoning-oriented pathology CoT data used by Patho-R1 for SFT and RL-enhanced pathology reasoning. |
| PathVQA | [Paper](https://arxiv.org/abs/2003.10286) [Dataset](https://huggingface.co/datasets/flaviagiammarino/path-vqa) [Code](https://github.com/KaveeshaSilva/PathVQA) | G1 pathology VQA benchmark with 4,998 images and 32,799 QA pairs. |
| PathMMU | [Paper](https://arxiv.org/abs/2401.16355) [Dataset](https://huggingface.co/datasets/jamessyx/PathMMU) [Code](https://github.com/PathMMU-Benchmark/PathMMU) [Website](https://pathmmu-benchmark.github.io/) | G1 pathology multimodal understanding benchmark with 24,067 items and 33,428 multiple-choice questions. |
| WSI-VQA | [Paper](https://arxiv.org/abs/2407.05603) [Code](https://github.com/cpystan/WSI-VQA) | G3 whole-slide VQA benchmark with 977 WSIs and 8,672 QA pairs. |
| REG2025 | [Website](https://reg2025.grand-challenge.org/data-description/) | Public Grand Challenge report-generation benchmark with 10,494 WSI-report pairs across seven organs. |
| TCGA | [Website](https://www.cancer.gov/ccg/research/genome-sequencing/tcga) [Portal](https://portal.gdc.cancer.gov/) | Public/request-access pan-cancer WSI and molecular resource widely used for WSI classification, VQA, report generation, survival, and pretraining. |
| CPTAC | [Website](https://proteomics.cancer.gov/programs/cptac) [Portal](https://proteomic.datacommons.cancer.gov/) | Public/request-access cancer proteogenomics resource used for external WSI classification and survival evaluation. |
| BRACS | [Paper](https://arxiv.org/abs/2111.04740) [Dataset](https://www.bracs.icar.cnr.it/) [Website](https://www.bracs.icar.cnr.it/) | G2/G3 ROI and WSI breast pathology classification benchmark with 547 WSIs and 4,539 ROIs. |
| EBRAINS Digital Brain Tumour Atlas | [Paper](https://doi.org/10.1038/s41597-022-01157-0) | Public brain-tumor histopathology resource with 3,115 slides across 126 tumor types, used for rare subtype evaluation. |
| PatchGastric | [Paper](https://arxiv.org/abs/2202.03432) [Dataset](https://zenodo.org/records/6550925) | G1 patch classification benchmark for 3-class gastric adenocarcinoma differentiation. |
| CAMELYON16 | [Paper](https://doi.org/10.1001/jama.2017.14585) [Dataset](https://camelyon16.grand-challenge.org/Data/) [Website](https://camelyon16.grand-challenge.org/) | G3 lymph-node metastasis detection benchmark with 400 WSIs. |
| PCam | [Paper](https://arxiv.org/abs/1806.03962) [Dataset](https://zenodo.org/records/2546921) [Code](https://github.com/basveeling/pcam) [Website](https://patchcamelyon.grand-challenge.org/) | G1 patch classification benchmark with 327,680 patches derived from CAMELYON16. |
| NCT-CRC-HE-100K | [Dataset](https://zenodo.org/records/1214456) | G1 9-class colorectal cancer patch classification benchmark with roughly 100K patches. |
| PanNuke | [Paper](https://arxiv.org/abs/2003.10778) [Dataset](https://huggingface.co/datasets/RationAI/PanNuke) [Website](https://warwick.ac.uk/fac/sci/dcs/research/tia/data/pannuke/) | G1 nuclei and tissue benchmark with multi-organ H&E patches and instance-level annotations. |
| PANDA | [Paper](https://doi.org/10.1038/s41591-021-01620-2) [Dataset](https://www.kaggle.com/c/prostate-cancer-grade-assessment/data) [Website](https://panda.grand-challenge.org/) | G3 prostate cancer Gleason grading benchmark with roughly 11,000 WSIs. |
| HEST-1k / HEST-Bench | [Paper](https://arxiv.org/abs/2406.16192) [Dataset](https://huggingface.co/datasets/MahmoodLab/hest) [Code](https://github.com/mahmoodlab/HEST) [Website](https://hest.readthedocs.io/) | Public spatial-transcriptomics and pathology benchmark with 1,229 ST profiles and paired morphology-expression data. |
| UBC-OCEAN | [Dataset](https://www.kaggle.com/competitions/UBC-OCEAN/data) | Public ovarian cancer WSI classification dataset used in WSI-level pathology model evaluation. |
| IMP-CRS 2024 | [Dataset](https://rdm.inesctec.pt/dataset/nis-2023-008) | Public/request-access colorectal WSI dataset with 5,333 biopsy and polypectomy slides from IMP Diagnostics. |
| PathGLS | [Paper](https://arxiv.org/abs/2603.16113) [Code](https://github.com/My13ad/PathGLS) | Reference-free pathology VLM evaluation resource spanning grounding, logic, and stability checks for patch and WSI settings. |

## 4. Acknowledgements

This repository builds upon many work of researchers and groups developing pathology vision-language models. We sincerely thank the author, maintainer, and the contributors of the papers, datasets, and benchmarks collected in this project.

## 5. Citation

If this repository is helpful for your project, please consider citing it:

```bibtex
@misc{awesome_pathology_vlms,
  title = {Awesome-Pathology-VLMs},
  author = {{Awesome-Pathology-VLMs Contributors}},
  journal = {Github repository},
  year = {2026},
  url = {https://github.com/easonPing/Awesome-Pathology-VLMs},
}
```
