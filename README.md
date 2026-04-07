<!-- github.com/namanadep/namanadep — profile README (shown on https://github.com/namanadep) -->

## Hi, I'm Naman — GPU & HPC infrastructure

I commission, validate, and operate GPU systems for AI and HPC-style workloads (AMD Instinct, NVIDIA datacenter GPUs).  
This README is my **curated index of HPC-related repositories** I maintain on GitHub—similar to an “awesome list,” but only for my own projects. **Update the tables below** whenever you add a new repo.

---

## Master index (all HPC-related repos)

| Repository | Focus | One-line summary |
|------------|-------|------------------|
| [**gpu-obs-quickstart**](https://github.com/namanadep/gpu-obs-quickstart) | Observability | DCGM → Prometheus → Alertmanager → Grafana + `node_exporter`; dashboards & rules in git (H200 NVL). |
| [**isaac-sim-pow**](https://github.com/namanadep/isaac-sim-pow) | Simulation | Isaac Sim 6 on a headless GPU VM: install, fixes, WebRTC/UDP networking notes, handoff docs. |
| [**mi300x-amd-rocm-validation**](https://github.com/namanadep/mi300x-amd-rocm-validation) | AMD / ROCm | ROCm perf, RCCL, HBM stress, thermal — 8-GPU node + single-VF `rocprof`. |
| [**amd-enterprise-ai-platform**](https://github.com/namanadep/amd-enterprise-ai-platform) | AMD / platform | Bloom → RKE2 → ClusterForge → AIRM — deployment narrative and failures documented. |
| [**llm-inference-observability**](https://github.com/namanadep/llm-inference-observability) | Inference / metrics | Qwen3-32B on MI300X VF: throughput, latency, OOM behavior. |
| [**amd-rocm-gpu-ops**](https://github.com/namanadep/amd-rocm-gpu-ops) | Operations | Health checks + Kubernetes GPU Operator runbook patterns. |
| [**multi-node-nccl-p2p-benchmarks**](https://github.com/namanadep/multi-node-nccl-p2p-benchmarks) | Networking / NCCL | Multi-node NCCL P2P, RoCE investigation; RCCL companion on Instinct. |
| [**amd-ai-workbench-ops**](https://github.com/namanadep/amd-ai-workbench-ops) | Ops / workbench | AMD AI Workbench — install, user guide, model deploy. |

---

## Featured write-ups (longer blurbs)

### [gpu-obs-quickstart](https://github.com/namanadep/gpu-obs-quickstart) — observability & GPU infrastructure

**What it is:** Production-style **GPU + host observability** on Linux: **NVIDIA DCGM exporter**, **Prometheus** (alert rules), **Alertmanager**, **Grafana**, and **node_exporter**. Dashboards and datasources are **provisioned from the repo**.

**Why it matters:** Datacenter GPU metrics (utilization, thermal, power, XID-related signals, PCIe/NVLink where exposed) with **host context** (CPU, memory, disk, network) on one dashboard; includes a **screenshot Grafana walkthrough** and monitoring test scenarios.

**Docs:** [README](https://github.com/namanadep/gpu-obs-quickstart/blob/main/README.md) · [Technical orientation](https://github.com/namanadep/gpu-obs-quickstart/blob/main/docs/REVIEWER_BRIEF.md) · [Grafana user guide](https://github.com/namanadep/gpu-obs-quickstart/blob/main/grafana_user_guide/GRAFANA_USER_GUIDE.md)

---

### [isaac-sim-pow](https://github.com/namanadep/isaac-sim-pow) — simulation & Physical AI

**What it is:** **NVIDIA Isaac Sim 6** on a **bare Linux GPU VM** (pip, headless, SSH): storage/cache layout, real install failures and fixes, **headless `SimulationApp`**, and **WebRTC / UDP** networking analysis.

**Why it matters:** Repeatable path from empty VM to working Isaac Sim on datacenter hardware, with observations captured in-repo.

**Docs:** [README](https://github.com/namanadep/isaac-sim-pow/blob/main/README.md) · [GPU VM handoff](https://github.com/namanadep/isaac-sim-pow/blob/main/docs/ISAAC_SIM_GPU_VM_HANDOFF.md) · [WebRTC / UDP deep dive](https://github.com/namanadep/isaac-sim-pow/blob/main/docs/webrtc_udp_deep_dive.md)

---

## Platform snapshots (measured hardware)

Details and numbers live in the repos above; at a glance:

| Platform | Notes |
|----------|--------|
| **AMD Instinct MI300X** (VF & 8-GPU) | FP32/FP16 runs, RCCL all-reduce, HBM stress, thermal — see *mi300x-amd-rocm-validation*. |
| **NVIDIA H200 NVL** | Single-node and 2-node work — ties to *gpu-obs-quickstart*, *isaac-sim-pow*, and NCCL benchmarks repo. |

**Stack keywords:** ROCm · PyTorch · vLLM · RKE2 · AMD GPU Operator · Prometheus · Grafana · CUDA / NVLink.

---

## Skills

`ROCm` `HIP` `rocprof` `RCCL` `NCCL` `PyTorch` `vLLM` · `Kubernetes` `AMD GPU Operator` `RKE2` `Argo CD` · `Prometheus` `Grafana` · `NVIDIA CUDA` `H200` `NVLink`

---

## Writing

Technical articles on GPU infrastructure and AI systems (e.g. Medium) — MI300X vs H200, ROCm setup, NVLink, AllReduce, GPU OOM. *No vendor affiliation; numbers are from real hardware runs.*

---

## Maintaining this index

1. Add a **row** to the **Master index** table when you publish a new HPC-related repo.  
2. Add a **Featured write-up** subsection if the repo needs a longer explanation; otherwise the table row is enough.  
3. Commit and push to **`namanadep/namanadep`** (this repo).

**Tip:** Pin up to **six** repositories on [your profile](https://github.com/namanadep) (e.g. this repo + key projects) so visitors see them above your contribution graph.

---

*Last updated: 2026-04-07*
