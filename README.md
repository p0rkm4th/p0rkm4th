# Scotty Greer — HckrSlsh

**IT Systems Engineer (ESa, Nashville) · Independent IT consultant as [HckrSlsh](https://hckrslsh.com) · Local-first AI builder**

I build and benchmark self-hosted AI that runs on hardware you own — no cloud
inference, no hosted fallback. My homelab, **HADES**, is a private seven-node
local-AI installation built around Proxmox, GPU inference nodes, and a LiteLLM
gateway. My public work is the evidence trail for that lab: benchmark methods,
sanitized results, and the tools that run on it.

## HADES Herd — the benchmark portfolio

[hades-herd](https://github.com/p0rkm4th/hades-herd) is a dependency-free
client that discovers Ollama models across the Herd fleet and launches Codex
CLI against local models only — it never pulls a model automatically and never
falls back to hosted inference.

The fleet is evaluated, not vibes-checked:

- **Method:** pass@1 on real coding tasks, with controls, published in
  [benchmarks/](https://github.com/p0rkm4th/hades-herd/tree/main/benchmarks) —
  agent completion is reported separately from patches that needed human
  correction.
- **Daily-driver gate:** 20 varied tasks at 85% pass@1. **No current profile
  meets it, and the repo says so.** That honesty is the point of the exercise.

| Profile | Hardware class | What the evidence shows |
|---|---|---|
| MiMo-V2.6 9B Q4_K_M | Single 12 GB GPU | One task (HTTPie #1960) completed and independently verified — 122 tests passed; other tasks timed out. Task-qualified, not general-purpose. |
| Qwen3.8 27B Q4 | Dual 10 GB GPUs | Repeated registry / multi-file passes at 8K context; several 16K agent tasks incomplete. Experimental. |
| Qwen3.6 35B | Multi-GPU legacy node | Configured fleet default (27.65–37.60 tok/s class, 65,536 effective context in earlier harness work); not yet qualified as a dependable coding agent. |

Full detail: [model matrix](https://github.com/p0rkm4th/hades-herd/blob/main/docs/MODEL_MATRIX.md) ·
[status](https://github.com/p0rkm4th/hades-herd/blob/main/docs/STATUS.md) ·
[reliability baseline](https://github.com/p0rkm4th/hades-herd/tree/main/benchmarks)

## Projects

| Repo | What it is |
|---|---|
| [hades-herd](https://github.com/p0rkm4th/hades-herd) | Codex client for a local Ollama fleet + the pass@1 benchmark portfolio above. CI green on Python 3.10–3.14. |
| [hades](https://github.com/p0rkm4th/hades) | HADES v2 — the local LLM stack the fleet runs on. Contract-tested, CI green. |
| [aegis-dev](https://github.com/p0rkm4th/aegis-dev) | AEGIS — local-first personal AI assistant: tasks, homelab, finance, and research on your own hardware. No cloud, no subscription. |
| [hckrslsh-fieldos](https://github.com/p0rkm4th/hckrslsh-fieldos) | FieldOS — offline field computer (Ubuntu + local AI + reference packs) for work where the network isn't trusted or isn't there. Apache-2.0. |
| [bitburner-ai-os](https://github.com/p0rkm4th/bitburner-ai-os) | A local AI that plays Bitburner through a visible browser + legitimate Netscript APIs, localhost-only — an agent-harness testbed. |
| [herdcode](https://github.com/p0rkm4th/herdcode) | Android cockpit for Codex + a local Ollama herd: streaming chat and agent runs over Tailscale, token-auth bridge on the host. |
| [styxworks](https://github.com/p0rkm4th/styxworks) | STYXWORKS — a Greek-underworld idle game. Single-file HTML, zero external references, fully offline, plus a zero-permission Android shell. |
| [hades-v3](https://github.com/p0rkm4th/hades-v3) | Bounded harness-comparison experiment. Frozen — no candidate qualified, and the repo documents why. |

Day job context: endpoint/device lifecycle, Intune/SCCM, Active Directory,
M365, and automation in an enterprise Windows/macOS/Linux environment.
Certifications: CompTIA A+, Network+, Security+, CIOS, CSIS.

## Hardware testing & sponsorship

I test hardware the way I'd want it tested before I spent my own money on it,
and I publish the data either way.

**What I can credibly test:**
- Unified-memory AI mini-PCs (Strix Halo, GB10) and inference nodes — as a
  single node *against* a distributed seven-node fleet, same models, same
  pass@1 method
- Edge AI accelerators — household vision workloads, FPS/watt, latency,
  model-conversion experience
- Storage & networking for inference fleets — model-load time, 10GbE
  throughput, sustained-write thermals, VLAN/Tailscale behaviour

**How I measure:** tokens/second and pass@1 (not demo prompts), watts at the
wall, thermals and noise under sustained load, and a multi-day soak in a real
deployment — not an afternoon on a test bench.

**What you get:** a public write-up and benchmark data with raw numbers,
photos, setup pain, and honest cons, delivered on the date agreed in writing
before anything ships. Gifted or loaned hardware is disclosed in every
publication (FTC). I never promise a positive review — I promise a thorough,
honest, on-time one. Loaner vs. keep is confirmed in writing before shipping.

**Contact:** via [hckrslsh.com](https://hckrslsh.com) — Scotty from HckrSlsh.

---

*Machines in the lab are named for the Greek underworld. The cat is Lyxa.
She supervises.*
