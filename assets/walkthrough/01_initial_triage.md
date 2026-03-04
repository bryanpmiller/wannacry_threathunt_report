# 01 - Initial Triage

Goal: confirm scope and determine whether this is likely impact activity.

## Steps
1. Confirm host: `vm-final-lab-wo`
2. Search for any artifacts containing `want_to_cry`
3. Identify earliest time observed (start of suspected impact)
4. Identify directories impacted

## Queries
- [1 Find Wannacry Files](../kql_queries/01_find_want_to_cry_files.kql)
- [2 Identify Encryption Start Time](../kql_queries/02_encryption_start_time.kql)

## Common pitfalls
- Using `Timestamp` in an Azure Log Analytics context when the table uses `TimeGenerated`


