# Build LLM From Scratch Lab

> A notebook-first educational lab for understanding transformer language models from the inside out.

## Overview

This repository is centered on one public artifact:

`notebooks/build_llm_from_scratch_lab.ipynb`

The notebook builds a small autoregressive transformer step by step, starting from tiny examples and ending with:

- a scratch implementation of tokenization, embeddings, positional information, attention, masking, MLPs, residual connections, transformer blocks, logits, and next-token prediction
- a toy-data training run on small synthetic text
- a lightweight Project Gutenberg training run on a cleaned subset of *Alice's Adventures in Wonderland*
- a GPT-2 Small comparison that connects the educational build to a real pretrained model

The emphasis is understanding, inspection, and clear narrative flow rather than framework complexity or benchmark performance.

## Notebook Arc

The notebook is organized as a single story:

1. framing and roadmap
2. text to tokens
3. tokens to embeddings
4. positional information
5. single-head self-attention
6. multi-head attention
7. MLPs, residual connections, and transformer blocks
8. logits and next-token prediction
9. tiny autoregressive generation
10. Stage A training on synthetic text
11. Stage B training on a small Project Gutenberg subset
12. GPT-2 Small comparison
13. final synthesis

Each major output is followed by a short interpretation block with:

- What to notice
- What this step contributes
- Why it matters

## Running The Lab

### In Google Colab

Open the notebook and run it top to bottom. The setup cell installs only missing packages, and the rest of the notebook is self-contained.

### Locally

Use a standard Jupyter workflow. A simple local install looks like:

```bash
uv pip install torch matplotlib requests transformers notebook
```

Then launch Jupyter and open:

`notebooks/build_llm_from_scratch_lab.ipynb`

The notebook is designed for CPU or a basic Colab session. The training runs are intentionally small so they stay practical to inspect.

## Design Choices

- The notebook begins with a tiny regex-based word tokenizer for intuition.
- The trainable scratch model switches to character-level tokenization to keep the vocabulary small and the training loops easy to inspect.
- The early embedding examples use intentionally tiny vector widths so the mechanics stay readable on the page before the notebook connects them to real model scales such as GPT-2 Small.
- The Stage A corpus uses repeated factual and grammar-like patterns so the model's improvements are easy to interpret.
- The Stage B corpus uses a small cleaned slice of Project Gutenberg text to bridge the gap between toy data and real language.
- GPT-2 Small appears at the end as a bridge from the educational build to a real pretrained transformer, not as a replacement for the scratch model.

## Repository Layout

```text
build_llm_from_scratch_lab/
├── README.md
└── notebooks/
    └── build_llm_from_scratch_lab.ipynb
```
