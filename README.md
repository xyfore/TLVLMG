# Making Large Vision Language Models Better Few-Shot Learners

[![Paper](https://img.shields.io/badge/Paper-IEEE_TIP-blue)](https://github.com/HUOUO7/TLVLMG)
[![Venue](https://img.shields.io/badge/Status-Under_Review-orange)](https://github.com/HUOUO7/TLVLMG)

This repository is the official implementation of the paper: **"Making Large Vision Language Models Better Few-Shot Learners"**, currently submitted to **IEEE Transactions on Image Processing (TIP)**. 

---

## 🆕 Extension Highlights (TIP Version)
This work is a significant extension of our previous research published at **AAAI 2025**. Key upgrades include:
* **Base Model**: Upgraded from Qwen-VL to **Qwen2.5-VL**.
* **Debiasing**: Identified and corrected the **Recency Bias** in state-of-the-art LVLMs.
* **Learning Enhancement**: Introduced **Semantic-Guided Background Generation (SGBG)** and **Hard Negative Mining (HNMTC)**.
* **Inference Efficiency**: Proposed a **Differentiated Token Pruning** framework, achieving a **3.43x speedup** (FLOPs reduced to 19.2%).

---

## 📚 Previous Work (AAAI 2025)
For our preliminary study and code base, please refer to:
* **Project**: [MLVLM-FSL (AAAI 2025)](https://github.com/HUOUO7/MLVLM-FSL)
* **Paper**: [Making Large Vision Language Models to Be Good Few-Shot Learners](https://arxiv.org/abs/2412.14713)

---

## 📖 Introduction
Few-shot classification (FSC) is challenging for LVLMs due to two core bottlenecks:
1.  **Positional Bias**: Models exhibit severe biases (e.g., Primacy Bias in Qwen-VL, Recency Bias in Qwen2.5-VL), favoring specific option positions.
2.  **Insufficient Learning**: Models often over-rely on pre-trained knowledge rather than learning from the provided support samples.

Our TIP version addresses these issues while maintaining high efficiency via token pruning.

---

## 🚀 Step-by-Step Guide

### Step 1: Build Meta-task Instructions
Generate N-way K-shot instruction-following data.
* **Folder**: `build_data_instruction/`
* **Core Logic**: Converts datasets into formats where query samples are aligned with candidate answers, incorporating **Position-Balanced** distribution.

### Step 2: Instruction Fine-tuning
Perform QLoRA fine-tuning with our enhanced strategies.
* **Strategies**: 
    * **PB-FT**: Position-balanced training.
    * **SGBG**: Semantic-guided background augmentation via Stable Diffusion.
    * **Label Augmentation (LA)**: Character perturbation to break token overconfidence.
* **Script**: `finetune_qlora_ds_cww.sh`

### Step 3: Inference & Efficiency Optimization
* **Differentiated Token Pruning**: Prunes support and query images with different ratios to balance latency and accuracy.
* **Evaluation Action**: Execute scripts in `Test_Qwen_scripts/`.
* **Metric Calculation**: Use `cal_for_Qwen_using_CLIP.py` for `Acc`, `Acc_occur`, etc.

### Step 4: Attribute & Candidate Selection (Optional)
* **Attribute Generation**: `attribute_text/mllm_generate_text_v3.py` generates detailed visual attributes.
* **Candidate Selection (CS)**: Filters unreliable candidates to simplify the classification task during inference.

---

## 📊 Performance (5-way 1-shot)

| Dataset | AAAI 2025 | **Ours (TIP Extension)** | Improvement |
| :--- | :---: | :---: | :---: |
| MiniImageNet | 98.24% | **99.20%** | +0.96% |
| CIFAR-FS | 95.02% | **97.24%** | +2.22% |
| CUB-200 | 96.40% | **99.16%** | +2.76% |
| Stanford Cars | 99.72% | **99.84%** | +0.12% |

---

## 📂 Data Preparation
The experiments utilize datasets from **ELEVATER** for training and 8 established benchmarks for testing:
* **General**: MiniImageNet, CIFAR-FS, Tiered-ImageNet.
* **Fine-grained**: CUB, Stanford Dogs, FGVC-Aircraft, Oxford Flowers, Stanford Cars.

---

## 📅 Roadmap
- [x] Paper submitted to IEEE TIP.
- [ ] Release of Pre-trained LoRA weights (Upon Acceptance).
- [ ] Open-source full code-base (Upon Acceptance).

---

## 📝 Citation
```bibtex
@article{zhang2026making,
  title={Making Large Vision Language Models Better Few-Shot Learners},
  author={Zhang, Chuanyi and Liu, Fan and Xu, Yi and An, Yuexuan and Cao, Shuhua and Deng, Cheng},
  journal={IEEE Transactions on Image Processing},
  year={2026}
}

@inproceedings{liu2025making,
  title={Making Large Vision Language Models to Be Good Few-Shot Learners},
  author={Liu, Fan and Cai, Wenwen and Huo, Jian and Zhang, Chuanyi and Chen, Delong and Zhou, Jun},
  booktitle={Proceedings of the AAAI Conference on Artificial Intelligence},
  year={2025}
}
