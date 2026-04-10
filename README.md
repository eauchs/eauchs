# Théophile Lafargue

I build local AI infrastructure on Apple Silicon.
Open-source contributor to llama.cpp, Unsloth, and StepFun.
Patent holder. Student-Entrepreneur at Paris-Saclay (Pépite PEIPS).

## Projects

| Project | What it does |
|---------|-------------|
| [LACE](https://github.com/eauchs/lace) | Semantic compression under LoRa/SMS constraints. 47 concepts emerge from 198 tasks. Negative result on retrieval/inference separation — clean and honest. arXiv pending. |
| [mythos](https://github.com/eauchs/mythos) | Behavioral distillation of Anthropic's Mythos into Gemma 4 26B via LoRA. 551 pairs, val loss 1.398, 7/7 out-of-distribution questions without system prompt. |
| Phantom | Personal AI OS — Two-Tower behavioral recommender + RLHF loop. MLX on-device, M3 Max. |
| VoxTape | Local voice-to-text for macOS — MLX Whisper on Metal GPU. Open-source SuperWhisper alternative. |
| [llama.cpp #20075](https://github.com/ggml-org/llama.cpp/pull/20075) | Fix speculative decoding on hybrid SSM/MoE models. +45% inference on M3 Max. Cited as prior work in #20428 and #20649. |
| [unslothai/unsloth #4901](https://github.com/unslothai/unsloth/pull/4901) | Fix RoPE offset cast for Gemma 4 on Apple Silicon. Merged by danielhanchen. |
| StepFun Cookbook #14 | Local deployment of Step-3.5-flash on Apple Silicon. Merged. |
| patent-low-bandwidth-ai | Hybrid RAG pipeline for AI over 2G/SMS — backend for patent FR2511116. |
| benchmark-422-qec | 11 LLMs vs. one quantum error correction problem. 0/11 correct. |

## HuggingFace

| Dataset | Description |
|---------|-------------|
| [ox-ox/lace-semantic-compression](https://huggingface.co/datasets/ox-ox/lace-semantic-compression) | 198 operational tasks, LoRa/SMS constraints, VQ codebook |
| [ox-ox/mythos-character-distillation](https://huggingface.co/datasets/ox-ox/mythos-character-distillation) | 551 behavioral pairs for Mythos-style distillation |

## Stack

**Inference** — llama.cpp · MLX · Metal · GGUF  
**AI/ML** — LoRA · Transformers · VQ-VAE · Whisper · RAG  
**Languages** — Python · C++ · TypeScript  
**Infra** — Docker · Tailscale · Bare-metal homelab

## Patent

FR2511116 — Hybrid State-Preserving Gateway for LLM over 2G/SMS

[LinkedIn](https://linkedin.com/in/theophile-lafargue) · [Substack](https://theophilelafargue.substack.com) · [HuggingFace](https://huggingface.co/ox-ox)
