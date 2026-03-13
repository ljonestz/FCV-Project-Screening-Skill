# FCV Project Screener

A Claude Code skill for conducting systematic **FCV (Fragility, Conflict, and Violence) sensitivity and responsiveness screening** of World Bank Group project documents.

Designed for World Bank **Task Team Leaders (TTLs)** preparing or reviewing PCNs, PIDs, PADs, Additional Financing, Restructuring Papers, and ISRs in FCV-affected contexts.

---

## What It Does

This skill guides Claude through a structured 4-stage analytical workflow, grounding all outputs in uploaded project documents and real-time web research.

| Stage | Name | Output |
|-------|------|--------|
| 1 | **Identify FCV Risks** | FCV risks extracted from the project document + wider FCV context from web research |
| 2 | **FCV-Sensitivity Screening** | Assessment of 6 OST recommendations with [S], [R], [S+R] tags and a Summary Assessment Table |
| 3 | **Identifying Project Gaps** | Do-No-Harm checklist, gap analysis, and mitigation measures |
| 4 | **Recommendations Note** | TTL-ready memo with Strategic Priorities, FCV ratings, and action guidance |

After Stage 4, an optional **Explorer Mode** is available — triggered by `Explore Priority [Number]` — for deep-dive implementation guidance with PAD/Operations Manual language.

---

## Installation

### Prerequisites

- [Claude Code](https://claude.ai/code) (the CLI for Claude)
- A Claude account with web search access (required for Stage 1 Part B)

### Install the Skill

```bash
# Clone this repository
git clone https://github.com/your-org/FCV-Project-Screening-Skill.git

# Install the skill into Claude Code
claude skill install FCV-Project-Screening-Skill/fcv-project-screener.skill
```

Or install directly from the repository URL:

```bash
claude skill install https://github.com/your-org/FCV-Project-Screening-Skill/raw/main/fcv-project-screener.skill
```

---

## Usage

### Activate the Skill

Upload a WBG project document (PCN, PID, PAD, AF, Restructuring Paper, or ISR) to your Claude Code session, then use any of the following trigger phrases:

- `"Screen this project for FCV"`
- `"Run an FCV analysis"`
- `"Assess FCV sensitivity"`
- `"Generate FCV recommendations"`
- `"Produce a TTL support note"`
- `"Check this PAD for conflict risks"`

### Workflow

The skill enforces a **sequential workflow** — you must approve each stage before the next begins:

```
Upload document
     ↓
Stage 1: FCV Risk Identification  →  [Approve to continue]
     ↓
Stage 2: FCV-Sensitivity Screening  →  [Approve to continue]
     ↓
Stage 3: Gap Analysis  →  [Approve to continue]
     ↓
Stage 4: Recommendations Note
     ↓
(Optional) Explorer Mode: "Explore Priority 1"
```

### Example Session

```
User: Screen this project for FCV [uploads PAD]

Claude: [Stage 1] I've identified the following FCV risks from the project document...
        [Part A: Document-based risks]
        [Part B: Wider FCV context from web research]
        Ready to proceed to Stage 2 — FCV-Sensitivity Screening?

User: Yes, proceed.

Claude: [Stage 2] FCV-Sensitivity Screening against 6 OST Recommendations...
        [Summary Assessment Table with S/R/S+R tags]
        Ready to proceed to Stage 3?

... and so on through to the Recommendations Note.
```

---

## Key Features

- **Evidence-grounded analysis** — All findings are cited to uploaded documents (Tier 1), named web sources (Tier 2), or named organisations (Tier 3). No fabricated citations.
- **Document-type adaptation** — Adjusts analytical depth for PCN, PID, PAD, AF, Restructuring, and ISR document types.
- **Sensitivity vs. Responsiveness distinction** — Carefully distinguishes [S] (harm avoidance/adaptation) from [R] (directly addressing fragility drivers) and applies strict rules for [S+R] overlaps.
- **Operational pragmatism** — References real WBG instruments (CERC, TPM, GEMS, HEIS, DLIs, GRM) with consultative, actionable language.
- **AI transparency** — Stage 4 output is prepended with a disclaimer confirming this is supplementary analytical input, not a substitute for expert review.
- **Do-No-Harm checklist** — Stage 3 includes a systematic harm-avoidance assessment.

---

## FCV Framework Overview

The skill is grounded in the WBG FCV Strategy and the Operational Sensitivity Toolkit (OST). It assesses projects across **six FCV dimensions**:

1. Institutional Legitimacy
2. Inclusion
3. Social Cohesion
4. Security
5. Economic Livelihoods
6. Resilience

And evaluates them against the **six OST recommendations** for FCV-sensitive project design.

---

## Limitations

- **Requires document upload** — The skill cannot work from text descriptions alone; actual project documents must be uploaded.
- **Web search dependency** — Stage 1 Part B draws on real-time web research. Results may vary based on available sources.
- **Not a substitute for expert review** — Outputs are analytical inputs to support TTL judgment, not authoritative FCV assessments.
- **WBG-specific** — The framework, terminology, and instruments are specific to World Bank Group operations.

---

## Repository Structure

```
FCV-Project-Screening-Skill/
├── fcv-project-screener.skill   # The installable skill (ZIP archive)
│   ├── SKILL.md                 # Workflow framework and orchestration logic
│   └── references/
│       ├── fcv-guidance.md      # Analytical framework (44KB)
│       └── stage-prompts.md     # Detailed stage prompts (24KB)
├── README.md                    # This file
├── CONTRIBUTING.md              # How to contribute
└── LICENSE                      # MIT License
```

---

## Contributing

Contributions are welcome. Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

## Disclaimer

This skill is an AI-assisted analytical tool. All outputs should be critically reviewed by qualified professionals. It does not constitute official World Bank Group guidance or policy.
