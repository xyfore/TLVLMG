# Making Large Vision Language Models Better Few-Shot Learners

[![Paper](https://img.shields.io/badge/Paper-IEEE_TIP-blue)](https://github.com/HUOUO7/TLVLMG)
[![Venue](https://img.shields.io/badge/Status-Under_Review-orange)](https://github.com/HUOUO7/TLVLMG)

This repository is the official implementation of the paper: **"Making Large Vision Language Models Better Few-Shot Learners"**, currently submitted to **IEEE Transactions on Image Processing (TIP)**.

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

## 📊 Experimental Results (5-way 1-shot)
Our methods achieve superior performance across multiple FSC benchmarks:

### General Benchmarks
| Method | MiniImageNet | CIFAR-FS | TieredImageNet |
| :--- | :---: | :---: | :---: |
| Qwen2.5-VL (Base) | 94.02% | 89.16% | 93.56% |
| **Ours** | **99.20%** | **97.24%** | **98.80%** |

### Fine-Grained Benchmarks
| Method | CUB-200 | Stanford Dogs | Stanford Cars |
| :--- | :---: | :---: | :---: |
| Qwen2.5-VL (Base) | 96.28% | 94.02% | 97.84% |
| **Ours** | **99.16%** | **98.26%** | **99.84%** |

---

## 📅 Roadmap
- [x] Paper submitted to IEEE TIP.
- [ ] Release of Pre-trained LoRA weights (Upon Acceptance).
- [ ] Open-source training and evaluation scripts (Upon Acceptance).

---

## 📝 Citation
If you find our work or code useful, please cite:

```bibtex
@article{zhang2026making,
  title={Making Large Vision Language Models Better Few-Shot Learners},
  author={Zhang, Chuanyi and Liu, Fan and Xu, Yi and An, Yuexuan and Cao, Shuhua and Deng, Cheng},
  journal={IEEE Transactions on Image Processing},
  year={2026}
}
