# Evidence Screenshot Capture Guide

This folder tracks query output screenshots referenced by the root README.

## Required Files

1. `kql_query_results_1_find_want_to_cry.png`
2. `kql_query_results_2_process_investigation.png`
3. `kql_query_results_3_registry_exclusions.png`
4. `kql_query_results_4_network_validation.png`

## Capture Checklist

### 1) `kql_query_results_1_find_want_to_cry.png`
- Source query: `kql_queries/01_find_want_to_cry_files.kql`
- Recommended filter: host `vm-final-lab-wo`, incident investigation window
- Expected columns: `TimeGenerated`, `DeviceName`, file path and name fields, action type
- Redaction guidance: mask usernames, full internal paths, tenant IDs, and workspace identifiers

### 2) `kql_query_results_2_process_investigation.png`
- Source query: `kql_queries/03_file_activity_by_process.kql`
- Recommended filter: same impact window identified in query 2
- Expected columns: `TimeGenerated`, `DeviceName`, `InitiatingProcessFileName`, process command-line context, file action
- Redaction guidance: redact account names and command-line secrets or tokens

### 3) `kql_query_results_3_registry_exclusions.png`
- Source query: `kql_queries/06_defender_exclusions_paths.kql`
- Recommended filter: +/-30 minutes around observed impact window
- Expected columns: `TimeGenerated`, `DeviceName`, registry key/value path, modification details
- Redaction guidance: mask sensitive directory names and environment-specific paths

### 4) `kql_query_results_4_network_validation.png`
- Source query: `kql_queries/07_network_connections.kql`
- Recommended filter: incident window plus short pre/post buffer
- Expected columns: `TimeGenerated`, `DeviceName`, remote IP/domain, remote port, initiating process
- Redaction guidance: redact public IPs or domains if environment policy requires

## Formatting Notes

- Prefer full-screen query and results grid in each screenshot.
- Include the time filter and query name in view when possible.
- Keep one screenshot per query for consistency.
