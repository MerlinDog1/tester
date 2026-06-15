# Active Project Portfolio

Updated: 2026-06-15
Audience: Teto, Yuji, and clawddad

This is a sanitized orientation document. It intentionally excludes credentials, private customer data, medical access details, API keys, and unpublished source code.

## Collaboration model

- GitHub-hosted work: Yuji may inspect, review, propose patches, or work through branches and pull requests.
- Local-only work: Teto provides bounded context, relevant snippets, patches, screenshots, test output, and applies/verifies changes locally.
- Every task should use a dedicated GitHub issue with a clear repository, objective, owner, acceptance criteria, and six-message default loop limit.

## Priority projects

### 1. Foundry and Vector Pro

High-precision engraving and manufacturing-ready vector workflow. The pipeline combines image generation, GPU upscaling, and vector tracing for laser/chemical etching. It includes V8 Pro tracing, Potrace for binary halftones, tiled tracing for extreme detail, and mosaic reconstruction for very large engravings.

- Status: active, core technical programme.
- Main local areas: `vector-tool/`, Vector Pro, Foundry tracing scripts, ComfyUI integration.
- Key risks: memory/path explosion on dense artwork, speckle/noise control, preserving fine detail while keeping SVG production-safe.
- Best Yuji contribution: algorithm review, isolated tracing fixes, test design, performance analysis, documentation.

### 2. Grayscale SVG Lab

Browser application that converts raster images into millimetre-accurate SVG using 25 production-oriented generators including halftone, dithering, stipple, TSP, Hilbert, mezzotint, contour, flow, spiral, hybrid etch, and Foundry V8 trace.

- Stack: Vite, React, SVG web worker, optional local Python/OpenCV/vtracer backend.
- Status: v1.4.0 production build; extensive browser and stress validation completed.
- Strengths: deterministic output, fabrication profiles, path caps, batch/ZIP/contact-sheet export, setup persistence, feature-floor and precision controls.
- Known limit: TSP is approximate; extreme density can still create very large SVGs.
- Best Yuji contribution: regression review, performance improvements, generator correctness, production geometry audits.

### 3. Plaques AI customer journey

Full guided plaque design application with portrait generation/tracing, inscription composition, proof controls, realistic mockups, and SVG/PDF production export.

- Main local app: `plaque-designer-customer-journey`.
- Related forks: internal tool, Express experiments, and Lovable/TanStack port.
- Current direction: fast internal proof creation with manual refinement, plaque-aware image generation, safe typography geometry, and faithful workshop exports.
- Important boundary: the live customer journey has separate forks; changes must target the named fork and must not clean or overwrite sibling working trees.
- Best Yuji contribution: review isolated export/layout bugs, UI flows, validation logic, and tests after Teto supplies scoped files/context.

### 4. Lovable Plaque Studio

Public-facing memorial sketch plaque site built around a simple offer: send a photo and wording, receive a free digital proof, and pay only after approval.

- Repo: `MerlinDog1/the-plaque-proof`.
- Current work: memorial positioning, equine/dog/cat vertical pages, responsive hero assets, simplified proof request form, live indicative order preview, package pricing and mounting rules.
- Product rule: photo-sketch products start at A5; public choices remain simple while internal costing stays hidden.
- Best Yuji contribution: UX review, responsive QA, form/data-flow review, accessibility, conversion-focused copy and implementation.

### 5. EtchMaster Pro / Plaques AI Lovable port

A TanStack Start/Lovable repository containing a port of the real AI portrait plaque designer rather than the older quote-desk prototype.

- Repo: `MerlinDog1/blank-canvas-project`.
- Includes guided journey, portrait generation, inscription layout, previews, export services, vector sketch tooling, and plaque-specific layout logic.
- Best Yuji contribution: portability review, dependency cleanup, build/lint fixes, parity checks against the source app.

### 6. Luxury Sign

Luxury Dullaghan.com web experience with iron/brass theme switching, cinematic scroll, and interactive metal visuals.

- Repo: `MerlinDog1/luxury-sign` (private).
- Stack: Next.js App Router, Tailwind, GSAP, Three.js/R3F, Lenis.
- Best Yuji contribution: frontend performance, motion/accessibility review, responsive polish, Three.js optimisation.

### 7. Laser2Etch

Industrial marketing project aimed at laser engraving businesses adding deeper chemical etching while retaining existing laser workflows.

- Public repo: `MerlinDog1/laser2etch-redesign`.
- Local outputs: one-page redesign plus full and compact email campaign packages.
- Current focus: dense viewport-fit desktop layout, industrial visual system, clear process/benefit communication, robust email rendering.
- Best Yuji contribution: copy/UX review, responsive QA, email client compatibility, performance and semantic HTML.

## Directory and lead systems

### 8. Signage and engraving directories

Data acquisition and verification programme for signage, engraving, plaque, laser, architectural and wayfinding companies.

- Main repositories include UK business/sign directory, UK wayfinding directory, UK architects directory, and North America/international laser directory.
- Recent emphasis: strict source-backed additions, direct company-site validation, duplicate control, and rejection of guessed/fabricated URLs.
- Critical quality rule: generated candidates are untrusted until independently validated against direct sources.
- Best Yuji contribution: validator design, deduplication, provenance schemas, review tooling, deterministic data tests.

## Local AI and operations

### 9. Qwen-Agent Local

Offline agent framework using Qwen models through Ollama on a local RTX 3060. Supports ReAct tool use, RAG, and local code/system tasks.

- Default proven model: Qwen 2.5 Coder 7B.
- Larger models are constrained by VRAM and cold-start latency.
- Best Yuji contribution: prompt/tool schemas, benchmark design, RAG evaluation, small-model reliability improvements.

### 10. Teto OS Dashboard

Firebase command centre for projects, agents, schedules, and machine telemetry.

- Status: v0.8 deployed.
- Best Yuji contribution: telemetry schema review, dashboard UX, alerting logic, and security review using sanitized configuration only.

### 11. Fin-Teto

Local financial research workflow using market/fundamental data to produce concise ticker briefings.

- Trigger: `/fin <ticker>`.
- Best Yuji contribution: calculation validation, source attribution, report structure, risk controls. It should not make autonomous trades.

### 12. Research portfolio

Ongoing industrial materials, architectural etching, medical knowledge, and AI/model research.

- Industrial themes: metal quality, corrosion risk, architectural finishes, elite fabrication benchmarks.
- AI themes: coding/reasoning model tracking and practical local/cloud capability tests.
- Medical/private family material is excluded from this bridge unless clawddad explicitly scopes a sanitized task.
- Best Yuji contribution: source verification, technical synthesis, reproducible research notes.

## Suggested first operating sequence

1. Confirm the GitHub bridge handshake.
2. Pick one bounded GitHub-hosted project for a trial collaboration.
3. Open one issue containing objective, relevant files, constraints, and acceptance tests.
4. Yuji reviews or proposes a patch; Teto handles local-only context and verification.
5. Record outcome and refine the protocol before broadening access.

## Initial recommendation

Use Grayscale SVG Lab or Lovable Plaque Studio as the first trial. Both have clear behaviour, testable UI/output, and useful work that can be bounded without exposing unrelated local data.