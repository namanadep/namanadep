<!-- Profile repo: github.com/namanadep/namanadep -->

### GitHub pins (do this in the UI — API cannot set pins)

GitHub does not allow setting profile pins via `gh` or the public API. While logged in as **namanadep**:

1. Open [github.com/namanadep](https://github.com/namanadep).
2. Click **Customize your pins** (or **Edit profile** → pinned repositories).
3. **Unpin** anything that is not in the list below (e.g. old AI/ESG/security demos).
4. **Pin exactly these four** (order is up to you; you can add up to **6** total if you want two more later):

| Pin | Repository |
|-----|------------|
| 1 | [mi300x-amd-rocm-validation](https://github.com/namanadep/mi300x-amd-rocm-validation) |
| 2 | [multi-node-nccl-p2p-benchmarks](https://github.com/namanadep/multi-node-nccl-p2p-benchmarks) |
| 3 | [cuda-pytorch-optimization-benchmarks](https://github.com/namanadep/cuda-pytorch-optimization-benchmarks) |
| 4 | [hpc-gpu-observability-lab](https://github.com/namanadep/hpc-gpu-observability-lab) |

---

### Hi, I'm Naman — GPU infrastructure & HPC performance engineering

I commission, validate, and operate GPU clusters for AI workloads. I have run experiments on real hardware — not simulators, not vendor-provided benchmarks — and written down what I measured.

---

### Hardware I have worked on directly

| System | Key specs | What I measured |
|--------|-----------|-----------------|
| **NVIDIA H200 NVL** (8-GPU node) | 141 GB HBM3e, NVLink 4.0 (NV18) | 46.5 TFLOPS FP32, 548 W peak, 100% util · Ollama 704 tokens/s |
| **NVIDIA H200 SXM** (training cluster) | 2,725 GB/s HBM bandwidth, CUDA 12.8 | Kernel fusion 7.94×, Tensor Core 14.38×, training loop 7.34× |
| **2-node 16-GPU H200 NVL cluster** | NVLink intra-node, RoCE v2 cross-node | NCCL AllReduce ~781 GB/s intra-node · TCP fallback 2.28 GB/s · Full RoCE v2 failure investigation |
| **AMD Instinct MI300X VF** (8-GPU node) | 192 GB HBM3/GPU · 1.54 TB total · XGMI full-mesh | 94.5 TFLOPS FP32 · RCCL AllReduce 433 GB/s · 1.29 TB stressed · ROCm 6.4.1 |

---

### Problems I solve

**Cluster commissioning** — driver/NCCL/ROCm stack validation, GRES GPU config, munge auth, SLURM scheduler bring-up, acceptance testing before handing a cluster to users.

**Performance measurement** — FLOPS-vs-theoretical gap analysis, collective bandwidth sweeps (NCCL/RCCL), kernel fusion and mixed precision profiling, memory allocator behavior under fragmentation.

**Failure investigation** — RoCE v2 IBV_WC_RETRY_EXC_ERR root cause (PFC/ECN fabric misconfiguration), SLURM GPU GRES mismatches causing silent queue stalls, GPU thermal throttle identification.

**Observability** — DCGM exporter + AMD amd-metrics-exporter unified on port 9400, Prometheus scrape configs, XID error alerting, sacct-based GPU waste reports.

**Storage for AI** — fio benchmarks with O_DIRECT (144 tests), data loading vs checkpointing IOPS decomposition, VAST vs NetApp real-cluster comparison.

---

### Selected work (flagship repos — start here)

| Repo | Key result | What it shows |
|------|-----------|---------------|
| [**mi300x-amd-rocm-validation**](https://github.com/namanadep/mi300x-amd-rocm-validation) | 94.5 TFLOPS · 433 GB/s RCCL · 1.29 TB stress · 0 throttle events | Complete AMD MI300X commissioning checklist — 9 production-readiness reports, ROCm bring-up, XGMI topology, amd-metrics-exporter |
| [**multi-node-nccl-p2p-benchmarks**](https://github.com/namanadep/multi-node-nccl-p2p-benchmarks) | NVLink ~781 GB/s · TCP ~2.28 GB/s · RoCE v2 IBV_WC_RETRY_EXC_ERR diagnosed | 16-GPU H200 NCCL commissioning — full P2P matrix, cross-node AllReduce sweep, RoCE v2 PFC/ECN failure investigation |
| [**cuda-pytorch-optimization-benchmarks**](https://github.com/namanadep/cuda-pytorch-optimization-benchmarks) | Kernel fusion 7.94× · Tensor Core 14.38× · training loop 7.34× · 95.24% fragmentation | 4 measured experiments on H200SXM — why each optimization works, not just that it works |
| [**hpc-gpu-observability-lab**](https://github.com/namanadep/hpc-gpu-observability-lab) | NVIDIA DCGM + AMD amd-metrics-exporter, both port 9400 | Dual-vendor telemetry — unified Prometheus stack, real GPU power/temp CSV, XID error alerting |

---

### All repos

| Repo | What it demonstrates |
|------|----------------------|
| [**mi300x-amd-rocm-validation**](https://github.com/namanadep/mi300x-amd-rocm-validation) | Full AMD MI300X validation: 94.5 TFLOPS FP32, 433 GB/s RCCL AllReduce, 1.29 TB stress — real scripts and 9 production-readiness reports |
| [**multi-node-nccl-p2p-benchmarks**](https://github.com/namanadep/multi-node-nccl-p2p-benchmarks) | 16-GPU H200 NCCL commissioning: NVLink ~781 GB/s intra-node, TCP ~2.28 GB/s cross-node, full RoCE v2 failure investigation (IBV_WC_RETRY_EXC_ERR, PFC/ECN root cause) |
| [**cuda-pytorch-optimization-benchmarks**](https://github.com/namanadep/cuda-pytorch-optimization-benchmarks) | 4 measured experiments on H200SXM: kernel fusion 7.94×, Tensor Core 14.38×, training loop 7.34×, 95.24% memory fragmentation |
| [**hpc-gpu-observability-lab**](https://github.com/namanadep/hpc-gpu-observability-lab) | Dual-vendor telemetry: NVIDIA DCGM + AMD amd-metrics-exporter, both port 9400, same Prometheus stack — real GPU power/temp CSV included |
| [**h200-gpu-benchmark-suite**](https://github.com/namanadep/h200-gpu-benchmark-suite) | H200 NVL: 46.5 TFLOPS FP32, 548W peak, 100% utilization — reproducible CLI + real monitoring CSV |
| [**storage-ai-fio-benchmarks**](https://github.com/namanadep/storage-ai-fio-benchmarks) | 144 fio benchmarks on H200 cluster: VAST vs NetApp — 10.9× mixed IOPS gap (207K vs 19K) |
| [**llm-inference-observability**](https://github.com/namanadep/llm-inference-observability) | Inference harness: Ollama on H200 NVL — 704 tokens/s, 12-request latency table, correlated GPU telemetry |
| [**slurm-job-analyzer**](https://github.com/namanadep/slurm-job-analyzer) | SLURM 2-node 16-GPU cluster: Job 31 — all 16 H200s at 100% util for 3 min, GPU waste report, queue-wait analysis |
| [**mig-performance-lab**](https://github.com/namanadep/mig-performance-lab) | MIG profile tradeoffs: isolation vs throughput on A100/H100-class GPUs |

### Writing

Medium: [@adepnaman](https://medium.com/@adepnaman) — benchmarks on H200 and MI300X, NCCL, mixed precision, kernel fusion, GPU memory, VAST vs NetApp storage, India AI infrastructure.

Topics: *CUDA kernel fusion 7.94×* · *MI300X vs H200 actual numbers* · *RoCE v2 IBV_WC_RETRY_EXC_ERR root cause* · *14.38× Tensor Core speedup* · *144 storage benchmarks VAST vs NetApp*

---

### Contact

LinkedIn: [namanadep](https://www.linkedin.com/in/namanadep/) · Mentoring: [topmate.io/namanadep](https://topmate.io/namanadep)

---

<p align="center">
  <img src="https://img.shields.io/badge/NVIDIA-H200-76B900?style=flat&logo=nvidia&logoColor=white" alt="NVIDIA H200" />
  <img src="https://img.shields.io/badge/AMD-MI300X-ED1C24?style=flat&logo=amd&logoColor=white" alt="AMD MI300X" />
  <img src="https://img.shields.io/badge/ROCm-6.4.1-ED1C24?style=flat&logo=amd&logoColor=white" alt="ROCm 6.4.1" />
  <img src="https://img.shields.io/badge/CUDA-12.8-76B900?style=flat&logo=nvidia&logoColor=white" alt="CUDA 12.8" />
  <img src="https://img.shields.io/badge/Stack-NCCL%20%7C%20RCCL%20%7C%20SLURM%20%7C%20DCGM-111?style=flat" alt="Stack" />
</p>
