# Cavrix Code (Experiment 5 — Q8_0)

**Cavrix Code** is an independent, ultra-lightweight bilingual AI coding assistant developed within the **Cavrix Core** technology ecosystem ([https://cavrixcore.com](https://cavrixcore.com)). Engineered specifically for **Python** and **JavaScript** developers, Cavrix Code runs locally through Ollama with an active RAM working set of ~650 MB and zero cloud dependencies.

---

## Model Specifications

| Property | Value |
| :--- | :--- |
| **Model Name** | Cavrix Code (Experiment 5) |
| **Organization** | [Cavrix Core](https://cavrixcore.com) |
| **Category** | Local AI Coding Assistant |
| **Specialization** | Python & JavaScript Code Generation, Debugging, Explanation |
| **Total Parameters** | 494,032,768 (~0.494B) |
| **Non-Embedding Parameters** | 357,898,112 (~0.358B) |
| **Fine-Tuning Architecture** | Low-Rank Adaptation (LoRA $r=8, \alpha=16$ on $W_q, W_v$) |
| **Upstream Base Architecture** | `Qwen2.5-0.5B-Instruct` (Apache License 2.0) |
| **Quantization Format** | GGUF `Q8_0` (8-bit quantization) |
| **Model Artifact** | `cavrix_code_exp5_q8_0.gguf` |
| **Exact Size** | 531,068,000 bytes (506.47 MiB) |
| **SHA-256 Checksum** | `4a9f433d4ef7cacf4fe41c4df66fb902138dcc1cfc43510ae8575a17e62db4b1` |
| **License** | [Apache License 2.0](LICENSE) |

---

## Cavrix Core Ecosystem

Cavrix Code is a developer tooling project developed within the **Cavrix Core** technology ecosystem:
- **Organization:** Cavrix Core ([https://cavrixcore.com](https://cavrixcore.com))
- **Mission & Tagline:** *"Building technology for what comes next."*
- **Founders:** Faaiz Johar and Mohd Fahad (also known as Fahad Multani).
- **Core Technology Ecosystem:**
  - **Cavrix Cloud:** Cloud infrastructure and high-performance hosting solutions ([cavrix.cloud](https://cavrix.cloud/)).
  - **SpawnX:** Developer and builder community platform ([spawnx.cavrixcore.com](https://spawnx.cavrixcore.com/)).
  - **Rootix:** Interactive gaming studio (creators of *RiftShot*, a browser-based FPS).
  - **Quill Labs:** Education technology studio (creators of *Padhle*).
  - **AyushUnitech:** Health and AYUSH technology platform.
  - **Cavrix Code:** Ultra-lightweight local AI coding model engineered to turn ideas into working code.

---

## Key Capabilities & Features

- **Dual-Stack Programming Focus:** Specialized for Python and JavaScript utility functions, algorithms, asynchronous event loops, data transformation, and object manipulation.
- **Flawless Syntax Discipline:** Reached **100% syntax validity** (110/110 tasks) across frozen benchmark, quarantined validation, and fresh unseen test suites with clean markdown code formatting.
- **Minimal Local Footprint:** Operates in ~650 MB of RAM during active CPU inference, ensuring smooth execution on systems with as little as 2 GB to 4 GB total host memory.
- **High CPU Throughput:** Delivers 21–23 tokens per second on standard multi-core laptop and desktop CPUs (e.g., AMD Ryzen, Intel Core) without requiring discrete GPU acceleration.
- **Honest Knowledge Boundaries:** When asked about unverified company details or facts outside its training scope, Cavrix Code acknowledges missing information rather than hallucinating.

---

## Verified Benchmark Results

Evaluated across **110 non-training coding tasks** under standardized evaluation conditions (temperature 0.0, max predict 512, 60s timeout, isolated AST and subprocess assertion harnesses):

### 1. 50-Problem Frozen Benchmark (`benchmark_50`)
Measures core algorithmic correctness, data structures, and bilingual competence:
- **Cavrix Code Exp 5 (Latest):** **26 / 50 (52.0% Pass@1)**
  - Python: 20 / 40 (50.0%)
  - JavaScript: 6 / 10 (60.0%)
- **Cavrix Code Exp 4:** 24 / 50 (48.0% Pass@1)
- **Base Architecture Baseline:** 19 / 50 (38.0% Pass@1)

### 2. 40-Problem Quarantined Validation Set
Held-out unseen coding problems measuring functional generalization:
- **Cavrix Code Exp 5 (Latest):** **25 / 40 (62.5% Pass@1)**
  - Python: 15 / 24 (62.5%)
  - JavaScript: 10 / 16 (62.5%)
- **Cavrix Code Exp 4:** 22 / 40 (55.0% Pass@1)
- **Base Architecture Baseline:** 25 / 40 (62.5% Pass@1)

### 3. 20-Problem Fresh Unseen Evaluation Suite
Non-overlapping tasks testing prompt stability and zero-shot reasoning:
- **Cavrix Code Exp 5 (Latest):** **14 / 20 (70.0% Pass@1)**
  - Python: 10 / 12 (83.3%)
  - JavaScript: 4 / 8 (50.0%)
- **Base Architecture Baseline:** 10 / 20 (50.0% Pass@1)

### Combined 110-Task Evaluation Summary
| Model Configuration | Overall Pass@1 | Python Pass@1 | JavaScript Pass@1 | Syntax Validity | Avg Latency | Throughput |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Base Architecture Baseline** | 54 / 110 (49.1%) | 38 / 76 (50.0%) | 16 / 34 (47.1%) | 97.3% | ~10.5s | 16–20 tok/s |
| **Cavrix Code Exp 4** | 61 / 110 (55.5%) | 42 / 76 (55.3%) | 19 / 34 (55.9%) | 100.0% | ~4.9s | 15–22 tok/s |
| **Cavrix Code Exp 5 (Latest)** | **65 / 110 (59.1%)** | **45 / 76 (59.2%)** | **20 / 34 (58.8%)** | **100.0%** | **~3.6s** | **21–23 tok/s** |

---

## Installation & Running via Ollama

### Prerequisites
- [Git](https://git-scm.com/) and [Git LFS](https://git-lfs.com/)
- [Ollama](https://ollama.com/)

### Step 1: Clone Repository with Git LFS
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

### Step 3: Register Model in Ollama
```bash
ollama create cavrix-code -f Modelfile
```

### Step 4: Run the Model
```bash
ollama run cavrix-code
```

### Example Usage
```text
>>> Tell me about yourself.
I am Cavrix Code, an AI coding assistant developed within the Cavrix Core technology ecosystem.
I specialize in Python and JavaScript, and I can assist with algorithmic problems, utility functions,
debugging, code explanation, and implementation reviews.

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

- **Processor:** 64-bit multi-core CPU (x86_64 or ARM64).
- **RAM:** Minimum 2 GB host RAM (active model working set is ~650 MB).
- **Storage:** ~600 MB free space for the model file.
- **GPU:** Not required (runs efficiently on CPU).

---

## Provenance & Attribution

- **Base Architecture:** Fine-tuned on the `Qwen2.5-0.5B-Instruct` base model architecture created by the Alibaba Cloud Qwen Team.
- **Cavrix Code Training & Quantization:** Designed, fine-tuned, and evaluated by Faaiz Johar within the Cavrix Core ecosystem using targeted bilingual instruction tuning and 8-bit GGUF quantization.
- **License:** Distributed under the [Apache License, Version 2.0](LICENSE). You may freely use, modify, and distribute this model in accordance with the terms of the Apache 2.0 license.
