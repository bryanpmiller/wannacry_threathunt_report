# 04 - Registry Analysis (Defender / Tampering)

Goal: detect defense evasion patterns (especially Windows Defender exclusions).

## Focus areas
- `Exclusions\Paths` modifications
- New exclusions pointing to temp directories or user-writable paths
- Sudden broad exclusions (for example, entire drive roots)

## Queries
- `kql_queries/06_defender_exclusions_paths.kql`
- `kql_queries/05_registry_modifications.kql`

## Interpretation guidance
One-off changes might be IT activity; correlate to time window plus process/user context.
