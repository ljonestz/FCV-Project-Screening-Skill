# Contributing to FCV Project Screener

Thank you for your interest in improving this skill. Contributions are welcome from anyone with expertise in FCV analysis, World Bank operations, or Claude skill development.

---

## Types of Contributions

### Analytical Framework
- Corrections or updates to FCV guidance in `fcv-guidance.md`
- Refinements to the six OST recommendation assessments
- Updates to reflect new WBG FCV Strategy guidance or operational instruments
- Improved Do-No-Harm checklist items

### Workflow & Prompts
- Improvements to stage prompts in `stage-prompts.md`
- Better citation handling or source-tier logic
- Enhancements to the Explorer Mode deep-dive structure
- Improved document-type adaptation logic

### Documentation
- Clarifications to the README
- Example outputs or case studies (anonymised)
- Translations of the README into other languages

### Bug Reports
- If a stage produces incorrect or misleading outputs, please open an issue with the specific prompt, document type (PCN/PAD/etc.), and observed vs. expected behaviour.

---

## How to Contribute

1. **Fork** this repository and create a feature branch from `main`:
   ```bash
   git checkout -b feature/improve-stage2-prompts
   ```

2. **Make your changes** inside the skill archive. To edit the skill contents:
   ```bash
   # Unzip the skill
   unzip fcv-project-screener.skill -d fcv-project-screener/

   # Edit the relevant markdown file
   # e.g. fcv-project-screener/references/fcv-guidance.md

   # Repackage the skill
   cd fcv-project-screener && zip -r ../fcv-project-screener.skill . && cd ..
   ```

3. **Test your changes** by installing the updated skill locally and running through at least one full stage cycle with a sample document.

4. **Commit** with a clear message describing what changed and why:
   ```bash
   git commit -m "Update Stage 2 prompt to clarify S+R overlap rules"
   ```

5. **Open a Pull Request** against the `main` branch with:
   - A summary of what changed
   - The rationale (e.g. reference to WBG guidance, observed output issue)
   - Any relevant testing notes

---

## Contribution Guidelines

- **Ground changes in evidence** — Analytical changes should reference WBG FCV Strategy documentation, the OST manual, or other authoritative sources.
- **Preserve the anti-hallucination design** — Do not weaken citation tier rules or source-grounding requirements.
- **Keep the workflow discipline** — Do not modify stage progression logic to auto-advance without user approval.
- **Respect the S/R/S+R distinction** — Changes to sensitivity/responsiveness tagging must maintain the strict [S+R] rules to avoid inflation.
- **Keep prompts actionable** — Stage outputs should remain TTL-friendly: specific, consultative in tone, and grounded in WBG instruments.

---

## Reporting Issues

Please open a GitHub issue for:
- Incorrect FCV guidance or outdated references
- Prompt outputs that are off-topic, hallucinated, or analytically wrong
- Installation or compatibility problems

When reporting a prompt issue, please include:
- Document type (PCN, PID, PAD, etc.)
- Stage where the issue occurred
- The trigger phrase used
- The problematic output (paraphrased or anonymised if needed)

---

## Code of Conduct

Be respectful and constructive. This skill exists to support better project outcomes in fragile contexts — contributions should reflect that purpose.
