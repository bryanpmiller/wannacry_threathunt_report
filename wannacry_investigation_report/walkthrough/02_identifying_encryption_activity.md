# 02 — Identifying Encryption vs Simulation

Ransomware investigations often start with an “encryption signal.”  
But many labs simulate encryption by renaming files rather than actually encrypting.

## What to look for
- Burst of `FileRenamed` / write operations
- Many unique file paths in a narrow time window
- Correlation to a single responsible process tree

## Queries
- `kql_queries/02_encryption_start_time.kql`
- `kql_queries/03_file_activity_by_process.kql`
- `kql_queries/10_rename_burst_by_minute.kql`

## How to decide
If you see **many renames** but no other destructive behaviors (shadow copies, backups, persistence, external comms), it may indicate a **simulation**.
