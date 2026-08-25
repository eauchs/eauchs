# Théophile Lafargue

**Founder & CTO — [Sub Specie Aeternitatis](https://aeternitatis.eu)** · Paris

Sovereign LLM inference where networks end — 2G/SMS, LoRa, satellite.
The model runs on-premise. No data leaves the machine. Patent **FR2511116** (INPI, filed Sep 2025, 11 claims, under examination).

> **200,000+ views** on r/LocalLLaMA release posts · **32,800+ downloads** on my open-source model builds (**12,100** in the last 30 days)
> First public MLX/GGUF builds of 4 frontier models · PRs merged into `llama.cpp`, `unsloth`, `StepFun Cookbook`

**Available for contract work** — Apple Silicon LLM inference: KV-cache optimization, quantization, speculative decoding, throughput tuning.
→ **contact@aeternitatis.eu**

---

## Shipped

| Model build | What it was | All-time | Last 30d |
|---|---|---:|---:|
| [**DeepSeek-V4-Flash-0731**](https://huggingface.co/ox-ox/DeepSeek-V4-Flash-0731-gguf-ds4) | GGUF quants (IQ2_XXS / Q2_K / Q4_K) + the **430 MB imatrix** collected on the 0731 weights | **9,697** | **9,697** |
| [**MiniMax-M2.5**](https://huggingface.co/ox-ox/MiniMax-M2.5-GGUF) (230B MoE) | *First* public GGUF quants — **87k views on r/LocalLLaMA**, integrated into ubergarm's reference quantization chart | **13,890** | 88 |
| [**Laguna M.1**](https://huggingface.co/ox-ox/Laguna-M.1-MLX-Q3) (225B-A23B MoE) | *First* Apple Silicon build of Poolside's frontier release — 3-bit, ~26 t/s, ~100 GB peak on M3 Max 128GB. Featured by Poolside. | **4,707** | 1,322 |
| [**Hy3-295B-Instruct**](https://huggingface.co/ox-ox/Hy3-295B-Instruct-w2q3exp-AProjQ8-SExpQ8-OutQ8-MTP-mlx) | Mixed-precision MLX build w/ MTP | **2,038** | 524 |
| [**MiniMax-M2.7**](https://huggingface.co/ox-ox/MiniMax-M2.7-GGUF) (229B MoE) | *First* public GGUF quants — Q3_K_L + Q8_0, PPL 8.44, 28.5 t/s · **17k views on r/LocalLLaMA** | 732 | 35 |
| [Qwen3-VL-32B-Thinking](https://huggingface.co/ox-ox/Qwen3-VL-32B-Thinking-FP8-Q3_K_M-GGUF) | GGUF quants | 249 | 41 |

Datasets: [mythos-character-distillation](https://huggingface.co/datasets/ox-ox/mythos-character-distillation) (1,328) · [lace-semantic-compression](https://huggingface.co/datasets/ox-ox/lace-semantic-compression) (211)

*HuggingFace counts exclude GGUF files pulled directly via llama.cpp / Ollama / direct download — real usage is higher.*
Member of [`mlx-community`](https://huggingface.co/mlx-community).

---

## Upstream contributions

| PR | What it does | Status |
|---|---|---|
| [`llama.cpp` #20075](https://github.com/ggml-org/llama.cpp/pull/20075) | Fix state corruption in speculative decoding on hybrid SSM/MoE models. **+45% inference speed** on Apple Silicon Metal. | **Merged** — cited as prior work in #20428 and #20649 |
| [`llama.cpp` #20649](https://github.com/ggml-org/llama.cpp/pull/20649) | Mistral Small 4 (119B MoE) support — diagnostic + fix. | **Merged** — alongside ggerganov, ngxson |
| [`unsloth` #4901](https://github.com/unslothai/unsloth/pull/4901) | Fix RoPE offset cast crashing Gemma 4 inference on Apple Silicon. | **Merged** by danielhanchen (creator) |
| [`StepFun Cookbook` #14](https://github.com/stepfun-ai/StepFun-Cookbook/pull/14) | Local deployment architecture for Step-3.5-Flash on Apple Silicon. | **Merged** |
| [`mlx-lm` #1415](https://github.com/ml-explore/mlx-lm/pull/1415) | Laguna M.1 (225B-A23B MoE) architecture for mlx-lm. | Not merged upstream — [weights shipped directly](https://huggingface.co/ox-ox/Laguna-M.1-MLX-Q3) (4.7k downloads) |

---

## Projects

| | |
|---|---|
| [**mlx-dflash**](https://github.com/eauchs/mlx-dflash) | Native MLX port of DFlash speculative decoding. **3.34× faster** inference on Apple Silicon — Qwen3-8B bf16, M3 Max 128GB, 1024 tokens. Acceptance 8.68/16. Single `mx.eval()` per step, intra-GPU `verify_ids`. |
| **modex** *(private)* | Fully local assistant stack running on my own published DeepSeek-V4-Flash quant. Terminal client in C on top of `ds4-server`: persistent memory, **43 tools** (6 native + 37 MCP — sandboxed exec, web), **11 skills**, **5 grounding packs**, 131k-token context with on-disk KV cache. Companion iOS app (SwiftUI) over a private Tailscale network. Zero cloud. |
| [**grounding-engine**](https://github.com/eauchs/grounding-engine) | Keep a local LLM honest: the model proposes validated, typed deltas instead of mutating state — invalid changes are rejected before they exist. Anti-hallucination by construction. Zero deps, OpenAI-compatible, MIT. Powers modex's grounding packs and a fully offline grand-strategy engine. |
| [**LACE**](https://github.com/eauchs/lace) | Semantic compression under LoRa/SMS physical constraints. Cognitive Emergence Law: `N/K < C·d_cog`, C_emp = 0.391 ≈ 1/e. K=16 optimal deployment parameter (p=0.0034). Preprint: [HAL hal-05596229](https://hal.science/hal-05596229) · [Zenodo](https://doi.org/10.5281/zenodo.19664121) |
| [**mythos**](https://github.com/eauchs/mythos) | Behavioral distillation into Gemma 4 26B MoE via LoRA (r=64, 30 layers). 551 pairs, val loss 1.398, 7/7 out-of-distribution generalization without system prompt. 80 t/s on M3 Max. |
| **patent-low-bandwidth-ai** *(private)* | Reference gateway for stateful LLM dialogue over 2G / SMS — companion implementation to FR2511116. End-to-end SMS round trip under 10 s, fully offline, commodity hardware. |
| [**speech-to-speech-pipeline**](https://github.com/eauchs/speech-to-speech-pipeline) | Real-time interruptible (barge-in) STT-LLM-TTS pipeline, fully local, MLX-optimized. |
| [**VoxTape**](https://github.com/eauchs/voxtape) | Local voice dictation for macOS. MLX Whisper on Metal: 8.3s audio → 0.4s inference (20× real-time). |

---

## Stack

**Inference** — llama.cpp · MLX · Metal · GGUF · speculative decoding · quantization
**AI/ML** — LoRA · Transformers · VQ-VAE · RAG · Whisper · RLHF
**Protocols** — LoRa / 2G / SMS / satellite · stateful gateway
**Languages** — Python · C++ · Rust
**Infra** — bare-metal homelab · M3 Max 128GB · Tailscale

---

Student-Entrepreneur — Pépite PEIPS, Université Paris-Saclay
ORCID [0009-0001-5727-2475](https://orcid.org/0009-0001-5727-2475)

[Site](https://aeternitatis.eu) · [LinkedIn](https://linkedin.com/in/theophile-lafargue) · [Substack](https://theophilelafargue.substack.com) · [HuggingFace](https://huggingface.co/ox-ox) · [X](https://x.com/eauchs)
