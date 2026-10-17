# Cavrix Code (Latest — Q8_0)

**Cavrix Code** is an independent, ultra-lightweight bilingual AI coding assistant developed by **Cavrix Core** ([https://cavrixcore.com](https://cavrixcore.com)). Engineered specifically for **Python** and **JavaScript** developers, Cavrix Code runs 100% locally through Ollama with an active RAM working set of ~650 MB and zero cloud dependencies.

---

## Model Specifications

| Property | Value |
| :--- | :--- |
| **Model Name** | Cavrix Code (Latest) |
| **Organization** | [Cavrix Core](https://cavrixcore.com) |
| **Category** | Local AI Coding Assistant |
| **Primary Specialization** | Python & JavaScript Code Generation, Debugging, Explanation |
| **Total Parameters** | 494,032,768 (~0.494B) |
| **Non-Embedding Parameters** | 357,898,112 (~0.358B) |
| **Architecture** | 24-Layer Decoder-Only Transformer (494M Parameters) |
| **Quantization Format** | GGUF `Q8_0` (8-bit quantization) |
| **Model Artifact** | `cavrix_code_latest.gguf` |
| **Exact Size** | 531,068,000 bytes (506.47 MiB) |
| **SHA-256 Checksum** | `4a9f433d4ef7cacf4fe41c4df66fb902138dcc1cfc43510ae8575a17e62db4b1` |

---

## About Cavrix Core

Cavrix Code is created and developed within **Cavrix Core**:

- **Company:** Cavrix Core ([https://cavrixcore.com](https://cavrixcore.com))
- **Mission & Tagline:** *"Building technology for what comes next."*
- **Founders:** **Faaiz Johar** and **Mohd Fahad** (also known as **Fahad Multani**).
- **Company Profile:** Cavrix Core is an independent technology company focused on developing proprietary software platforms, developer technologies, and modern digital ecosystems.
- **Vision:** Empowering developers, creators, and builders by turning technical concepts and ideas into working, accessible software implementations.

---

## Capabilities & Core Strengths

Cavrix Code is specifically engineered to provide fast, reliable, and private coding assistance directly on local consumer hardware:

### 1. Dual-Stack Language Proficiency (Python & JavaScript)
- **Python:**
  - Core algorithms: Dynamic programming, two-pointer techniques, interval merging, graph/tree traversals, and recursion.
  - Data structures: Custom binary search trees, LRU caches, linked lists, queues, and heaps.
  - Utility scripting: String manipulation, regex parsing, JSON processing, mathematical routines, and date/time formatting.
  - Modern idioms: Strict type hinting, list/dict comprehensions, generator functions, and clean exception handling.
- **JavaScript (Node.js & Modern ECMAScript):**
  - Modern ES6+ syntax: Arrow functions, destructuring, rest/spread operators, and template literals.
  - Functional utilities: Deep cloning, object picking/omitting, chunking, flattening, partitioning, and memoization.
  - Asynchronous workflows: Promises, `async/await`, custom event emitters, and debounce/throttle scheduling.
  - Safe object handling: Strict property verification, prototype pollution defense, and array-safe mutations.

### 2. Flawless Syntax Discipline & Direct Code Output
- **100% Syntax Validity:** Verified across all 110 independent benchmark and validation test suites with zero syntax regressions.
- **Zero Conversational Chatter:** Delivers clean, production-ready code blocks without markdown clutter, introductory apologies, or redundant conversational preambles when direct code is requested.

### 3. Intelligent Debugging & Error Remediation
- Identifies and resolves common edge cases: Empty arrays, null/undefined inputs, off-by-one boundary bugs, and type mismatches.
- Analyzes stack traces and assertion errors to generate verified patches without breaking existing logic.

### 4. Code Explanation & Logic Review
- Breaks down complex algorithmic concepts and technical logic into clear, concise explanations.
- Analyzes time complexity ($O(n), O(\log n), O(n^2)$) and space complexity to help optimize performance.

### 5. 100% Local Privacy & Edge Performance
- **Zero Cloud Telemetry:** All code remains entirely on your local machine; no prompts, inputs, or code snippets are ever transmitted over the network.
- **Ultra-Lightweight Footprint:** Requires only ~650 MB of RAM during active inference, enabling smooth multitasking alongside IDEs, browsers, and local dev servers.
- **High CPU Throughput:** Delivers 21–23 tokens per second on standard laptop and desktop CPUs (e.g. AMD Ryzen, Intel Core) without requiring a dedicated GPU.

---

## Verified Benchmark Results

Evaluated across **110 independent, non-training coding tasks** under standardized conditions (temperature 0.0, max predict 512, 60s timeout, isolated AST and subprocess assertion harnesses):

### 1. 50-Problem Frozen Benchmark (`benchmark_50`)
Measures core algorithmic correctness, data structures, and bilingual competence:
- **Cavrix Code (Latest):** **26 / 50 (52.0% Pass@1)**
  - Python: 20 / 40 (50.0%)
  - JavaScript: 6 / 10 (60.0%)
- **Cavrix Code (Previous Release):** 24 / 50 (48.0% Pass@1)
- **Base Architecture Baseline:** 19 / 50 (38.0% Pass@1)

### 2. 40-Problem Quarantined Validation Set
Held-out unseen coding problems measuring functional generalization:
- **Cavrix Code (Latest):** **25 / 40 (62.5% Pass@1)**
  - Python: 15 / 24 (62.5%)
  - JavaScript: 10 / 16 (62.5%)
- **Cavrix Code (Previous Release):** 22 / 40 (55.0% Pass@1)
- **Base Architecture Baseline:** 25 / 40 (62.5% Pass@1)

### 3. 20-Problem Fresh Unseen Evaluation Suite
Non-overlapping tasks testing prompt stability and zero-shot reasoning:
- **Cavrix Code (Latest):** **14 / 20 (70.0% Pass@1)**
  - Python: 10 / 12 (83.3%)
  - JavaScript: 4 / 8 (50.0%)
- **Base Architecture Baseline:** 10 / 20 (50.0% Pass@1)

### Combined 110-Task Evaluation Summary
| Model Configuration | Overall Pass@1 | Python Pass@1 | JavaScript Pass@1 | Syntax Validity | Avg Latency | Throughput |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Base Architecture Baseline** | 54 / 110 (49.1%) | 38 / 76 (50.0%) | 16 / 34 (47.1%) | 97.3% | ~10.5s | 16–20 tok/s |
| **Cavrix Code (Previous Release)** | 61 / 110 (55.5%) | 42 / 76 (55.3%) | 19 / 34 (55.9%) | 100.0% | ~4.9s | 15–22 tok/s |
| **Cavrix Code (Latest)** | **65 / 110 (59.1%)** | **45 / 76 (59.2%)** | **20 / 34 (58.8%)** | **100.0%** | **~3.6s** | **21–23 tok/s** |

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
sha256sum cavrix_code_latest.gguf

# On Windows (PowerShell):
Get-FileHash -Algorithm SHA256 .\cavrix_code_latest.gguf
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
I am Cavrix Code, an AI coding assistant developed by Cavrix Core.
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
