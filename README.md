# Naman — GPU & HPC Infrastructure

GPU commissioning, validation, and operations across NVIDIA and AMD datacenter hardware.
Hands-on with **H200 NVL**, **MI300X**, multi-node NCCL, ROCm, and Physical AI (Isaac Sim).

[![GPU Observability](https://img.shields.io/badge/GPU_Observability-DCGM_·_Prometheus_·_Grafana-76B900?style=flat-square&logo=nvidia)](https://github.com/namanadep/gpu-obs-quickstart)
[![Physical AI](https://img.shields.io/badge/Physical_AI-Isaac_Sim_6_·_H200_NVL-76B900?style=flat-square&logo=nvidia)](https://github.com/namanadep/isaac-sim-pow)
[![ROCm](https://img.shields.io/badge/AMD_ROCm-MI300X_·_RCCL_·_rocprof-ED1C24?style=flat-square&logo=amd)](https://github.com/namanadep/mi300x-amd-rocm-validation)

---

## Projects

| Repository | Domain | Summary |
|------------|--------|---------|
| [**gpu-obs-quickstart**](https://github.com/namanadep/gpu-obs-quickstart) | Observability | DCGM → Prometheus → Alertmanager → Grafana + node_exporter; 24 GPU metrics, 12 alert rules, all provisioned from git (H200 NVL) |
| [**isaac-sim-pow**](https://github.com/namanadep/isaac-sim-pow) | Physical AI / Simulation | Isaac Sim 6 pip install on a bare headless GPU VM — real failures documented, headless `SimulationApp` verified, WebRTC/UDP networking analysis |
| [**mi300x-amd-rocm-validation**](https://github.com/namanadep/mi300x-amd-rocm-validation) | AMD / ROCm | ROCm perf, RCCL all-reduce, HBM stress, thermal validation — 8-GPU node + single VF with `rocprof` |
| [**amd-enterprise-ai-platform**](https://github.com/namanadep/amd-enterprise-ai-platform) | AMD / Platform | Bloom → RKE2 → ClusterForge → AIRM deployment narrative with failures documented |
| [**llm-inference-observability**](https://github.com/namanadep/llm-inference-observability) | Inference | Qwen3-32B on MI300X VF: throughput, latency, OOM behaviour |
| [**multi-node-nccl-p2p-benchmarks**](https://github.com/namanadep/multi-node-nccl-p2p-benchmarks) | Networking | Multi-node NCCL P2P, RoCE investigation; RCCL companion on Instinct |
| [**amd-rocm-gpu-ops**](https://github.com/namanadep/amd-rocm-gpu-ops) | Operations | Health checks + Kubernetes GPU Operator runbook patterns |
| [**amd-ai-workbench-ops**](https://github.com/namanadep/amd-ai-workbench-ops) | Ops | AMD AI Workbench — install, user guide, model deploy |

---

## Highlights

### GPU Observability — [gpu-obs-quickstart](https://github.com/namanadep/gpu-obs-quickstart)

Production-style GPU + host observability on a bare H200 NVL VM.
DCGM exporter surfaces metrics that `nvidia-smi` polling cannot — XID hardware errors, SM-level occupancy, HBM temperature, PCIe/NVLink bandwidth — alongside Prometheus alert rules, Alertmanager routing, and a Grafana dashboard provisioned from git with zero click-ops.

**24 GPU metrics · 12 alert rules · 74 host metrics via node_exporter**

→ [README](https://github.com/namanadep/gpu-obs-quickstart/blob/main/README.md) · [Dashboard spec](https://github.com/namanadep/gpu-obs-quickstart/blob/main/docs/dashboard-spec.md) · [Grafana user guide](https://github.com/namanadep/gpu-obs-quickstart/blob/main/grafana_user_guide/GRAFANA_USER_GUIDE.md)

---

### Physical AI / Simulation — [isaac-sim-pow](https://github.com/namanadep/isaac-sim-pow)

NVIDIA Isaac Sim 6.0.0 installed via pip on a bare H200 NVL VM (SSH-only, no Docker, no desktop).
Documents real install failures (`No space left on device` on 4 GB+ wheels, `libGLU` segfault on RTX init), fixes applied, headless `SimulationApp` lifecycle verified, and Full Streaming WebRTC started with TCP signaling confirmed. The UDP media gap is fully diagnosed with three concrete paths to unblock browser video (Tailscale, bastion DNAT, Chisel tunnel).

→ [README](https://github.com/namanadep/isaac-sim-pow/blob/main/README.md) · [GPU VM session notes](https://github.com/namanadep/isaac-sim-pow/blob/main/docs/ISAAC_SIM_GPU_VM_HANDOFF.md) · [WebRTC / UDP deep dive](https://github.com/namanadep/isaac-sim-pow/blob/main/docs/webrtc_udp_deep_dive.md)

---

### AMD MI300X Validation — [mi300x-amd-rocm-validation](https://github.com/namanadep/mi300x-amd-rocm-validation)

ROCm performance validation, RCCL all-reduce benchmarks, HBM stress testing, and thermal characterisation on an 8-GPU MI300X node and a single VF, with `rocprof` profiling.

---

## Hardware

| Platform | Work |
|----------|------|
| **NVIDIA H200 NVL** | GPU observability stack, Isaac Sim 6 / Physical AI, NCCL benchmarks |
| **AMD Instinct MI300X** | ROCm validation, RCCL, HBM stress, LLM inference (Qwen3-32B / vLLM) |

---

## Stack

![NVIDIA](https://img.shields.io/badge/NVIDIA-CUDA_·_DCGM_·_NVLink-76B900?style=flat-square&logo=nvidia)
![AMD](https://img.shields.io/badge/AMD-ROCm_·_HIP_·_RCCL-ED1C24?style=flat-square&logo=amd)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

`NCCL` `rocprof` `vLLM` `Isaac Sim` `RKE2` `Argo CD` `Alertmanager` `DCGM`

---

## Writing

Technical articles on GPU infrastructure — MI300X vs H200, ROCm setup, NVLink, AllReduce, GPU OOM — based on real hardware runs, no vendor affiliation.

---

*Updated 2026-04-07*
