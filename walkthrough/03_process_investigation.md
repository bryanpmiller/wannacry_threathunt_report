# 03 - Process Investigation

Goal: tie file activity to a process and parent process chain.

## Steps
1. Identify the process responsible for file changes (where available)
2. Pivot to process executions around the impact window
3. Validate parent/child lineage (who launched PowerShell?)

## Queries
- [3 Correlate File Activity by Process](../kql_queries/03_file_activity_by_process.kql)
- [4 Review PowerShell Activity](../kql_queries/04_powershell_activity.kql)
- [9 Process Tree Helpers](../kql_queries/09_process_tree_helpers.kql)


