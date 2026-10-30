# Nayte — Apple Silicon / Neural Engine systems research

Independent research into **Apple Neural Engine execution, Core ML compilation, graph placement, and numerical correctness**. I work primarily with native Swift, MIL specifications, ML packages, and controlled measurement on Apple Silicon.

**Research home:** [MacBrains Labs](https://macbrainslabs.org/) · **Methods:** [Experimental approach](https://macbrainslabs.org/methods/) · **Contact:** [research@macbrainslabs.org](mailto:research@macbrainslabs.org)

**ORCID:** [0009-0003-4026-8212](https://orcid.org/0009-0003-4026-8212) · **Citable data:** [ANE Research Records v0.1.0, DOI 10.5281/zenodo.23798037](https://doi.org/10.5281/zenodo.23798037) · **Organization:** [github.com/macbrainslabs](https://github.com/macbrainslabs)

## Selected measurements

| Case | Reported result | What it establishes |
| --- | --- | --- |
| [Qwen2.5-1.5B, 28-layer LUT4 graph](https://macbrainslabs.org/notes/qwen-lut4/) | 2,090 ANE-assigned / 79 CPU-assigned operations | A bounded Core ML placement result; not a claim of full chip residency |
| [LFM sealed S2 graph](https://macbrainslabs.org/notes/lfm-parity/) | 743 / 743 operations ANE-assigned | Placement for the specified production graph; diagnostic builds are separately evaluated |
| [Qwen batch decode sweep](https://macbrainslabs.org/notes/decode-regimes/) | 45.4 to 125.8 aggregate tokens/s (B=1 to B=8) | A shape-dependent throughput comparison on single-function probe artifacts; output quality was not validated |

Measurements are tied to specific configurations and methods. **MLComputePlan assignment is not equivalent to direct silicon tracing.** Failed hypotheses and non-ANE fallbacks remain part of the research record.

## Working areas

- Typed MIL emission and native MLPackage generation
- Quantized-weight inference and stateful decode interfaces
- Numerical parity: relative L2, cosine similarity, absolute error, and finite-value gates
- Reproducibility through fixture provenance and exact graph/shape specification

[Research index](https://macbrainslabs.org/research/) · [Read the methodology](https://macbrainslabs.org/methods/) · [Technical correspondence](https://macbrainslabs.org/contact/)

<sub>MacBrains Labs is an independent research identity, not a claim of corporate or university affiliation. Not affiliated with Apple.</sub>
