# ai-sys-papers

A reading list of AI systems papers, focused on LLM inference and serving.
PDFs are checked in alongside each entry.

## Cross-model KV cache

- [Cross-Model KV Cache Transfer in LLM Families](Cross-Model%20KV%20Cache%20Transfer%20in%20LLM%20Families.pdf)

## Serving systems — [`serving/`](serving/)

| Paper | Venue | Idea |
|---|---|---|
| [Orca](serving/orca-iteration-level-scheduling.pdf) | OSDI 2022 | Iteration-level (continuous) batching. Start here. |
| [vLLM / PagedAttention](serving/vllm-pagedattention.pdf) ([2309.06180](https://arxiv.org/abs/2309.06180)) | SOSP 2023 | Paged KV allocator everything now assumes |
| [Sarathi-Serve](serving/sarathi-serve.pdf) ([2403.02310](https://arxiv.org/abs/2403.02310)) | OSDI 2024 | Chunked prefill; prefill/decode interference |
| [DistServe](serving/distserve.pdf) ([2401.09670](https://arxiv.org/abs/2401.09670)) | OSDI 2024 | Prefill/decode disaggregation for goodput |
| [Splitwise](serving/splitwise.pdf) ([2311.18677](https://arxiv.org/abs/2311.18677)) | ISCA 2024 | Phase splitting onto separate hardware pools |
| [Mooncake](serving/mooncake.pdf) ([2407.00079](https://arxiv.org/abs/2407.00079)) | FAST 2025 | KVCache-centric disaggregated architecture |
| [SGLang / RadixAttention](serving/sglang-radixattention.pdf) ([2312.07104](https://arxiv.org/abs/2312.07104)) | NeurIPS 2024 | Prefix sharing via a radix tree over cached KV |
| [AlpaServe](serving/alpaserve.pdf) ([2302.11665](https://arxiv.org/abs/2302.11665)) | OSDI 2023 | Model parallelism as a latency tool, not just capacity |
| [FlexGen](serving/flexgen.pdf) ([2303.06865](https://arxiv.org/abs/2303.06865)) | ICML 2023 | Offloading-based high throughput on a single GPU |

## KV cache eviction & compression — [`kv-cache/`](kv-cache/)

| Paper | Venue | Idea |
|---|---|---|
| [H2O: Heavy-Hitter Oracle](kv-cache/h2o-heavy-hitter-oracle.pdf) ([2306.14048](https://arxiv.org/abs/2306.14048)) | NeurIPS 2023 | Evict all but heavy-hitter tokens |
| [StreamingLLM](kv-cache/streamingllm-attention-sinks.pdf) ([2309.17453](https://arxiv.org/abs/2309.17453)) | ICLR 2024 | Attention sinks; unbounded streaming |
| [Multi-Query Attention](kv-cache/multi-query-attention.pdf) ([1911.02150](https://arxiv.org/abs/1911.02150)) | 2019 | One write-head — the original cache shrink |
| [GQA](kv-cache/gqa-grouped-query-attention.pdf) ([2305.13245](https://arxiv.org/abs/2305.13245)) | EMNLP 2023 | Grouped-query interpolation between MHA and MQA |
| [DeepSeek-V2 (MLA)](kv-cache/deepseek-v2-mla.pdf) ([2405.04434](https://arxiv.org/abs/2405.04434)) | 2024 | Multi-head latent attention: compress KV to a latent |
| [KVQuant](kv-cache/kvquant.pdf) ([2401.18079](https://arxiv.org/abs/2401.18079)) | NeurIPS 2024 | Low-bit KV quantization to 10M context |
| [KIVI](kv-cache/kivi.pdf) ([2402.02750](https://arxiv.org/abs/2402.02750)) | ICML 2024 | Tuning-free asymmetric 2-bit KV quantization |
| [InfiniGen](kv-cache/infinigen.pdf) ([2406.19707](https://arxiv.org/abs/2406.19707)) | OSDI 2024 | Offloaded KV with speculative prefetch |

## Kernels & long context — [`kernels-long-context/`](kernels-long-context/)

| Paper | Venue | Idea |
|---|---|---|
| [FlashAttention](kernels-long-context/flashattention.pdf) ([2205.14135](https://arxiv.org/abs/2205.14135)) | NeurIPS 2022 | IO-aware exact attention. Required background. |
| [FlashAttention-2](kernels-long-context/flashattention-2.pdf) ([2307.08691](https://arxiv.org/abs/2307.08691)) | 2023 | Better parallelism and work partitioning |
| [FlashAttention-3](kernels-long-context/flashattention-3.pdf) ([2407.08608](https://arxiv.org/abs/2407.08608)) | NeurIPS 2024 | Asynchrony and low precision on Hopper |
| [Ring Attention](kernels-long-context/ring-attention.pdf) ([2310.01889](https://arxiv.org/abs/2310.01889)) | ICLR 2024 | Blockwise sequence parallelism for near-infinite context |

## Mixture of Experts — [`moe/`](moe/)

| Paper | Venue | Idea |
|---|---|---|
| [GShard](moe/gshard.pdf) ([2006.16668](https://arxiv.org/abs/2006.16668)) | ICLR 2021 | Conditional computation + automatic sharding |
| [Switch Transformer](moe/switch-transformer.pdf) ([2101.03961](https://arxiv.org/abs/2101.03961)) | JMLR 2022 | Top-1 routing to trillion parameters |
| [MegaBlocks](moe/megablocks.pdf) ([2211.15841](https://arxiv.org/abs/2211.15841)) | MLSys 2023 | Block-sparse MoE kernels, no token dropping |
| [DeepSpeed-MoE](moe/deepspeed-moe.pdf) ([2201.05596](https://arxiv.org/abs/2201.05596)) | ICML 2022 | MoE inference and training at scale |
| [DeepSeek-V3](moe/deepseek-v3.pdf) ([2412.19437](https://arxiv.org/abs/2412.19437)) | 2024 | Production MoE infra report |

## Speculative decoding — [`speculative-decoding/`](speculative-decoding/)

| Paper | Venue | Idea |
|---|---|---|
| [Speculative Decoding](speculative-decoding/speculative-decoding-leviathan.pdf) ([2211.17192](https://arxiv.org/abs/2211.17192)) | ICML 2023 | The original (Leviathan et al.) |
| [Medusa](speculative-decoding/medusa.pdf) ([2401.10774](https://arxiv.org/abs/2401.10774)) | ICML 2024 | Multiple decoding heads, no draft model |
| [EAGLE](speculative-decoding/eagle.pdf) ([2401.15077](https://arxiv.org/abs/2401.15077)) | ICML 2024 | Drafting at the feature level |
| [SpecInfer](speculative-decoding/specinfer.pdf) ([2305.09781](https://arxiv.org/abs/2305.09781)) | ASPLOS 2024 | Tree-based speculation and token-tree verification |

---

