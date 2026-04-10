# [VPLS 2025] DP-Ens DurationQA: Dual-Prompt Fine-Tuning with Log-Probability Ensemble for Duration Question Answering
Team name: Softmind_AIO
This repository contains the code and resources for **Duration Question Answering (DurationQA)** in VLSP 2025 Track 8, Subtask 2.

[📄 Paper](https://aclanthology.org/2025.vlsp-1.42.pdf)

---

## 🔥 Highlights

- 🏆 **VLSP 2025**: Accepted paper in Track 8 (DurationQA)
- 🧠 **Dual-Prompt Fine-Tuning**:
  - Chain-of-Thought (CoT) for reasoning
  - Refinement for label prediction conditioned on reasoning
- 🔗 **Log-Probability Ensemble**:
  - Combines outputs from multiple prompts in a numerically stable way
  - Improves consistency across candidate duration labels
- ⏱️ **Multi-label Temporal QA**:
  - Handles multiple correct duration answers
  - Requires multi-step reasoning
- ⚡ **Efficient LLM Adaptation**:
  - Uses 4-bit quantization for memory-efficient training and inference
- 📈 **State-of-the-Art Performance**:
  - Achieves best F1 score on VLSP 2025 DurationQA benchmark


⚠️ Recommended to run all notebooks on Kaggle P100 GPU to ensure stable execution.

---

## Model

- **Pre-finetuned model:** [`thailevann/cot_refine`](https://huggingface.co/thailevann/cot_refine)  
- The model is already fine-tuned for DurationQA and can be used directly for inference.
  
---

## Dataset

- **Training and test data:** [`thailevann/durationQA_track8_vlsp2025`](https://huggingface.co/thailevann/durationQA_track8_vlsp2025)

---

## Training

- Notebook: [`training.ipynb`](training.ipynb)  
- For reference or further fine-tuning, but the pre-finetuned model can be used directly.
---

## Inference

- Notebook: [`inference.ipynb`](inference.ipynb)  
- Generates predicted labels for the test set.  
- Supports varying `w_refine` from 0 to 1.0 for ensemble weighting.  
- Saves predictions as a JSON file.
---

## Evaluation

- Notebook: [`eval.ipynb`](eval.ipynb)  
- Evaluate predictions using a TXT file formatted according to the example in the notebook (similar to `results.txt` submitted to AIHub).  
- Computes: **Precision, Recall, F1, Exact Match**.
---
⭐ **Star this repo if you find it helpful!** ⭐ 

## Notes

- Recommended execution order: **Inference → Evaluation** if using the pre-finetuned model.  
