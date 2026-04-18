# Making Large Vision Language Models Better Few-Shot Learners [cite: 2]

[![Paper](https://img.shields.io/badge/Paper-IEEE_TIP-blue)](https://github.com/HUOUO7/TLVLMG)
[![Venue](https://img.shields.io/badge/Status-Under_Review-orange)](https://github.com/HUOUO7/TLVLMG)

[cite_start]This repository is the official implementation of the paper: **"Making Large Vision Language Models Better Few-Shot Learners"** [cite: 2][cite_start], currently submitted to **IEEE Transactions on Image Processing (TIP)**[cite: 1].

---

## 📖 Introduction
[cite_start]Few-shot classification (FSC) aims to emulate the human ability to rapidly learn new concepts from a handful of examples[cite: 5]. [cite_start]While Large Vision-Language Models (LVLMs) show promise [cite: 6][cite_start], our research identifies two core bottlenecks[cite: 7]:
1.  [cite_start]**Positional Bias**: Models like Qwen2.5-VL exhibit a strong "recency bias," favoring the last options in a support set[cite: 8, 55, 509].
2.  [cite_start]**Insufficient Learning**: Models tend to over-rely on pre-trained knowledge rather than genuinely generalizing from the provided support samples[cite: 9, 65].

[cite_start]We propose a systematic optimization framework to address these challenges while significantly reducing inference latency[cite: 14, 72].

---

## 🚀 Core Contributions

* [cite_start]**Position-Balanced Instruction Fine-Tuning (PB-FT)**: Corrects positional bias by constructing meta-tasks where the correct answer is uniformly distributed across all candidate positions[cite: 83, 230].
* [cite_start]**Semantic-Guided Background Generation (SGBG)**: Diversifies training data by generating novel backgrounds to break spurious visual correlations[cite: 85, 240].
* [cite_start]**Hard Negative Mining Task Construction (HNMTC)**: Constructs more effective meta-tasks by mining neighboring classes to enhance discriminative power[cite: 85, 268].
* [cite_start]**Differentiated Token Pruning**: A two-stage framework that prunes support and query images with different ratios, reducing FLOPs to $19.2\%$ while maintaining performance[cite: 81, 96, 97, 494].

---

## 📊 Experimental Results (5-way 1-shot)
[cite_start]Our methods achieve superior performance across multiple FSC benchmarks[cite: 15, 86, 348]:

### General Benchmarks
| Method | [cite_start]MiniImageNet [cite: 304] | [cite_start]CIFAR-FS [cite: 304] | [cite_start]TieredImageNet [cite: 304] |
| :--- | :---: | :---: | :---: |
| Qwen2.5-VL (Base) | 94.02% | 89.16% | 93.56% |
| **Ours** | **99.20%** | **97.24%** | **98.80%** |

### Fine-Grained Benchmarks
| Method | [cite_start]CUB-200 [cite: 307] | [cite_start]Stanford Dogs [cite: 307] | [cite_start]Stanford Cars [cite: 307] |
| :--- | :---: | :---: | :---: |
| Qwen2.5-VL (Base) | 96.28% | 94.02% | 97.84% |
| **Ours** | **99.16%** | **98.26%** | **99.84%** |

> [cite_start]**Efficiency**: Our pruning strategy yields a $3.43\times$ speedup compared to previous work while maintaining high accuracy[cite: 312, 372].

---

## 📅 Roadmap
- [x] [cite_start]Paper submitted to IEEE TIP[cite: 1].
- [ ] [cite_start]Release of Pre-trained LoRA weights (Upon Acceptance)[cite: 16].
- [ ] [cite_start]Open-source training and evaluation scripts (Upon Acceptance)[cite: 16].

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
