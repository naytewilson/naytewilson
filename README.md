# Nayte — Native systems, Apple Silicon & autonomous agent research

Independent research into **Apple Neural Engine execution, Core ML compilation, graph placement, and numerical correctness**. I work primarily with native Swift, MIL specifications, ML packages, and controlled measurement on Apple Silicon.

**Research home:** [MacBrains Labs](https://macbrainslabs.org/) · **Methods:** [Experimental approach](https://macbrainslabs.org/methods/) · **Contact:** [research@macbrainslabs.org](mailto:research@macbrainslabs.org)

**ORCID:** [0009-0003-4026-8212](https://orcid.org/0009-0003-4026-8212) · **Citable records:** [ANE Research Records, all versions, DOI 10.5281/zenodo.23798036](https://doi.org/10.5281/zenodo.23798036) · **Organization:** [github.com/macbrainslabs](https://github.com/macbrainslabs)

## Published research records

Each record is a tagged release of [macbrainslabs/ane-research-records](https://github.com/macbrainslabs/ane-research-records) with its own Zenodo version DOI. Current verification status for every record is on [Publications](https://macbrainslabs.org/publications/).

| Version | Record | Scope as published | DOI |
| --- | --- | --- | --- |
| v0.3.0 · Nov 2026 | [ANERECore cross-repo MIL parity: tap, steer and functionWide](https://macbrainslabs.org/research/records/ane-record-b8f78a146608021d974dcdec/) | Same chip, single device. MIL text byte equality on one Qwen fixture; 10 of 10 counted runs pass across two clean-room arms. No Core ML compile, ANE execution or numerics claimed | [10.5281/zenodo.24034510](https://doi.org/10.5281/zenodo.24034510) |
| v0.2.0 · Nov 2026 | [LFM3-1.7B layer-14 diagnostic under Core ML `cpuAndNeuralEngine`](https://macbrainslabs.org/research/records/ane-record-c188def1e88a0d94018dfe99/) | Same chip, single device (A18 Pro). ANE execution inferred from compute-plan placement; 8 executions disclosed, 5 counted | [10.5281/zenodo.23905811](https://doi.org/10.5281/zenodo.23905811) |
| v0.1.0 · Oct 2026 | [Public measurement summaries](https://github.com/macbrainslabs/ane-research-records/releases/tag/v0.1.0) | Baseline archive of derived summary tables, not raw fixtures | [10.5281/zenodo.23798037](https://doi.org/10.5281/zenodo.23798037) |

Same-chip reruns are reported as repeatability, never as cross-device replication. No record claims novelty, and an archived DOI is not peer review.

## ANVIL — Agent operating system

<a href="https://github.com/naytewilson/anvil-showcase"><img src="https://raw.githubusercontent.com/naytewilson/anvil-showcase/main/assets/anvil-banner.svg" width="100%" alt="ANVIL — native-first autonomous agent operating system" /></a>

**ANVIL** (**A**gent **N**etwork for **V**erification, **I**ntegration, and **L**ineage) is my native-first systems research project for **accountable autonomous AI agents**. It addresses cross-session identity, distributed work ownership, heterogeneous execution, evidence provenance, recoverability, and the distinction between a passing source test and proven runtime behavior.

The architecture draws on **Swift, PostgreSQL, macOS / Apple Silicon, Linux, and independent verification**. ANVIL is being developed privately; the public project repository documents its engineering objectives and conceptual system boundaries without releasing its implementation or internal operating state. A Swift-native, deny-by-default agent sandbox is implemented.

### Research publication pipeline

The records above come out of a review and publication pipeline that runs on ANVIL infrastructure. It is in use: v0.2.0 and v0.3.0 were each released only after a final INCLUDE on their exact package hash. A finding moves through it as one hash-identified package that is never edited after submission:

1. **Frozen run profiles.** A profile is committed to git and hashed before its first counted run. Every execution goes into an append-only per-device log and is disclosed, passed or failed.
2. **Independent review.** An evidence reviewer and a skeptical reviewer (pinned AI models) and a deterministic, versioned policy gate check the exact bundle. A split verdict is a hold.
3. **Final review.** A separate reviewer returns INCLUDE or HOLD for the exact package hash, against a versioned checklist and a cumulative adversarial probe suite. A held hash is never republished.
4. **Verified release.** After INCLUDE, a GitHub release, a new Zenodo version and a site record page are published, then checked live. A daily drift check compares every public surface with the records index.

Still manual: findings are staged by hand, and independent recompute and prior-art checks are not automated. Neural Engine execution remains INFERRED from compute-plan placement; no record has a hardware execution trace. Details: [review](https://macbrainslabs.org/methods/#review) · [publication](https://macbrainslabs.org/methods/#publication) · [run accounting](https://macbrainslabs.org/methods/#runs).

**[Technical overview](https://github.com/naytewilson/anvil-showcase)** · [Evidence pipeline](https://github.com/naytewilson/anvil-showcase/blob/main/docs/EVIDENCE_PIPELINE.md) · [Architecture](https://github.com/naytewilson/anvil-showcase/blob/main/docs/ARCHITECTURE.md) · [Verification model](https://github.com/naytewilson/anvil-showcase/blob/main/docs/VERIFICATION.md)

## Selected measurements

| Case | Reported result | What it establishes |
| --- | --- | --- |
| [Qwen2.5-1.5B, 28-layer LUT4 graph](https://macbrainslabs.org/notes/qwen-lut4/) | 2,090 ANE-assigned / 79 CPU-assigned operations (June 2026 build) | A bounded Core ML placement result; not a claim of full chip residency |
| [LFM sealed S2 graph](https://macbrainslabs.org/notes/lfm-parity/) | 743 / 743 operations ANE-assigned | Placement for the specified production graph; diagnostic builds are separately evaluated |
| [Qwen batch decode sweep](https://macbrainslabs.org/notes/decode-regimes/) | 45.4 to 125.8 aggregate tokens/s (B=1 to B=8) | A shape-dependent throughput comparison on single-function probe artifacts; output quality was not validated |

Measurements are tied to specific configurations and methods. **MLComputePlan assignment is not equivalent to direct silicon tracing.** Failed hypotheses and non-ANE fallbacks remain part of the research record.

## Public code

- [qwen2.5-ane](https://github.com/naytewilson/qwen2.5-ane): Qwen2.5-1.5B-Instruct on the Apple Neural Engine, a Swift server with an OpenAI-compatible API, batch-64 prefill and LUT4 Core ML. Model on [Hugging Face](https://huggingface.co/NayteThaGreat/Qwen2.5-1.5B-Instruct-ANE).

## Working areas

- Typed MIL emission and native MLPackage generation
- Quantized-weight inference and stateful decode interfaces
- Numerical parity: relative L2, cosine similarity, absolute error, and finite-value gates
- Reproducibility through fixture provenance and exact graph/shape specification

[Research index](https://macbrainslabs.org/research/) · [Read the methodology](https://macbrainslabs.org/methods/) · [Technical correspondence](https://macbrainslabs.org/contact/)

<sub>MacBrains Labs is an independent research identity, not a claim of corporate or university affiliation. Not affiliated with Apple.</sub>
