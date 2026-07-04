# BOD 26-04 Remediation Clock

A single-file HTML/JS tool that tiers vulnerabilities per CISA's [BOD 26-04](https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-risk)
("Prioritizing Security Updates Based on Risk") and tells you how many days you have to patch.

## What it does
- Scores a CVE against the four BOD 26-04 risk variables: public exposure, KEV status,
  exploit automatability, and technical impact
- Computes the remediation deadline and flags whether forensic triage is mandatory
- Tracks multiple vulnerabilities in a live-countdown queue (persisted locally)
- **Live lookups** against two CISA-maintained sources:
  - [`cisagov/kev-data`](https://github.com/cisagov/kev-data) — confirms KEV status by CVE ID
  - [`cisagov/vulnrichment`](https://github.com/cisagov/vulnrichment) — pulls CISA's own
    SSVC scoring (Automatable, Technical Impact, Exploitation) where available

## Usage
Open `bod-26-04-calculator.html` in any browser. No build step, no server, no dependencies.

## ⚠️ Disclaimer
The 16-row decision matrix is reconstructed from CISA's published criteria and
secondary analysis of the directive, not copied verbatim from Appendix A (CISA's site
blocks automated retrieval). Validate against the official directive before using this
for compliance reporting. See the in-app banner for details, and edit the `MATRIX`
object in the source if any row differs from the authoritative table.

## License
MIT
