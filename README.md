# TOPSIS Analysis for Text Generation Models

## Overview

This project applies **TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution)** to evaluate and rank modern **text generation models** based on both generation quality and deployment efficiency.

Unlike traditional evaluations focused only on quality, this analysis balances:

- generation performance  
- response latency  
- resource efficiency  

making it suitable for **real-time AI systems and production deployment**.

---

## Objective

To identify the most suitable text generation model for real-world applications by evaluating multiple performance criteria.

---

## Models Evaluated

The following widely used generation models were evaluated:

1. GPT-2  
2. GPT-Neo-1.3B  
3. T5-base  
4. BART-large  
5. LLaMA-2-7B  
6. Mistral-7B  

---

## Evaluation Criteria

Models were evaluated using both quality and efficiency metrics.

| Criterion | Type | Weight | Description |
|----------|------|--------|-------------|
| **BLEU Score** | Benefit ↑ | 25% | Measures fluency & n-gram similarity |
| **ROUGE-L** | Benefit ↑ | 20% | Measures content relevance |
| **BERTScore** | Benefit ↑ | 20% | Captures semantic coherence |
| **Latency (ms)** | Cost ↓ | 15% | Response speed |
| **VRAM Usage (GB)** | Cost ↓ | 10% | GPU memory required |
| **Model Size (MB)** | Cost ↓ | 10% | Storage footprint |

> **Benefit criteria (↑):** higher is better  
> **Cost criteria (↓):** lower is better  

---

## TOPSIS Results

### Final Ranking

| Rank | Model | TOPSIS Score | Key Insights |
|------|-------|--------------|-------------|
| 🥇 1 | **BART-large** | **0.7199** | Best balance of quality & efficiency |
| 🥈 2 | **T5-base** | 0.6657 | Strong generation quality with good efficiency |
| 🥉 3 | **GPT-Neo-1.3B** | 0.5805 | Balanced performance |
| 4 | GPT-2 | 0.4970 | Lightweight and stable baseline |
| 5 | LLaMA-2-7B | 0.3665 | High resource usage impacts ranking |
| 6 | Mistral-7B | 0.3073 | Resource-heavy for this setup |

---

### Visualization: Final Ranking

![Final Ranking](results/final_ranking_generation.png)

---

## Interpretation of Results

### 🥇 Why BART-large Ranked First
- Highest combined generation quality
- Strong semantic coherence
- Balanced latency and resource usage

### 🥈 Why T5-base Performed Strongly
- Excellent text coherence & summarization ability
- Efficient compared to larger models

### ⚖️ Mid-Tier Models
- GPT-Neo provides balance
- GPT-2 remains a reliable lightweight baseline

### 📉 Why Larger Models Ranked Lower
LLaMA-2 and Mistral require significantly more compute resources, reducing suitability for latency-sensitive deployment.

---

## Recommendation

## ✅ Recommended Model: **BART-large**

Best suited for:

- conversational AI  
- content generation  
- summarization systems  
- real-time AI applications  

Provides the best balance of quality and efficiency.

### Alternative Recommendations

✔ **T5-base** → best efficiency + quality trade-off  
✔ **GPT-Neo** → balanced performance  
✔ **GPT-2** → resource-constrained environments  

---

## TOPSIS Methodology

TOPSIS ranks alternatives based on distance from:

- **Ideal Best (A⁺)** → optimal values  
- **Ideal Worst (A⁻)** → least desirable values  

### Steps:

1. Normalize decision matrix  
2. Apply weights  
3. Identify ideal best & worst  
4. Compute distances (S⁺ and S⁻)  
5. Calculate TOPSIS score  
6. Rank alternatives  

**Score formula:**

Score = S⁻ / (S⁺ + S⁻)

Higher score indicates better overall performance.

---

## Usage

### Run Analysis

```bash
python text_generation_topsis.py
```

### Generate Visualizations

```bash
python visualizations_generation.py
```

Outputs are saved in:

```
/results
```

---

## Applications

This evaluation framework is useful for:

- conversational AI systems  
- live commerce assistants  
- content generation platforms  
- chatbot deployment decisions  
- AI model benchmarking  

---

## Author

**Ojas Jindal**
