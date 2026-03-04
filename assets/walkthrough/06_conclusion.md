# 06 — Conclusion and Confidence

## Conclusion
This investigation supports **simulated ransomware-like activity**.

## Confidence rubric
- **High confidence simulation** if:
  - artifacts are explicitly scenario-labeled (`want_to_cry`)
  - impact activity is bounded to a host/time window
  - no lateral movement
  - no clear destructive actions beyond rename/write patterns

- **High confidence real compromise** if:
  - widespread, uncontrolled file write/rename patterns across many directories
  - clear defense evasion + persistence + suspicious network comms
  - evidence of credential misuse/lateral movement

## Next steps
- Turn key queries into analytics rules
- Add enrichment (known-good processes, baseline remote IPs)
- Document containment actions and recovery steps
