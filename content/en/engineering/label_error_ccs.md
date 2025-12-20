---
title: "Unmasking Label Errors: Why Cybersecurity Benchmarks Need Stronger Benchmarks"
date: 2024-12-02
draft: false
description: "An empirical investigation into annotation errors in cybersecurity benchmarks, revealing how noisy test labels distort model evaluation and mislead progress in threat intelligence."
featured_image: "/images/research_images/ccs_poster.png"
tags: ["cybersecurity", "data-quality", "benchmarks", "threat-intelligence", "llms", "evaluation"]
---

### 🧪 What if your benchmark is wrong and your best model only looks good because of it?
This work exposes a critical but underappreciated issue in cybersecurity research: annotation errors in benchmark datasets, particularly in evaluation (test) splits. The study shows that even modest label noise can severely distort model rankings, evaluation metrics, and research conclusions.  
By carefully curating a widely used CTI dataset and re-evaluating modern language models, this work argues for a fundamental shift toward robust, community-validated cybersecurity benchmarks.

### 📄 Work Overview <a href="https://doi.org/10.1145/3658644.3691418" target="_blank" rel="noopener">🔗</a>
**Venue**: ACM CCS 2024   
**Focus**: Data curation, benchmark reliability, Cyber Threat Intelligence (CTI) evaluation

Cyber Threat Intelligence (CTI) systems rely heavily on supervised learning for tasks such as Named Entity Recognition (NER) and Relation Detection (RD). While model robustness to training noise has received attention, errors in test labels — used to measure progress — remain largely unexamined.  
This work demonstrates that evaluation noise is not benign and must be addressed explicitly.

### 🎯 The Core Problem  
It is often assumed that benchmark datasets are: Carefully curated, Consistently annotated, and Suitable for fair model comparison. This assumption is particularly fragile in cybersecurity, where:
- Labels are domain-specific and ambiguous
- Entities and relations evolve over time
- Annotation often mixes automation and human judgment

The central claim of this work is clear:
> Noisy test labels undermine the scientific validity of cybersecurity benchmarks.

### 🧠 Dataset Curation: From LADDER to D-LADDER++  
The study revisits the LADDER dataset, a recent benchmark for CTI information extraction, and performs a systematic manual audit of both training and test splits. Types of Annotation Errors Identified:
- **Incorrect**: Clearly wrong labels
- **Ambiguous**: Multiple plausible interpretations
- **Inconsistent**: Similar instances labeled differently
- **Tagging Errors**: BIO format violations

These errors are not edge cases — they occur at non-trivial scale.

### 📊 Correction Statistics  
After curation:  
- NER:
   - 17.37% of test labels corrected
   - 11.45% of training labels corrected
- Relation Detection:
   - 12.72% of test labels corrected
   - 8.41% of training labels corrected

The resulting dataset, D-LADDER++, represents a significantly more reliable evaluation baseline.

### ⚠️ Why Test Label Noise Is Especially Dangerous  
Unlike training noise, test label errors:
- Cannot be learned around
- Directly corrupt evaluation metrics
- Invert or exaggerate model rankings

The experiments show that:  
- Models trained on clean data but tested on noisy labels suffer >40% F1 degradation
- Apparent performance gaps between models shrink or reverse once labels are corrected

This means that **model “improvements” may be artifacts of benchmark noise**.

### 🧩 Broader Implications for Cybersecurity Research  
This work reframes progress in cybersecurity ML as a data-centric problem:
- Benchmark quality is as important as model innovation
- Evaluation datasets deserve the same scrutiny as training data
- Community collaboration is essential for sustainable benchmarks

Without this, the field risks:
- Overestimating real-world readiness
- Selecting suboptimal models for deployment
- Building systems on misleading evidence

### 🛡️ Recommendations
The work advocates for:
- Multi-annotator validation instead of single-label gold standards
- Transparent reporting of annotation uncertainty
- Shared responsibility for benchmark maintenance
- Automated and human-in-the-loop validation pipelines

These practices align cybersecurity evaluation with the realities of noisy, evolving threat data.

### 🧾 Conclusion
This paper delivers a clear message:
> You cannot trust model performance if you cannot trust the benchmark.

For researchers and practitioners alike, it offers a timely reminder that robust cybersecurity starts with reliable data.