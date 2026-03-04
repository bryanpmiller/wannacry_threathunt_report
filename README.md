# wannacry_investigation_report

Investigating **simulated ransomware-like activity** using **KQL** in an **Azure Log Analytics Workspace**.

This repository blends a **SOC-style incident report** with a **step-by-step threat hunting tutorial**. The scenario includes artifacts containing the string **`want_to_cry`** (e.g., file names ending with `.want_to_cry`). The goal is to teach how to validate impact signals, build a timeline, and assess lateral movement (or the lack of it).

> **Scope:** Single host `vm-final-lab-wo`.  
> **Conclusion:** Ransomware-like **simulation** (controlled artifacts + no proven lateral movement), based on the investigation workflow documented here.

## Repository Map

- **/report/** — incident-style writeup (summary, timeline, findings, recommendations)
- **/walkthrough/** — learning guide (triage → timeline → process → registry → network → conclusion)
- **/kql_queries/** — ready-to-run KQL hunting/playbook queries
- **/mitre_mapping/** — MITRE ATT&CK mapping for observed behaviors
- **/artifacts/** — artifact list focusing on `want_to_cry` strings

## Quick Start (Run These First)

1. `kql_queries/01_find_want_to_cry_files.kql`
2. `kql_queries/02_encryption_start_time.kql`
3. `kql_queries/03_file_activity_by_process.kql`
4. `kql_queries/06_defender_exclusions_paths.kql`
5. `kql_queries/08_lateral_movement_check.kql`

## How to Use

1. Open **Azure Log Analytics Workspace** → **Logs**
2. Paste a query from `/kql_queries/`
3. Adjust the time range (e.g., “Last 7 days”) and the device name if needed
4. Follow the `/walkthrough/` chapters to pivot correctly and avoid common mistakes

## Notes on Fields (Important)

In this investigation we standardize on **`TimeGenerated`** in Azure Log Analytics.

---

## License

MIT (see `LICENSE`)
