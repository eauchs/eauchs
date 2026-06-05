# Théophile Lafargue

**20 · Founder · Paris**

I build AI infrastructure for constrained environments — the edges where most systems stop working.

**Available for contract work** — Apple Silicon LLM inference: KV-cache optimization, quantization, speculative decoding, throughput tuning.
→ **contact@aeternitatis.eu**

Student-Entrepreneur — Pépite PEIPS, Université Paris-Saclay (SNEE)
ORCID: [0009-0001-5727-2475](https://orcid.org/0009-0001-5727-2475)

---

### Selected proof

- First GGUF quants of MiniMax-M2.5 & M2.7 (229B MoE) — used and recommended by the llama.cpp / r/LocalLLaMA community
- llama.cpp PRs **merged and cited as prior work** by core maintainers
- Native MLX speculative decoding port — **3.41× faster** inference on Apple Silicon

---

### Open-source contributions

| PR | What it does | Status |
|----|--------------|--------|
| **llama.cpp #20075** | Fix state corruption in speculative decoding on hybrid SSM/MoE models. +45% inference speed on Apple Silicon Metal. | Merged · cited as prior work in #20428 + #20649 |
| **llama.cpp #20649** | Diagnostic + flake8 fix for Mistral Small 4 (119B MoE). | Merged · cited alongside ggerganov + ngxson |
| **unslothai/unsloth #4901** | Fix RoPE offset cast crashing Gemma 4 inference on Apple Silicon. | Merged by danielhanchen (creator) |
| **StepFun Cookbook #14** | Local deployment architecture for Step-3.5-Flash on Apple Silicon. | Merged |

---

### Projects

| Project | Description |
|---------|-------------|
| **mlx-dflash** | Native MLX port of DFlash speculative decoding. 3.41× faster inference on Apple Silicon — Qwen3-8B bf16, M3 Max 128GB, 1024 tokens. Acceptance 8.75/16. Single `mx.eval()` per step, intra-GPU `verify_ids`. |
| **LACE** | Semantic compression under LoRa/SMS physical constraints. Cognitive Emergence Law: N/K < C·d_cog, C_emp=0.391≈1/e. K=16 optimal deployment parameter (p=0.0034). Preprint: HAL hal-05596229 · Zenodo 10.5281/zenodo.19664121 |
| **mythos-distillation** | Behavioral distillation into Gemma 4 26B MoE via LoRA (r=64, 30 layers). 551 pairs, val loss 1.398, 7/7 out-of-distribution questions generalized without system prompt. 80 t/s on M3 Max. |
| **patent-low-bandwidth-ai** | Reference gateway for stateful LLM dialogue over 2G / SMS. Companion implementation to patent FR2511116 (architecture). |
| **Phantom** | On-device behavioral AI OS. Two-Tower (LSTM 256d + action embeddings), full RLHF loop via local Qwen 122B as reward model. MLX, zero cloud. |
| **VoxTape** | Local voice dictation for macOS. MLX Whisper on Metal GPU: 8.3s audio → 0.4s inference (20× real-time). Open-source alternative to SuperWhisper. |
| **benchmark-422-qec** | 11 LLMs (cloud + local M3 Max) on the [[4,2,2]] CritPt QEC problem. 0/11 correct. Failure patterns documented. |

---

### Models — HuggingFace ([ox-ox](https://huggingface.co/ox-ox))

| Repo | Description | Downloads |
|------|-------------|-----------|
| **MiniMax-M2.7-GGUF** | First GGUF quants of MiniMax-M2.7 (229B MoE). Q3_K_L + Q8_0. PPL 8.44 · 28.52 t/s. | 522 |
| **MiniMax-M2.5-GGUF** | First GGUF quants of MiniMax-M2.5 (229B MoE). PPL 8.79 · 28.7 t/s. Recommended by llama.cpp community. | 437 |
| **mythos-character-distillation** | 551 behavioral pairs for Mythos-style LoRA distillation. | 66 |
| **lace-semantic-compression** | 198 operational tasks (defense / medical / industrial), VQ codebook, LACE v2 dataset. | 40 |

---

### Patent

**FR2511116** — Hybrid State-Preserving Gateway for LLM Inference over Low-Bandwidth Protocols (2G / SMS / LoRa / satellite)
Filed: Sep 27, 2025 · INPI · 11 claims · examination in progress

---

### Stack

**Inference** — llama.cpp · MLX · Metal · GGUF · speculative decoding
**AI/ML** — LoRA · Transformers · VQ-VAE · RAG (ChromaDB) · Whisper · RLHF
**Protocols** — LoRa / 2G / SMS / satellite · Flask gateway
**Languages** — Python · C++
**Infra** — Tailscale · bare-metal homelab · M3 Max 128GB

---

[LinkedIn](https://www.linkedin.com/theophile-lafargue) · [Substack](https://theophilelafargue.substack.com) · [HuggingFace](https://huggingface.co/ox-ox) · [ORCID](https://orcid.org/0009-0001-5727-2475)
