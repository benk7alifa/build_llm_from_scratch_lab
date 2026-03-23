# Build LLM From Scratch Lab

> A self-contained, Colab-friendly educational lab for understanding how transformer-based language models work from the inside out.

---

## 1. Project Goal

This repository is a serious educational lab focused on one objective:

**understand how a transformer-based language model works by building the mechanics step by step, training a tiny model, and then connecting that understanding to GPT-2 Small.**

The goal is not to build the biggest model or the most optimized training stack. The goal is to understand the core ideas clearly and concretely.

By the end of this lab, the reader should understand:

- how text becomes tokens
- how tokens become embeddings
- how positional information is added
- how self-attention mixes information across tokens
- how masking enforces autoregressive prediction
- how MLP blocks refine representations
- how residual connections accumulate updates
- how transformer blocks compose into a language model
- how logits become next-token probabilities
- how a tiny model can be trained for educational purposes
- how that understanding connects to GPT-2 Small

---

## 2. Philosophy

This lab is built around a simple standard:

**If we cannot build it, inspect it, and explain it clearly, then we do not understand it deeply enough.**

That means this repository prioritizes:

- conceptual clarity
- step-by-step explanation
- tiny concrete examples before abstraction
- readable code
- interpretable outputs
- notebook-first learning
- Colab-friendliness
- clean public presentation

It deliberately avoids:

- unnecessary framework complexity
- configuration sprawl
- boilerplate-heavy project structure
- vague explanations
- hidden workflow clutter

---

## 3. Main Deliverable

The main artifact in this repository is the notebook:

`notebooks/build_llm_from_scratch_lab.ipynb`

The notebook is intended to be:

- self-contained
- educational
- readable
- polished
- easy to inspect
- GitHub-friendly
- runnable in Google Colab with minimal friction

This repo is intentionally minimal so the notebook stays the clear center of gravity.

---

## 4. What the Notebook Covers

The notebook is designed to build understanding progressively.

It explicitly implements and explains:

- tokenization
- embeddings
- positional information
- self-attention
- masking
- MLP
- residual connections
- transformer blocks
- logits
- next-token prediction

Then it extends that understanding into:
- a tiny educational training run
- a small Project Gutenberg training example
- a GPT-2 Small comparison

---

## 5. Data Strategy

This lab uses a staged data strategy so that learning remains interpretable and training remains lightweight.

### Stage A. Tiny Synthetic / Toy Text

The notebook starts with very small hand-made or lightly generated text.

Examples include:
- simple grammar sequences
- repeated sentence patterns
- tiny stories
- arithmetic-like token patterns
- structured templates such as `"The capital of France is Paris"`

Why this comes first:
- we can see exactly what the model is supposed to learn
- training is fast
- outputs are interpretable
- tokenization, logits, and attention can be inspected without much noise

This is the best starting point for understanding the mechanics.

### Stage B. Tiny Real Corpus for Educational Pretraining

After toy data, the notebook moves to a small real-world corpus that remains Colab-friendly.

Primary choice:
- Project Gutenberg

A very small and carefully selected subset is preferred so the project stays lightweight, reproducible, and easy to reason about.

The goal is not benchmark performance. The goal is to see how the same language-modeling machinery behaves on more natural text.

---

## 6. Recommended Learning Arc

The notebook is expected to follow a sequence close to this:

1. Framing and roadmap  
2. Text to tokens  
3. Tokens to embeddings  
4. Positional information  
5. Single-head self-attention  
6. Multi-head attention  
7. MLP and residual stream  
8. Transformer block composition  
9. Logits and next-token prediction  
10. Tiny autoregressive generation demo  
11. Educational training on toy data  
12. Educational training on a small Project Gutenberg subset  
13. GPT-2 Small comparison  
14. Final synthesis

---

## 7. Why GPT-2 Small Appears in This Lab

After building the mechanics from scratch and training a tiny educational model, the notebook loads GPT-2 Small to connect those ideas to a real pretrained transformer.

This helps answer:
- what is conceptually the same
- what was simplified in the educational build
- how scale and pretraining change behavior

GPT-2 Small is not the starting point of the lab. It is the comparison point that helps bridge first-principles understanding and real pretrained models.

---

## 8. Environment Notes

This project is designed to be friendly to:

- Google Colab
- local notebook execution
- VS Code notebook workflows

The notebook should keep dependency setup simple and practical.

For local environments, `uv pip install ...` is preferred.

In Colab, simple in-notebook install cells are acceptable when needed.

The focus of this repo is learning, not environment engineering.

---

## 9. Repository Structure

The repository intentionally stays minimal:

```text
build_llm_from_scratch_lab/
├── .gitignore
├── README.md
└── notebooks/
    └── build_llm_from_scratch_lab.ipynb