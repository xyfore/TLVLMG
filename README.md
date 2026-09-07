# Making Large Vision Language Models Better Few-Shot Learners

[![Paper](https://img.shields.io/badge/Paper-IEEE_TIP-blue)](https://github.com/HUOUO7/TLVLMG)
[![Venue](https://img.shields.io/badge/Status-Accepted-brightgreen)](https://github.com/HUOUO7/TLVLMG)

This repository is the official implementation of the paper: **"Making Large Vision Language Models Better Few-Shot Learners"**, accepted by **IEEE Transactions on Image Processing (TIP)** on **September 2, 2025**.

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
* **Paper**: [Making Large Vision Language Models to Be Good Few-Shot Learners](https://arxiv.org/html/2408.11297v1)

---

## 📖 Introduction
Few-shot classification (FSC) aims to emulate the human ability to rapidly learn new concepts from a handful of examples. While Large Vision-Language Models (LVLMs) show promise, our research identifies two core bottlenecks:
1.  **Positional Bias**: Models like Qwen2.5-VL exhibit a strong "recency bias," favoring the last options in a support set.
2.  **Insufficient Learning**: Models tend to over-rely on pre-trained knowledge rather than genuinely generalizing from the provided support samples.

We propose a systematic optimization framework to address these challenges while significantly reducing inference latency.

---

## 🚀 Core Contributions

* **Position-Balanced Instruction Fine-Tuning (PB-FT)**: Corrects positional bias by constructing meta-tasks where the correct answer is uniformly distributed across all candidate positions.
* **Semantic-Guided Background Generation (SGBG)**: Uses GPT-4 guided prompts and Stable Diffusion to generate diverse backgrounds, breaking spurious visual correlations.
* **Hard Negative Mining Task Construction (HNMTC)**: Employs OpenCLIP-based similarity clustering to build more challenging meta-tasks, compelling the model to learn discriminative features.
* **Differentiated Token Pruning**: A two-stage framework that prunes support and query images with different ratios, reducing FLOPs to 19.2% while maintaining performance.

---

## 📅 Roadmap
- [x] Paper accepted by IEEE TIP (September 2, 2025).
- [ ] Release of Pre-trained LoRA weights (Upon Acceptance).
- [ ] Open-source training and evaluation scripts (Upon Acceptance).

---
