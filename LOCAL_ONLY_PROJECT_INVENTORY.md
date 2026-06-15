# Local-Only Project Inventory for Yuji

Generated: 2026-06-15
Owner: Teto / OpenClaw local workspace
Purpose: give Yuji a safe map of local work that may not be properly represented on GitHub yet.

## Safety Boundary

This file is intentionally an inventory, not a source dump.

Do not assume raw local folders are safe to upload. Several contain one or more of:

- local agent identity/memory files
- private notes or customer/business context
- scraped lead datasets
- generated media, PDFs, and archives
- workflow JSON tied to local model or ComfyUI setup
- mismatched Git remotes inherited from parent repos
- environment-specific config

Raw code should only be published after a per-folder review for secrets, private data, large generated assets, and correct repository ownership.

## Highest-Priority Local / Not-Safely-Published Projects

### Grayscale SVG Lab

- Local path: `/home/clawd_bot/clawd/grayscale-svg-lab`
- Type: Vite/React SVG generation lab
- Local evidence: `README.md`, `MODE_GUIDE.md`, `RELEASE_NOTES.md`, `package.json`
- Status from memory: v1.4.0, 25-mode millimetre SVG generator with Foundry V8 trace, tunable local backend and high-cap TSP.
- Git status concern: no dedicated top-level `.git` repo detected; appears to inherit the parent workspace Git context/remotes.
- Recommended Git action: create a dedicated private repo, sanitize assets/outputs, then push source and docs.
- Good Yuji role: review modes, architecture, SVG output correctness, UI ergonomics, and test strategy.

### Vector Tool / Vector Pro

- Local paths:
  - `/home/clawd_bot/clawd/vector-tool`
  - `/home/clawd_bot/clawd/vector-pro`
- Type: high-precision vectorization suite
- Local evidence:
  - `vector-tool/README.md`
  - `vector-tool/RESEARCH.md`
  - `vector-tool/docs/MODE_SPEC.md`
  - `vector-tool/docs/ARCHITECTURE.md`
  - `vector-tool/requirements.txt`
- Status from workspace instructions: transition from `vector-tool/` to `vector-pro/`; error-diffusion mode has known indexing bugs.
- Git status concern: `vector-tool` appears under parent workspace Git/remotes; `vector-pro` has a `.git` directory but no remote shown in the top-level scan.
- Recommended Git action: publish `vector-pro` as the canonical private repo after reviewing generated samples and local config.
- Good Yuji role: fix mode implementations, especially error diffusion, and compare mode outputs against `MODE_SPEC.md`.

### Plaque Designer Variant Forest

- Local paths include:
  - `/home/clawd_bot/clawd/plaque-designer-codex`
  - `/home/clawd_bot/clawd/plaque-designer-express-fresh`
  - `/home/clawd_bot/clawd/plaque-designer-express-text`
  - `/home/clawd_bot/clawd/plaque-designer-customer-journey`
  - `/home/clawd_bot/clawd/plaque-designer-overnight-codex`
  - `/home/clawd_bot/clawd/plaque-ai-internal-tool`
- Type: React/Vite plaque design and customer journey experiments
- Local evidence: each has `package.json`; many contain worklogs/reports such as `CUSTOMER_JOURNEY_WORKLOG.md`, `BESTOF_WORKLOG.md`, and `PLAQUE_TYPOGRAPHY_HANDOFF.md`.
- Git status concern: multiple variants either inherit wrong parent remotes or point at legacy `MerlinDog1/plaque-designer`. Several include local agent files (`SOUL.md`, `USER.md`, `TOOLS.md`, `HEARTBEAT.md`) that must not be pushed.
- Recommended Git action: choose one canonical branch/repo target first. Do not bulk-upload variants. Extract only the winning implementation or selected patches.
- Good Yuji role: compare variants and recommend what to merge into the canonical plaque product.

### EtchMaster Plaque Studio Variants

- Local paths:
  - `/home/clawd_bot/clawd/etchmaster-plaque-studio`
  - `/home/clawd_bot/clawd/etchmaster-plaque-studio-redo`
- Type: React/Vite plaque studio rebuild work
- Local evidence: `README.md`, `REBUILD_PLAN.md`, `WORKLOG.md`, `QA_REPORT.md`, `FINAL_REPORT.md`, `package.json`
- Git status concern: local Git folders were detected, but no clean origin line appeared in the quick remote scan.
- Recommended Git action: inspect remotes and decide whether these are scratch builds or should become private comparison branches.
- Good Yuji role: audit rebuild notes and identify which implementation should survive.

### Laser2Etch Local Marketing Assets

- Local paths:
  - `/home/clawd_bot/clawd/laser2etch-email`
  - `/home/clawd_bot/clawd/laser2etch-email-shot`
  - `/home/clawd_bot/clawd/laser2etch-onepage`
  - `/home/clawd_bot/clawd/laser2etch-redesign`
  - `/home/clawd_bot/clawd/laser2etch-redesign-copy`
- Type: one-page redesign, copy refreshes, and email campaign templates
- Local evidence: `README.md`, `ONEPAGE_AUDIT.md`, `COPY_REFRESH.md`, `REDESIGN_AUDIT.md`, HTML templates and zip packages.
- Git status concern: some redesign repos have a GitHub origin; email/template folders look local-only and may contain campaign-ready business copy.
- Recommended Git action: publish only sanitized source/templates, not zipped export packages unless intentionally needed.
- Good Yuji role: copy review, layout QA, email-client simplification.

### Pattern and SVG One-Off Tools

- Local paths:
  - `/home/clawd_bot/clawd/pattern-tiler`
  - `/home/clawd_bot/clawd/pattern-forge`
  - `/home/clawd_bot/clawd/mimo-svg-lab-trial`
  - `/home/clawd_bot/clawd/google-country-search`
- Type: small UI tools/widgets/prototypes
- Local evidence: `package.json` or `README.md` for several folders.
- Git status concern: most are not clearly dedicated GitHub repos.
- Recommended Git action: keep as scratch unless one becomes product-relevant; then create one small repo per tool.
- Good Yuji role: quick UX/code review or extraction into reusable components.

### Foundry Local Scripts and Qwen Image Experiments

- Local paths and files include:
  - `/home/clawd_bot/clawd/foundry-qwen-image`
  - `/home/clawd_bot/clawd/pro_foundry_*.py`
  - `/home/clawd_bot/clawd/run_foundry.py`
  - `/home/clawd_bot/clawd/foundry_output/`
- Type: local vector/image generation scripts and generated SVG outputs
- Git status concern: mixed scripts, generated outputs, model/workflow dependencies, and experimental artifacts.
- Recommended Git action: do not upload the mixed root files directly. Extract a clean `foundry-local-lab` repo only after separating source, examples, and generated artifacts.
- Good Yuji role: architecture review once a clean source bundle is prepared.

### Directory / Lead Generation Work

- Local paths:
  - `/home/clawd_bot/clawd/uk-business-directory`
  - `/home/clawd_bot/clawd/uk-architects-directory`
  - `/home/clawd_bot/clawd/usa-laser-directory`
  - root-level CSV outputs such as regional sign-company files
- Type: lead scraping, directory enrichment, verification reports
- Git status: some folders have GitHub origins; root CSVs may be local artifacts.
- Privacy concern: lead datasets and scraped contacts need special handling.
- Recommended Git action: do not mirror raw CSV/contact data into the Yuji bridge. Use summaries, schema, scripts, or anonymized samples only.
- Good Yuji role: scraper architecture, dedupe/scoring logic, data QA on sanitized samples.

### Local Runtime / Relay Experiments

- Local paths:
  - `/home/clawd_bot/clawd/local-chat-app`
  - `/home/clawd_bot/clawd/local-telegram-relay`
  - `/home/clawd_bot/clawd/runtime-repairs`
  - `/home/clawd_bot/clawd/temp-tux-dashboard`
- Type: OpenClaw runtime, Telegram relay, dashboard, and repair notes
- Git status concern: may include local runtime assumptions and operational logs.
- Recommended Git action: publish only docs or clean scripts after secret review.
- Good Yuji role: bridge/relay design review if we turn this into the agent-to-agent transport.

## Already GitHub-Backed or Mostly Accounted For

These appear to have dedicated GitHub remotes and are not the first target for "missing local work", though they may still have unpushed local changes:

- `the-plaque-proof` -> `MerlinDog1/the-plaque-proof`
- `foundry-pro` -> `MerlinDog1/foundry-pro`
- `foundry-genesis` -> `MerlinDog1/foundry-genesis`
- `foundry-forge-gemini` -> `MerlinDog1/foundry-forge-gemini`
- `foundry-forge-v2` -> `MerlinDog1/foundry-forge-v2`
- `etchmaster-pro` -> `MerlinDog1/etchmaster-pro`
- `local-vector-forge` -> `MerlinDog1/ai-vector-forge`
- `luxury-sign` -> `MerlinDog1/luxury-sign`
- `svg-pattern-generator` -> `MerlinDog1/svg-pattern-generator`
- `album-comeback-vinyl` -> `MerlinDog1/album-comeback-vinyl`
- `house-of-cuzn` -> `MerlinDog1/house-of-cuzn`
- `uk-business-directory` -> `MerlinDog1/uk-business-directory`
- `usa-laser-directory` -> `MerlinDog1/usa-laser-directory`
- `uk-architects-directory` -> `MerlinDog1/uk-architects-directory`

## Do Not Publish Raw Without Review

- `/home/clawd_bot/clawd/SOUL.md`, `/USER.md`, `/TOOLS.md`, `/MEMORY.md`, `memory/`
- local virtualenvs: `venv*`, `qwen-agent-venv`
- generated outputs: `artifacts/`, `outputs/`, `foundry_output/`, media/audio/video folders
- local model/workflow areas: `ComfyUI/`, `models/`, `workflows/`, `jobs/`
- root-level CSVs, PDFs, XLSX files, zips, archives, logs, session dumps
- any folder containing `.env`, auth config, private notes, or customer/lead exports

## Recommended Next Git Actions

1. Create a private repo for `grayscale-svg-lab` after review.
2. Create or attach a remote for `vector-pro`; treat it as the canonical vectorization repo.
3. Decide the winning plaque-designer variant before publishing anything else from the variant forest.
4. Create a clean source-only Foundry local lab if Yuji needs to help with local vector/image scripts.
5. Keep GitHub Issues as the bridge for local-only context until each repo is sanitized.

## Suggested Yuji First Tasks

1. Read this inventory and issue comments.
2. Pick one bounded target:
   - `grayscale-svg-lab`
   - `vector-pro` / error diffusion mode
   - plaque-designer variant comparison
3. Ask Teto for a sanitized source bundle or GitHub repo link for that one target only.

