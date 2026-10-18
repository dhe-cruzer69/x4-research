# x4-research

**Evidence-first research agent**

Claim graphs • Source ranking • Contradiction detection • Citation validation

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-v0.1-orange)](CHANGELOG.md)

Part of **[ARIEX4Ops / X4](https://github.com/dhe-cruzer69)**.

---

## Principle

Every important claim must carry source, evidence, confidence, and contradiction checks.

```
QUESTION
  ↓
PLANNER → SEARCH → SOURCE RANKING
  ↓
EVIDENCE EXTRACTION → CLAIM GRAPH
  ↓
CONTRADICTION DETECTION → CITATION VALIDATION
  ↓
SYNTHESIS → REPORT
```

## Related

- [x4-agents](https://github.com/dhe-cruzer69/x4-agents)
- [x4-ai](https://github.com/dhe-cruzer69/x4-ai)

## License

Apache-2.0

## Support

**[GitHub Sponsors](https://github.com/sponsors/dhe-cruzer69)**

## APEX Architecture Map

> Status: architecture documentation; implementation and deployment claims require independent verification.

```mermaid
flowchart LR
  Query[Research question] --> Plan[Create bounded search plan]
  Plan --> Sources[Collect candidate sources]
  Sources --> Trust[Assess source authority and freshness]
  Trust --> Select[Select evidence set]
  Select --> Fetch[Fetch permitted content]
  Fetch --> Parse[Extract claims and citations]
  Parse --> Synthesis[Draft answer from evidence]
  Synthesis --> Verify{Every factual claim traceable?}
  Verify -->|no| Gap[Flag unsupported claims]
  Gap --> Refine[Search more or narrow answer]
  Refine --> Fetch
  Verify -->|yes| Output[Answer + citations + limitations]
  Sources --> Provenance[Record source metadata]
  Provenance --> Output
```
**Evidence note:** Source ranking and citation validation are intended gates. Confirm they are enforced by code rather than only described in documentation.

