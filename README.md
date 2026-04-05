<!-- github.com/namanadep/namanadep — profile README -->

## Hi, I'm Naman — GPU infrastructure & performance engineering

I commission, validate, and operate GPU clusters for AI workloads — AMD Instinct and NVIDIA.
Everything below was measured on real hardware.

---

### AMD Instinct / ROCm work

| System | Specs | What I measured |
|--------|-------|-----------------|
| **AMD Instinct MI300X VF** | 191.69 GiB HBM3, gfx942 / CDNA3, ROCm 6.4.1 | FP32 90.56 TFLOPS · FP16 4.20× speedup · Qwen3-32B 296 tok/s @ conc=8 |
| **AMD MI300X (8-GPU node)** | 8× 192 GiB HBM3, XGMI, RCCL 2.22.3 | RCCL all-reduce bandwidth · 1.29 TB memory stress · thermal at 750 W/GPU |

**Stack:** ROCm 6.4.1 · PyTorch 2.4.1+rocm6.0 · RKE2 v1.34.1 · AMD GPU Operator v1.4.1 · AIRM / vLLM

---

### NVIDIA work (breadth)

| System | Key specs |
|--------|-----------|
| NVIDIA H200 NVL (single node) | 143 GiB HBM3e, NVLink 4.0 · 46.5 TFLOPS FP32 |
| NVIDIA H200 (2-node cluster) | NVLink intra-node ~781 GB/s · RoCE v2 failure investigation |

---

### Pinned repositories

| # | Repo | Signal |
|---|------|--------|
| 1 | [mi300x-amd-rocm-validation](https://github.com/namanadep/mi300x-amd-rocm-validation) | ROCm perf · RCCL · HBM stress · thermal — 8-GPU node + single-VF rocprof |
| 2 | [amd-enterprise-ai-platform](https://github.com/namanadep/amd-enterprise-ai-platform) | Bloom → RKE2 → ClusterForge → AIRM — every failure documented |
| 3 | [llm-inference-observability](https://github.com/namanadep/llm-inference-observability) | Qwen3-32B on MI300X VF: 296 tok/s, TTFT p50 62 ms, zero OOM |
| 4 | [amd-rocm-gpu-ops](https://github.com/namanadep/amd-rocm-gpu-ops) | Operational health checks + K8s GPU Operator runbook |
| 5 | [multi-node-nccl-p2p-benchmarks](https://github.com/namanadep/multi-node-nccl-p2p-benchmarks) | H200 NCCL P2P · RoCE investigation · RCCL-on-Instinct companion |
| 6 | [amd-ai-workbench-ops](https://github.com/namanadep/amd-ai-workbench-ops) | AI Workbench operations — install, user guide, model deploy |

---

### Skills

`ROCm` `HIP` `rocprof` `RCCL` `NCCL` `PyTorch` `vLLM`
`Kubernetes` `AMD GPU Operator` `RKE2` `Argo CD`
`Prometheus` `Grafana` `GPU observability`
`NVIDIA CUDA` `H200` `NVLink` `MIG`

---

### Writing

Technical articles on GPU infrastructure, performance engineering, and AI systems —
published on Medium. Topics: MI300X vs H200, ROCm setup, NVLink, AllReduce, GPU OOM.

---

> All numbers are from real hardware runs. VF and single-GPU constraints are called out
> in each repo. No vendor affiliation.
