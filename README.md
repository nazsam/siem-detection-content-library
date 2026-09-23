# 📚 SIEM Detection Content Library

*By S. Naz · Cybersecurity, Cloud & AI Security Leader*

A vendor-agnostic library of detection content: authored once in Sigma, mapped to ATT&CK, and portable across SIEMs.

![Sigma Rules](https://img.shields.io/badge/Sigma_Rules-2B50E4?style=flat-square) ![MITRE ATT%26CK](https://img.shields.io/badge/MITRE_ATT%26CK-C00?style=flat-square) ![Sentinel](https://img.shields.io/badge/Sentinel-0078D4?logo=microsoft&logoColor=white?style=flat-square) ![Splunk](https://img.shields.io/badge/Splunk-000000?logo=splunk&logoColor=white?style=flat-square)

## What's Inside

- Sigma detection rules organized by **MITRE ATT&CK tactic and technique**
- Conversion notes for Sentinel KQL, Splunk SPL, and Elastic EQL backends
- A lightweight test-case format for validating each rule against known-good and known-bad log samples
- False-positive tuning log per rule, so tuning knowledge doesn't live only in someone's head

## Key Practices

- Every rule ships with **one line explaining the attacker behavior it catches**, not just the query. Detections should be understandable by the analyst triaging the alert at 2am
- Coverage is tracked against the ATT&CK matrix to make gaps visible, not just wins

## Status

- Actively growing. Current focus is expanding cloud identity and AiTM phishing coverage.

## ☁️ Microsoft Sentinel deployment path

1. Author the rule once in Sigma.
2. Convert to KQL with `sigma-cli` and the pySigma Kusto backend (Sentinel and Defender XDR pipelines).
3. Wrap the query as a Sentinel scheduled analytics rule and deploy it through the CI/CD pipeline in
   **[azure-secops-toolkit](https://github.com/nazsam/azure-secops-toolkit)**, which validates every query with Microsoft's Kusto parser, compiles the rules
   to ARM and deploys with GitHub Actions or Azure DevOps.
4. Track coverage in the toolkit's [ATT&CK coverage matrix](https://github.com/nazsam/azure-secops-toolkit/blob/main/docs/mitre-coverage.md).

---

*Maintained by **Sam Naz**, Cybersecurity and AI Architect · [LinkedIn](https://www.linkedin.com/in/samicybersecurity) · Azure implementation: [azure-secops-toolkit](https://github.com/nazsam/azure-secops-toolkit)*
