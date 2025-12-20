---
title: "Reducing Communication Overhead in Federated Learning with Parameter-Efficient Finetuning"
date: 2023-11-20
draft: false
description: "An empirical study showing how parameter-efficient finetuning enables scalable, privacy-preserving federated learning for large language models with drastically reduced communication costs."
featured_image: "/images/research_images/fl_overhead.png"
tags: ["federated-learning", "nlp", "parameter-efficient-tuning", "privacy", "distributed-ml", "transfer-learning"]
---

### 📉 Federated learning promises privacy but large models make it impractical.  
This work tackles one of the biggest barriers to deploying pre-trained language models (PLMs) in federated learning (FL): communication overhead. By systematically evaluating parameter-efficient finetuning (PEFT) methods, the work shows that it is possible to reduce communication costs by orders of magnitude without sacrificing model performance.  
The result is a **practical pathway** for building privacy-preserving NLP systems on real-world, distributed data.

### 📄 Work Overview <a href="https://proceedings.mlr.press/v232/malaviya23a.html" target="_blank" rel="noopener">🔗</a>
**Venue**: Conference on Lifelong Learning Agents (CoLLAs), 2023  
**Focus**: Federated learning, communication efficiency, NLP

The work investigates a core tension in modern NLP systems:
- PLMs are powerful, but massive
- Federated learning is private, but communication-heavy

Bringing the two together requires rethinking what is actually shared during training.

### 🎯 The Core Challenge  
Standard federated learning requires each client to send: full model updates, every training round.  
For PLMs like BERT, this results in:
- Hundreds of megabytes per round
- Prohibitive bandwidth and latency costs
- Infeasibility on edge or enterprise devices

At the same time:
- Client-side labeled data is often unavailable
- Data is non-IID and unevenly distributed
- Privacy regulations restrict centralized training

The question becomes:
> Can we federate language models without federating the entire model?

### 💡 Key Insight: Update Less, Learn Enough  
The central idea explored in this work is simple but powerful:
- Only finetune and communicate a small subset of parameters; freeze everything else.

This is achieved using **parameter-efficient finetuning (PEFT)** methods that:
- Modify only specific components of the PLM
- Keep the backbone frozen
- Reduce both communication and computation costs

### 🧠 PEFT Methods Evaluated  
The study evaluates four major PEFT families, covering different design methods:
- **Prefix Tuning** – learnable prompts prepended to attention layers
- **Adapter Tuning** – lightweight bottleneck layers inserted into transformers
- **BitFit** – updating only bias parameters
- **LoRA** – low-rank reparameterization of attention weights

Each method updates <10% and sometimes <1% of model parameters.

### 📉 Communication Cost: The Real Win  
The most striking result is the reduction in communication overhead:

- Full model finetuning: ~420 MB per round
- PEFT methods:
   - Prefix: ~38 MB
   - Adapter: ~4 MB
   - BitFit: ~1 MB
   - LoRA: <1 MB

This reduction fundamentally changes what is deployable in practice.
> Communication, not accuracy, is often the true bottleneck in federated NLP.

### 🔄 Task-Level Transferability in Federated Learning  
Beyond efficiency, the paper explores task-level transferability:
- Train PEFT parameters on one task, transfer them zero-shot to related tasks

Findings:
- Strong transfer within task families (e.g., NLI → NLI)
- Weaker but non-trivial transfer across tasks
- Transferability in federated settings is often better than centralized training

This suggests PEFT parameters encode **compact, reusable task knowledge** even under distributed, noisy conditions.

### 🧩 Conclusion  
This work delivers a clear and actionable message:
> Federated learning with language models is only viable if we stop sharing the whole model.

By demonstrating that parameter-efficient finetuning drastically reduces communication overhead while remaining robust, transferable, and accurate, this paper bridges the gap between federated learning theory and deployable NLP systems.  
It shows that efficiency is not an optimization detail, but a prerequisite for real-world privacy-preserving AI.