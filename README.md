# Cavrix Code (Experiment 5 — Q8_0)

**Cavrix Code** is an ultra-lightweight, high-efficiency bilingual coding assistant fine-tuned specifically for **Python** and **JavaScript** execution on resource-constrained consumer hardware. Based on the `Qwen2.5-0.5B-Instruct` architecture (494M parameters), Cavrix Code is engineered to run locally in pure CPU environments with a memory working set under 700 MB.

---

## Model Specifications

| Parameter | Value |
| :--- | :--- |
| **Model Name** | Cavrix Code (Experiment 5) |
| **Base Model** | [Qwen/Qwen2.5-0.5B-Instruct](https://huggingface.co/Qwen/Qwen2.5-0.5B-Instruct) |
| **Total Parameters** | 494,032,768 (~0.494B) |
| **Non-Embedding Parameters** | 357,898,112 (~0.358B) |
| **Fine-Tuning Method** | Parameter-Efficient LoRA ($r=8, \alpha=16$ on $W_q, W_v$) |
| **Quantization Format** | GGUF `Q8_0` (8-bit quantization) |
| **Artifact Filename** | `cavrix_code_exp5_q8_0.gguf` |
| **Exact File Size** | 531,068,000 bytes (506.47 MiB) |
| **SHA-256 Checksum** | `4a9f433d4ef7cacf4fe41c4df66fb902138dcc1cfc43510ae8575a17e62db4b1` |
| **License** | [Apache License 2.0](LICENSE) |

---

## Key Features & Capabilities

- **Bilingual Dual-Stack Expertise:** Purpose-built for Python and JavaScript utility functions, algorithmic problem solving, array manipulations, data transformations, and asynchronous patterns.
- **Flawless Syntax Discipline:** Demonstrates 100% syntax validity across all 110 evaluation benchmark tasks, adhering strictly to markdown code fences without conversational chatter.
- **Ultra-Low Memory Footprint:** Consumes ~650 MB of RAM during active local inference, allowing it to run smoothly on machines with as little as 2 GB to 4 GB total system RAM.
- **Rapid CPU Inference:** Sustains 21–23 tokens/second on standard laptop/desktop CPUs (e.g., AMD Ryzen 5 / Intel Core i5) without requiring discrete GPU acceleration.

---

## Verified Benchmark Results

All evaluations were conducted under standardized conditions (temperature 0.0, max predict 512, 60s timeout, isolated AST and subprocess assertion runners):

### 1. 50-Problem Frozen Benchmark (`benchmark_50`)
Measures core algorithmic correctness, data structures, and bilingual competence:
- **Cavrix Code (Exp 5 Q8_0):** **26 / 50 (52.0% Pass@1)**
  - Python: 20 / 40 (50.0%)
  - JavaScript: 6 / 10 (60.0%)
- **Cavrix Code (Exp 4 Q8_0):** 24 / 50 (48.0% Pass@1)
- **Base Model (`qwen2.5:0.5b`):** 19 / 50 (38.0% Pass@1)

### 2. 40-Problem Quarantined Validation Set
Held-out unseen coding problems measuring generalization:
- **Cavrix Code (Exp 5 Q8_0):** **25 / 40 (62.5% Pass@1)**
  - Python: 15 / 24 (62.5%)
  - JavaScript: 10 / 16 (62.5%)
- **Cavrix Code (Exp 4 Q8_0):** 22 / 40 (55.0% Pass@1)
- **Base Model (`qwen2.5:0.5b`):** 25 / 40 (62.5% Pass@1)

### 3. 20-Problem Fresh Unseen Evaluation Suite
Brand-new, non-overlapping tasks testing prompt stability and zero-shot reasoning:
- **Cavrix Code (Exp 5 Q8_0):** **14 / 20 (70.0% Pass@1)**
  - Python: 10 / 12 (83.3%)
  - JavaScript: 4 / 8 (50.0%)
- **Base Model (`qwen2.5:0.5b`):** 10 / 20 (50.0% Pass@1)

### Combined 110-Task Evaluation Summary
| Model | Overall Pass@1 | Python Pass@1 | JavaScript Pass@1 | Syntax Validity | Avg Latency | Throughput |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Base (`qwen2.5:0.5b`)** | 54 / 110 (49.1%) | 38 / 76 (50.0%) | 16 / 34 (47.1%) | 97.3% | ~10.5s | 16–20 tok/s |
| **Cavrix Code Exp 4** | 61 / 110 (55.5%) | 42 / 76 (55.3%) | 19 / 34 (55.9%) | 100.0% | ~4.9s | 15–22 tok/s |
| **Cavrix Code Exp 5 (Latest)** | **65 / 110 (59.1%)** | **45 / 76 (59.2%)** | **20 / 34 (58.8%)** | **100.0%** | **~3.6s** | **21–23 tok/s** |

---

## Installation & Deployment via Ollama

### Prerequisites
- [Git](https://git-scm.com/) and [Git LFS](https://git-lfs.com/) installed
- [Ollama](https://ollama.com/) (version 0.1.30 or newer)

### Step 1: Clone the Repository with Git LFS
```bash
git lfs install
git clone https://github.com/FaaizJohar/CavrixCode-latest.git
cd CavrixCode-latest
git lfs pull
```

### Step 2: Verify Model Checksum
```bash
# On Linux / macOS:
sha256sum cavrix_code_exp5_q8_0.gguf

# On Windows (PowerShell):
Get-FileHash -Algorithm SHA256 .\cavrix_code_exp5_q8_0.gguf
```
Expected output:
`4a9f433d4ef7cacf4fe41c4df66fb902138dcc1cfc43510ae8575a17e62db4b1`

### Step 3: Register the Model in Ollama
Use the provided `Modelfile`:
```bash
ollama create cavrix-code -f Modelfile
```

### Step 4: Run the Model
```bash
ollama run cavrix-code
```

### Example Usage
```text
>>> Write a Python function to merge overlapping intervals.
```
```python
from typing import List

def merge_intervals(intervals: List[List[int]]) -> List[List[int]]:
    if not intervals:
        return []
    intervals.sort(key=lambda x: x[0])
    merged = [intervals[0]]
    for current in intervals[1:]:
        prev = merged[-1]
        if current[0] <= prev[1]:
            prev[1] = max(prev[1], current[1])
        else:
            merged.append(current)
    return merged
```

---

## Hardware Requirements

- **Processor:** Any modern x86_64 or ARM64 CPU (2 or more cores recommended).
- **RAM:** Minimum 2 GB host RAM; model working set requires ~650 MB.
- **Storage:** ~600 MB of free disk space for the GGUF weights.
- **GPU:** Optional. Discrete GPU acceleration is **not required**.

---

## Provenance & Attribution

- **Base Model Architecture:** `Qwen2.5-0.5B-Instruct`, developed by the Alibaba Cloud Qwen Team under the Apache License 2.0.
- **Fine-Tuning & Quantization:** Designed, fine-tuned, and evaluated by Faaiz Johar using targeted bilingual instruction-tuning and 8-bit GGUF quantization.
- **License:** Licensed under the [Apache License, Version 2.0](LICENSE). You may freely use, modify, and distribute this model in accordance with the license terms.
