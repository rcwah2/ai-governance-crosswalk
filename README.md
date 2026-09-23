# AI Governance Crosswalk: Practical Implementation Guide

A practical guide for organizations that need to operationalize multiple AI governance frameworks simultaneously. Focuses on what NIST and ISO don't provide: how to actually implement both frameworks together in practice.

## Why This Exists (And What It Is Not)

NIST already publishes an official crosswalk mapping NIST AI RMF functions to ISO/IEC 42001 clauses ([NIST AIRC](https://airc.nist.gov/airmf-resources/crosswalks/)). This repository does NOT duplicate that crosswalk.

Instead, this guide answers the question that comes after you've read the crosswalk: "Now what do I actually do?" It provides practical implementation guidance for organizations adopting both frameworks — what artifacts to create, what processes to establish, and how to avoid duplicating effort across frameworks.

## The Relationship Between the Frameworks

| Dimension | NIST AI RMF | ISO/IEC 42001 |
|---|---|---|
| Type | Voluntary risk management framework | Certifiable management system standard |
| Purpose | Identify and treat risks of specific AI systems | Organizational governance of AI across the lifecycle |
| Structure | 4 functions: Govern, Map, Measure, Manage | PDCA cycle with Annex A controls (39 controls across 9 areas) |
| Certification | None (self-assessment) | Yes (third-party audit, two-stage) |
| Origin | United States (NIST) | International (ISO/IEC) |
| Focus | Risk of individual systems | Organizational management system |

**Key insight:** NIST is the risk logic; ISO 42001 is the management system. They are complementary, not competing. NIST tells you what risks to look for; ISO 42001 tells you how to organize yourself to manage them systematically and auditably.

Source: [IA Governance](https://iagovernance.com/en/blog/iso-42001-vs-nist-ai-rmf/), [Acer Innovation](https://www.acerinnovation.com/nist-ai-rmf-iso-iec-42001-mapping)

## How They Map (High-Level)

NIST publishes an official crosswalk. The mapping works as follows:

| NIST AI RMF Function | ISO/IEC 42001 Home | What Sits There |
|---|---|---|
| GOVERN | Clauses 4-5 + Annex A.2/A.3 | AI policy, roles, responsibilities, oversight |
| MAP | Clause 6.1 + Annex A.4/A.5 | Scope, intended use, stakeholders, risk identification |
| MEASURE | Clause 6.1.2 + Clause 9 + Annex A.6 | Risk quantification, testing, performance monitoring |
| MANAGE | Clause 6.1.3 + Clauses 8, 10 + Annex A.8/A.10 | Risk treatment, operational controls, supplier management, improvement |

Source: [TCSA](https://www.tcsa.in/learn/iso-42001-vs-nist-ai-rmf), [Modulos](https://docs.modulos.ai/frameworks/comparison/iso-42001-vs-nist-ai-rmf)

**Important:** Only 7 of 45 requirement-level mappings are "strong" (completing one substantially satisfies the other). The other 38 are "partial" — work on one contributes evidence but does not satisfy the other. ([Shieldra](https://www.shieldra.ai/compare/nist-ai-rmf-vs-iso-42001))

## Practical Implementation Guide

### Step 1: Start with ISO 42001 as the Backbone

ISO 42001 is certifiable and provides the organizational structure. Use it as your management system backbone, then overlay NIST AI RMF activities within each clause area.

- Establish AI policy (ISO 42001 Clause 5)
- Define AI roles and responsibilities (Clause 5.3)
- Determine scope of the AIMS (Clause 4.3)
- Establish risk assessment process (Clause 6.1)

### Step 2: Overlay NIST AI RMF Risk Activities

Within the ISO 42001 management system, implement NIST AI RMF's risk functions:

- **GOVERN** → Establish governance structures (ISO 42001 Clauses 4-5, Annex A.2/A.3)
- **MAP** → Conduct AI system risk assessments (ISO 42001 Clause 6.1.4, Annex A.4/A.5)
- **MEASURE** → Implement testing and monitoring (ISO 42001 Clause 6.1.2, Clause 9, Annex A.6)
- **MANAGE** → Apply risk treatments and controls (ISO 42001 Clause 6.1.3, Clauses 8, 10, Annex A.8/A.10)

### Step 3: Create Shared Artifacts

Avoid duplicating effort by creating artifacts that satisfy both frameworks:

| Artifact | NIST AI RMF Function | ISO 42001 Clause | Template |
|---|---|---|---|
| AI system inventory | GOVERN (GOVERN 1.6), MAP | Clause 4.3, Annex A.4 | [ai-system-inventory-template](https://github.com/rcwah2/ai-system-inventory-template) |
| AI risk assessment | MAP, MEASURE | Clause 6.1, Annex A.4/A.5 | Create within your risk register |
| Vendor due diligence | GOVERN, MANAGE | Annex A.10 | [ai-vendor-due-diligence-template](https://github.com/rcwah2/ai-vendor-due-diligence-template) |
| Impact assessment | MAP | Annex A.5 | Document within system inventory |
| Incident response plan | MANAGE | Annex A.8.4 | Part of vendor governance pack |
| Statement of Applicability | GOVERN | Clause 6.1.3 | ISO 42001 requirement |
| AI policy | GOVERN | Clause 5.2 | ISO 42001 requirement |

### Step 4: Map Evidence to Both Frameworks

When you produce evidence for one framework, tag it for the other:

- A vendor assessment satisfies NIST AI RMF MANAGE (third-party risk) AND ISO 42001 Annex A.10 (suppliers)
- A bias test satisfies NIST AI RMF MEASURE AND ISO 42001 Annex A.6.2.4 (AI system verification and validation)
- An incident response plan satisfies NIST AI RMF MANAGE AND ISO 42001 Annex A.8.4

### Step 5: Align Review Cadences

| Activity | NIST AI RMF Cadence | ISO 42001 Cadence |
|---|---|---|
| AI system inventory review | As systems are added/changed | Clause 4.3, Annex A.4 — ongoing |
| Risk assessment | Annual or upon material change | Clause 6.1 — annual + on change |
| Performance monitoring | Continuous | Clause 9 — ongoing |
| Internal audit | Not required | Clause 9.2 — planned intervals |
| Management review | Not required | Clause 9.3 — planned intervals |
| Supplier reassessment | Annual or on material change | Annex A.10 — ongoing |

## Frameworks Covered

| Framework | Type | Scope |
|---|---|---|
| NIST AI RMF 1.0 | Risk management framework | AI system risk lifecycle |
| ISO/IEC 42001:2023 | Management system standard | Organizational AI governance |
| EU AI Act | Regulation | Legal compliance for AI systems in the EU |
| NIST SP 800-161r1 | Supply chain risk management | Vendor/supplier risk |
| NIST SP 1326 | Due diligence guide | Supplier assessment |
| ISO/IEC 27001 | Information security | Security controls |
| CSA Framework | Cloud security | Cloud-specific controls |

## Related Repositories

- [AI Vendor Due Diligence Template](https://github.com/rcwah2/ai-vendor-due-diligence-template) — Three-part vendor governance pack
- [AI System Inventory Template](https://github.com/rcwah2/ai-system-inventory-template) — Structured inventory schema
- [AI Governance Portfolio](https://github.com/rcwah2/ai-governance-portfolio) — Case studies and reasoning

## Author

**Raymond Wah** — Enterprise AI Governance & Implementation Program Leader

- LinkedIn: [linkedin.com/in/raymondwah](https://www.linkedin.com/in/raymondwah/)
- Substack: [rwahai.substack.com](https://rwahai.substack.com/)
- GitHub: [github.com/rcwah2](https://github.com/rcwah2)

## License

Copyright (c) 2026 Lissome Technology Consulting.

This work is licensed under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). You may share and adapt it, including for commercial purposes, provided you give appropriate credit to Lissome Technology Consulting, link to the license, and indicate if changes were made. See [LICENSE](LICENSE) for the full terms.

This guide is provided for educational and professional use. Adapt it to your organization's specific requirements and regulatory obligations.

## References

- [NIST AI RMF to ISO/IEC 42001 Official Crosswalk](https://airc.nist.gov/airmf-resources/crosswalks/)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [ISO/IEC 42001:2023](https://www.iso.org/standard/81230.html)
- [IA Governance: ISO 42001 vs NIST AI RMF](https://iagovernance.com/en/blog/iso-42001-vs-nist-ai-rmf/)
- [Modulos: ISO 42001 vs NIST AI RMF Documentation](https://docs.modulos.ai/frameworks/comparison/iso-42001-vs-nist-ai-rmf)
- [Shieldra: NIST AI RMF vs ISO 42001](https://www.shieldra.ai/compare/nist-ai-rmf-vs-iso-42001)
- [TCSA: ISO 42001 vs NIST AI RMF Crosswalk](https://www.tcsa.in/learn/iso-42001-vs-nist-ai-rmf)
- [Acer Innovation: NIST AI RMF x ISO/IEC 42001 Mapping](https://www.acerinnovation.com/nist-ai-rmf-iso-iec-42001-mapping)
