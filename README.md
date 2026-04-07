# HPC & GPU — repository index

I maintain this page as a **single entry point** to my **HPC-related** work on GitHub: GPU observability, simulation, and supporting tooling. It is updated when I add or significantly change a repository.

**Browse by category below**, or jump straight to a repo from the summary table.

---

## Summary

| Repository | Category | One-line summary |
|------------|----------|------------------|
| [**gpu-obs-quickstart**](https://github.com/namanadep/gpu-obs-quickstart) | Observability | Docker Compose stack: DCGM → Prometheus → Alertmanager → Grafana + `node_exporter`; dashboards and rules in git. |
| [**isaac-sim-pow**](https://github.com/namanadep/isaac-sim-pow) | Simulation | Isaac Sim 6 on a headless GPU VM (H200 NVL): install, fixes, WebRTC/network notes, and handoff docs. |

---

## Observability & GPU infrastructure

### [gpu-obs-quickstart](https://github.com/namanadep/gpu-obs-quickstart)

**What it is:** Production-style **GPU + host observability** on Linux using **NVIDIA DCGM exporter**, **Prometheus** (alert rules), **Alertmanager**, **Grafana**, and **node_exporter**. Dashboards and datasources are **provisioned from the repo** (not click-ops).

**Why it matters:** Datacenter-oriented GPU metrics (utilization, thermal, power, XID-related signals, PCIe/NVLink where exposed) with **host-side context** (CPU, memory, disk, network) on one Grafana dashboard. Includes a **visual Grafana walkthrough** with screenshots and a monitoring guide with test scenarios.

**Stack:** DCGM → Prometheus → Alertmanager + Grafana · validated on **NVIDIA H200 NVL**.

**Docs:** [README](https://github.com/namanadep/gpu-obs-quickstart/blob/main/README.md) · [Technical orientation](https://github.com/namanadep/gpu-obs-quickstart/blob/main/docs/REVIEWER_BRIEF.md) · [Grafana user guide](https://github.com/namanadep/gpu-obs-quickstart/blob/main/grafana_user_guide/GRAFANA_USER_GUIDE.md)

---

## Simulation & Physical AI

### [isaac-sim-pow](https://github.com/namanadep/isaac-sim-pow)

**What it is:** Hands-on documentation for running **NVIDIA Isaac Sim 6** on a **bare Linux GPU VM** (pip-based, headless, SSH-only): storage and cache layout, real install failures and fixes, **headless `SimulationApp`** verification, and a deep dive on **WebRTC / UDP** networking for streaming.

**Why it matters:** Practical path from empty VM to a working Isaac Sim environment on datacenter-class hardware, with **observations and results** captured for repeatability.

**Environment:** **H200 NVL**, Ubuntu, Python 3.12 venv on dedicated storage.

**Docs:** [README](https://github.com/namanadep/isaac-sim-pow/blob/main/README.md) · [GPU VM handoff](https://github.com/namanadep/isaac-sim-pow/blob/main/docs/ISAAC_SIM_GPU_VM_HANDOFF.md) · [WebRTC / UDP deep dive](https://github.com/namanadep/isaac-sim-pow/blob/main/docs/webrtc_udp_deep_dive.md)

---

## Related cross-links

- **Observability stack** (`gpu-obs-quickstart`) is **standalone**. It pairs naturally with **Isaac Sim** workloads on the same host when both checkouts exist; see each repo’s README for context.

---

## Maintaining this index

When I **add a new HPC-related repository**:

1. Add a row to the **Summary** table (keep it alphabetical or grouped by category—your choice).
2. Add a **subsection** under the right category (or create a new category, e.g. *Clusters*, *Containers*, *Benchmarks*).
3. Commit and push to this repository (`namanadep/namanadep`).

Optional: **pin** this repository on [your GitHub profile](https://github.com/namanadep) (up to six repos) so it stays visible beside your other work.

---

*Last updated: 2026-04-07*
