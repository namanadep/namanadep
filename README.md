<!-- Copy this file to: https://github.com/<your-username>/<your-username>/blob/main/README.md -->

### Hi, I'm Naman — GPU infrastructure & performance engineering

I commission, benchmark, and operate GPU clusters for AI workloads. My work spans **NVIDIA H200** and **AMD MI300X** hardware: multi-node NCCL/RCCL collectives, MIG and XGMI topology validation, cluster observability (DCGM / AMD metrics exporter / Prometheus), SLURM scheduler operations, storage benchmarking, and LLM inference measurement. I write about what I measure — not vendor spec sheets.

**Hardware I have worked on directly:**
- NVIDIA H200 NVL and H200 SXM — 8-GPU single-node and 2-node 16-GPU clusters
- AMD Instinct MI300X VF — 8× GPUs, 1.54 TB total HBM3, ROCm 6.4.1

**Stack:** PyTorch / CUDA / ROCm · NCCL / RCCL · SLURM · DCGM / AMD metrics exporter · Prometheus / Grafana · fio · nccl-tests · MPI

### Pinned portfolio (start here)

| Repo | What it demonstrates |
|------|----------------------|
| [**mi300x-amd-rocm-validation**](https://github.com/naman-adep/mi300x-amd-rocm-validation) | Full AMD MI300X validation: 94.5 TFLOPS FP32, 433 GB/s RCCL AllReduce, 1.29 TB stress — real scripts and 9 production-readiness reports |
| [**multi-node-nccl-p2p-benchmarks**](https://github.com/naman-adep/multi-node-nccl-p2p-benchmarks) | 16-GPU H200 NCCL commissioning: NVLink ~781 GB/s intra-node, TCP ~2.28 GB/s cross-node, full RoCE v2 failure investigation (IBV_WC_RETRY_EXC_ERR, PFC/ECN root cause) |
| [**cuda-pytorch-optimization-benchmarks**](https://github.com/naman-adep/cuda-pytorch-optimization-benchmarks) | 4 measured experiments on H200SXM: kernel fusion 7.94×, Tensor Core 14.38×, training loop 7.34×, 95.24% memory fragmentation |
| [**h200-gpu-benchmark-suite**](https://github.com/naman-adep/h200-gpu-benchmark-suite) | H200 NVL: 46.5 TFLOPS FP32, 548W peak, 100% utilization — reproducible CLI + real monitoring CSV |
| [**storage-ai-fio-benchmarks**](https://github.com/naman-adep/storage-ai-fio-benchmarks) | 144 fio benchmarks on H200 cluster: VAST vs NetApp — 10.9× mixed IOPS gap (207K vs 19K) |
| [**hpc-gpu-observability-lab**](https://github.com/naman-adep/hpc-gpu-observability-lab) | Dual-vendor telemetry: NVIDIA DCGM + AMD amd-metrics-exporter, both port 9400, same Prometheus stack — real GPU power/temp CSV included |
| [**llm-inference-observability**](https://github.com/naman-adep/llm-inference-observability) | Inference harness: Ollama on H200 NVL — 704 tokens/s, 12-request latency table, correlated GPU telemetry |
| [**slurm-job-analyzer**](https://github.com/naman-adep/slurm-job-analyzer) | SLURM 2-node 16-GPU cluster: Job 31 — all 16 H200s at 100% util for 3 min, real monitoring snapshots + slurm.conf |
| [**mig-performance-lab**](https://github.com/naman-adep/mig-performance-lab) | MIG profile tradeoffs: isolation vs throughput on A100/H100-class GPUs |

Replace `naman-adep` with your GitHub username if different.

### Writing

Medium: [@adepnaman](https://medium.com/@adepnaman) — benchmarks on H200 and MI300X, NCCL, mixed precision, kernel fusion, GPU memory, VAST vs NetApp storage, and India AI infrastructure.

### Contact

LinkedIn: [naman-adep](https://www.linkedin.com/in/naman-adep/) · Mentoring: [topmate.io/namanadep](https://topmate.io/namanadep)

---

<p align="center">
  <img src="https://img.shields.io/badge/NVIDIA-H200-76B900?style=flat&logo=nvidia&logoColor=white" alt="NVIDIA H200" />
  <img src="https://img.shields.io/badge/AMD-MI300X-ED1C24?style=flat&logo=amd&logoColor=white" alt="AMD MI300X" />
  <img src="https://img.shields.io/badge/Stack-CUDA%20%7C%20ROCm%20%7C%20NCCL%20%7C%20SLURM-111?style=flat" alt="Stack" />
</p>
