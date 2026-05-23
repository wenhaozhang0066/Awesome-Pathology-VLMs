# Awesome-Pathology-VLMs

**A curated awesome list of pathology vision-language models, datasets, benchmarks, and related resources.**

*Photo Credit: [ChatGPT Images 2.0](https://openai.com/index/introducing-chatgpt-images-2-0/).*

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
- [6. Star History](#6-star-history)

## 1. Aim of the Project

This project aims to:

- **Curate** representative papers, datasets, and benchmarks in the field of pathology VLMs.
- **Organize** the related works by model paradigm and input granularity, including patch-level, ROI-level, and whole-slide-level methods.
- **Track** progress of open-source works in the field of pathology VLMs.
- **Help** researchers follow recent progress and identify open challenges in pathology VLMs.

## 2. Pathology VLMs

Use the **Granularity** column to indicate the main pathology image level each system operates on:

- `G1` = Patch / Tile
- `G2` = Region of interest (ROI)
- `G3` = Whole-slide image (WSI)

For systems spanning multiple levels, use combined labels such as `G1/G3` or `G2/G3`.

### 2.1 Contrastive / Dual-Encoder

Pathology VLMs trained with image-text contrastive alignment or related dual-encoder objectives.


| Model Name | Paper Title                                                                                   | Granularity | Resources | Summary                                                                                                                                                   |
| ---------- | --------------------------------------------------------------------------------------------- | ----------- | --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PLIP       | A Visual-Language Foundation Model for Pathology Image Analysis Using Medical Twitter         | G1          |           | Introduces PLIP, a CLIP-style pathology VLM trained on OpenPath image-caption pairs for zero-shot classification and retrieval.                           |
| CONCH      | A Visual-Language Foundation Model for Computational Pathology                                | G1/G2/G3    |           | Introduces CONCH, a large-scale CoCa-trained pathology VLM used for zero-shot classification, retrieval, captioning, and as a backbone for later systems. |
| MR-PLIP    | Multi-Resolution Pathology-Language Pre-training Model with Text-Guided Visual Representation | G1/G2/G3    |           | Scales pathology-language pretraining to multi-resolution TCGA-derived image-text pairs with text-guided visual representation learning.                  |
| MUSK       | A Vision-Language Foundation Model for Precision Oncology                                     | G1/G2/G3    |           | Introduces MUSK, a BEiT-3-style pathology VLM pretrained on large-scale image and text tokens for visual, text, multimodal, and prognosis tasks.          |
| TITAN      | Multimodal Whole Slide Foundation Model for Pathology                                         | G1/G2/G3    |           | Introduces TITAN, a three-stage WSI foundation model aligning ROI captions and whole-slide reports for slide-level downstream tasks.                      |
| PRISM      | PRISM: A Multi-Modal Generative Foundation Model for Slide-Level Histopathology               | G2/G3       |           | Combines a Virchow tile encoder, slide aggregator, and BioGPT-style decoder for slide-level histopathology modeling.                                      |
| PRISM2     | PRISM2: Unlocking Multi-Modal General Pathology AI with Clinical Dialogue                     | G2/G3       |           | Scales PRISM with substantially more WSIs and QA pairs and adds clinical-dialogue-style WSI interrogation.                                                |
| HiPath     | HiPath: Hierarchical Vision-Language Alignment for Structured Pathology Report Prediction     | G2/G3       |           | Uses hierarchical VL alignment over pathologist-selected ROIs for structured pathology report prediction with frozen UNI2 and Qwen3 backbones.            |
| PathFLIP   | PathFLIP: Fine-grained Language-Image Pretraining for Versatile Computational Pathology       | G1/G2/G3    |           | Extends contrastive language-image pretraining to WSI-level pathology using a small curated WSI-caption corpus.                                           |


### 2.2 Generative / Instruction-Tuned

Pathology MLLMs that connect pathology visual encoders to language models and are trained or instruction-tuned for generation, dialogue, VQA, or report-style outputs.


| Model Name   | Paper Title                                                                                                             | Granularity | Resources | Summary                                                                                                                                   |
| ------------ | ----------------------------------------------------------------------------------------------------------------------- | ----------- | --------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| LLaVA-Med    | LLaVA-Med: Training a Large Language-and-Vision Assistant for Biomedicine in One Day                                    | G1          |           | Establishes the biomedical visual-instruction-tuned VLM template using BiomedCLIP, Vicuna, and GPT-4-synthesized biomedical instructions. |
| Quilt-LLaVA  | Quilt-LLaVA: Visual Instruction Tuning by Extracting Localized Narratives from Open-Source Histopathology Videos        | G1          |           | Builds a histopathology instruction-tuned assistant from localized narratives mined from YouTube pathology lectures.                      |
| PathAsst     | PathAsst: A Generative Foundation AI Assistant Towards Artificial General Intelligence of Pathology                     | G1          |           | Introduces a pathology assistant and the PathCap and PathInstruct datasets for captioning and VQA-style instruction tuning.               |
| PathChat     | A Multimodal Generative AI Copilot for Human Pathology                                                                  | G1/G2       |           | Introduces PathChat, a CONCH-based multimodal generative pathology copilot evaluated on expert diagnostic challenges.                     |
| PA-LLaVA     | PA-LLaVA: A Large Language-Vision Assistant for Human Pathology Image Understanding                                     | G1          |           | Develops a pathology-focused LLaVA-style assistant with domain-aligned pathology image-text data and strong PathVQA results.              |
| PathInsight  | PathInsight: Instruction Tuning of Multimodal Datasets and Models for Intelligence Assisted Diagnosis in Histopathology | G1          |           | Fine-tunes generic VLMs with PathEnhanceDS to improve histopathology classification and captioning performance.                           |
| Dr-LLaVA     | Dr-LLaVA: Visual Instruction Tuning with Symbolic Clinical Grounding                                                    | G1          |           | Adds symbolic clinical grounding and PPO to a pathology VLM, reporting improved bone-marrow VQA and reduced hallucination.                |
| PathologyVLM | PathologyVLM: A Large Vision-Language Model for Pathology Image Understanding                                           | G1          |           | Extends PA-LLaVA with domain-balanced curation and evaluates pathology VQA, classification, and human comparison settings.                |
| SlideChat    | SlideChat: A Large Vision-Language Assistant for Whole-Slide Pathology Image Understanding                              | G3          |           | Builds a WSI-level assistant using CONCH, LongNet, Qwen2.5, and Slide-Instruction for gigapixel slide VQA.                                |
| CPath-Omni   | CPath-Omni: A Unified Multimodal Foundation Model for Patch and Whole Slide Image Analysis in Computational Pathology   | G1/G2/G3    |           | Unifies patch- and WSI-level pathology analysis with a large multimodal model based on CPath-CLIP and Qwen2.5.                            |
| WSI-LLaVA    | WSI-LLaVA: A Multimodal Large Language Model for Whole Slide Image                                                      | G2/G3       |           | Trains a WSI-level LLaVA-style assistant on WSI-Bench for whole-slide visual question answering.                                          |
| MLLM-HWSI    | MLLM-HWSI: A Multimodal Large Language Model for Hierarchical Whole Slide Image Understanding                           | G1/G2/G3    |           | Aligns pathology language with cell, patch, region, and WSI representations for hierarchical evidence-grounded WSI understanding.         |


### 2.3 Reasoning / RL-Enhanced

Pathology VLMs or MLLMs that add explicit reasoning, chain-of-thought-style supervision, RLVR, preference optimization, structured memory, or reference-free evaluation.


| Model Name      | Paper Title                                                                                                                    | Granularity | Resources | Summary                                                                                                                                                                                              |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------ | ----------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| EAGLE           | EAGLE: Expert-Guided Self-Enhancement for Preference Alignment in Pathology Large Vision-Language Model                        | G1          |           | Synthesizes about 150K preference pairs of chosen and rejected responses, and applies iterative DPO-based PFT to reduce multimodal hallucination and biased responses.                               |
| PathVLM-R1      | PathVLM-R1: A Reinforcement Learning-Driven Reasoning Model for Pathology Visual-Language Tasks                                | G1          |           | Injects domain knowledge via SFT and applies GRPO with format and accuracy rewards to Qwen2.5-VL-7B-Instruct.                                                                                        |
| SmartPath-R1    | SmartPath-R1: A MoE-Based Multimodal Reasoner Unifying ROI and WSI Pathology Tasks                                             | G1/G2/G3    |           | Combines scale-dependent SFT, task-aware reinforcement fine-tuning, and MoE routing to solve multi-tasks on both ROI and WSI level.                                                                  |
| PathReasoner-R1 | PathReasoner-R1: Instilling Structured Reasoning into Pathology Vision-Language Model via Knowledge-Guided Policy Optimization | G1/G3       |           | Uses knowledge graph to align pathological findings and clinical reasoning with diagnoses, constructs a WSI reasoning dataset, and applies trajectory-masked SFT and multi-granular reward function. |
| PathMem         | PathMem: Toward Cognition-Aligned Memory Transformation for Pathology MLLMs                                                    | G3          |           | Builds a pathology knowledge graph as long-term memory and activates relevant long time memory into working memory for WSI level pathology reasoning                                                 |
| Patho-R1        | Patho-R1: A Multimodal Reinforcement Learning-Based Pathology Expert Reasoner                                                  | G1          |           | Applies continued pretraining, SFT on CoT samples, and fine-tuning with GRPO and DAPO on Qwen2.5-VL, and trains a model to access alignment quality.                                                 |


### 2.4 Agent-Based Systems

Pathology systems where an LLM or MLLM orchestrates perception, slide navigation, retrieval, tool use, multi-scale inspection, or external domain-specific modules.


| Model Name       | Paper Title                                                                                                                                     | Granularity | Resources | Summary                                                                                                                                                                                     |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| CPathAgent       | CPathAgent: An Agent-based Foundation Model for Interpretable High-Resolution Pathology Image Analysis Mimicking Pathologists' Diagnostic Logic | G2/G3       |           | Mimics the opperations in pathologist workflow, unifies patch-level, region-level, and WSI-level capability in one model, and constructs benchmark for large region analysis.               |
| PathAgent        | PathAgent: Toward Interpretable Analysis of Whole-slide Pathology Images via Large Language Model-based Agentic Reasoning                       | G1/G2/G3    |           | Builds a training-free LLM-based agent framework that automatically explore WSI, locate micro-regions, extract visual cues, and integrate findings into trajectories.                       |
| LAMMI-Pathology  | LAMMI-Pathology: A Tool-Centric Bottom-Up LVLM-Agent Framework for Molecularly Informed Medical Intelligence in Pathology                       | G1/G2/G3    |           | Builds a agent system with domain-adaptive tools and a planner, develops the unit of semi-simulated reasoning trajectory, and aligns planner's decision making with reasoning trajectories. |
| Patho-AgenticRAG | Patho-AgenticRAG: Towards Multimodal Agentic Retrieval-Augmented Generation for Pathology VLMs via Reinforcement Learning                       | G1          |           | Builds a multimodal RAG system with datasets from authoritative pathology textbook, which support joint text-image search.                                                                  |


### 2.5 VLM-Augmented MIL

Slide-level MIL methods that use frozen VLMs, text embeddings, prompts, or language-derived priors to improve WSI aggregationa


| Model Name  | Paper Title                                                                                                                             | Granularity | Resources | Summary                                                                                                                                                        |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------------- | ----------- | --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ViLa-MIL    | ViLa-MIL: Dual-scale Vision-Language Multiple Instance Learning for Whole Slide Image Classification                                    | G3          |           | Uses dual-scale visual descriptive prompts with prototype-guided patch decoder and context guided text decoder to transfer VLM priors into WSI classification. |
| VLEER       | VLEER: Vision and Language Embeddings for Explainable Whole Slide Image Representation                                                  | G3          |           | Uses pretrained pathology VLMs and task-specific keyword pools to learn interpretable WSI embeddings.                                                          |
| SLIP        | Slide-Level Prompt Learning with Vision Language Models for Few-Shot Multiple Instance Learning in Histopathology                       | G3          |           | Uses pathological prior knowledge from language models to identify crucial local tissue types for WSI classification.                                          |
| GMAT        | GMAT: Grounded Multi-Agent Clinical Description Generation for Text Encoder in Vision-Language MIL for Whole Slide Image Classification | G3          |           | Uses multi-agent description generation system based to generated a list of descriptions to improve WSI classification alignment                               |
| HistoSelect | Act Like a Pathologist: Tissue-Aware Whole Slide Image Reasoning                                                                        | G2/G3       |           | Applies a framewrok to select question-relevent tissue regions and informatic patches from the regions, reduces visual token usage, and improves accuracy.     |


## 3. Datasets and Benchmarks

This section tracks public or application-accessible multimodal datasets, benchmarks, and evaluation resources. Purely image-only classification, segmentation, detection, or retrieval datasets are intentionally omitted, as are internal/private pretraining corpora without a public or request-access route.

Use the **Granularity** column to indicate the data/evaluation input level of each dataset or benchmark:

- `G1` = Patch / Tile
- `G2` = Region of interest (ROI)
- `G3` = Whole-slide image (WSI)

For datasets or benchmarks spanning multiple levels, use combined labels such as `G1/G3` or `G2/G3`. Use `N/A` for non-pathology auxiliary resources where these pathology image levels do not apply.


| Dataset/Benchmark Name        | Granularity | Resources | Description                                                                                                                                                                           |
| ----------------------------- | ----------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| OpenPath                      | G1          |           | Pathology image-text pairs curated from public medical Twitter for PLIP training and retrieval.                                                                                       |
| Quilt-1M                      | G1          |           | Public histopathology image-caption corpus mined from educational videos; 437,878 images and roughly 802K captions.                                                                   |
| Quilt-Instruct                | G1          |           | Histopathology visual-instruction dataset with 107K QA pairs for Quilt-LLaVA.                                                                                                         |
| Quilt-VQA                     | G1          |           | Patch-level histopathology VQA benchmark with 985 images and 1,283 QA pairs.                                                                                                          |
| PathCap                       | G1          |           | Public pathology image-text caption dataset with roughly 207K image-text pairs.                                                                                                       |
| PathInstruct                  | G1          |           | Public pathology instruction-tuning dataset with roughly 180K instructions.                                                                                                           |
| LLaVA-Med-60K                 | G1          |           | Biomedical visual-instruction data released with LLaVA-Med, including the 60K instruction-tuning split.                                                                               |
| PCaption-0.5M                 | G1          |           | Human pathology image-text corpus used by PA-LLaVA/PathologyVLM for domain alignment.                                                                                                 |
| PathGen-1.6M                  | G1          |           | Public synthetic pathology corpus with 1.6M image-text pairs plus instruction data generated through multi-agent collaboration.                                                       |
| HISTAI-Instruct               | G3          |           | Public WSI instruction-tuning dataset generated from HISTAI with the Polysome pipeline; contains 24,259 WSIs and more than 1.1M instruction-response pairs for training ANTONI-alpha. |
| Slide-Instruction             | G3          |           | Public WSI instruction-tuning dataset for SlideChat built from TCGA and BCNB whole-slide sources.                                                                                     |
| SlideBench-VQA                | G3          |           | Public WSI VQA benchmark resource released with SlideChat for whole-slide pathology question answering.                                                                               |
| WSI-Bench                     | G3          |           | WSI VQA benchmark with 179,569 QA pairs across 3 major categories and 11 task types.                                                                                                  |
| PathCoT                       | G1          |           | Reasoning-oriented pathology CoT data used by Patho-R1 for SFT and RL-enhanced pathology reasoning.                                                                                   |
| PathReasoner                  | G3          |           | WSI reasoning dataset with more than 20K knowledge-guided instructional samples for PathReasoner-R1.                                                                                  |
| PathVQA                       | G1          |           | Pathology VQA benchmark with 4,998 images and 32,799 QA pairs.                                                                                                                        |
| PathMMU                       | G1          |           | Pathology multimodal understanding benchmark with 24,067 items and 33,428 multiple-choice questions.                                                                                  |
| WSI-VQA                       | G3          |           | Whole-slide VQA benchmark with 977 WSIs and 8,672 QA pairs.                                                                                                                           |
| REG2025                       | G3          |           | Public Grand Challenge report-generation benchmark with 10,494 WSI-report pairs across seven organs.                                                                                  |
| TCGA                          | G3          |           | Public/request-access pan-cancer WSI and molecular resource widely used for WSI classification, VQA, report generation, survival, and pretraining.                                    |
| CPTAC                         | G3          |           | Public/request-access cancer proteogenomics resource used for external WSI classification and survival evaluation.                                                                    |
| HEST-1k                       | G2/G3       |           | Public spatial-transcriptomics and pathology dataset with 1,229 ST profiles and paired morphology-expression data.                                                                    |
| HEST-Bench                    | G2/G3       |           | Benchmark suite released with HEST for morphology-to-spatial-transcriptomics prediction and related pathology tasks.                                                                  |
| PathGLS                       | G1/G3       |           | Reference-free pathology VLM evaluation resource spanning grounding, logic, and stability checks for patch and WSI settings.                                                          |
| LAION-5B                      | N/A         |           | Large-scale public image-text source used as part of OpenPath/PLIP data curation.                                                                                                     |
| PubMed Central-OA             | G1          |           | Public biomedical open-access article image-text source used for biomedical and pathology VLM pretraining.                                                                            |
| ARCH                          | G1          |           | Public pathology image-text dataset curated from textbooks and articles for retrieval and image-text evaluation.                                                                      |
| PathPedia                     | G1          |           | Public pathology education atlas used as an external PLIP validation/retrieval source.                                                                                                |
| PathQABench-Public            | G1/G2       |           | Public TCGA-derived subset of PathChat's expert-curated pathology question-answering benchmark.                                                                                       |
| VQA-RAD                       | N/A         |           | Public radiology visual-question-answering benchmark used in biomedical VLM evaluation such as LLaVA-Med.                                                                             |
| SLAKE                         | N/A         |           | Public medical visual-question-answering benchmark used in biomedical VLM evaluation such as LLaVA-Med.                                                                               |
| TITAN TCGA-Derived Benchmarks | G3          |           | TCGA-derived public benchmark splits introduced by TITAN, including TCGA-UniformTumor-8K, TCGA-OncoTree, and TCGA-Slide-Reports.                                                      |


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

## 6. Star History

[Star History Chart](https://star-history.com/#easonPing/Awesome-Pathology-VLMs&Date)