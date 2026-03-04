# Mitigation Recommendations

Even for simulations, treat findings as an opportunity to harden detections and response muscle memory.

## Detection engineering
- Create alerts for burst file renames to a novel extension (e.g., `.want_to_cry`)
- Alert on PowerShell running scripts from unusual directories or with suspicious command lines
- Alert on changes to Defender Exclusions (especially `Exclusions\Paths`)

## Response playbook
- Isolate host on first confirmed encryption/rename burst
- Acquire process tree and file-change evidence
- Validate backup/shadow copy tampering (if logs available)
- Hunt for lateral movement (authentication anomalies + remote process execution)

## Hardening
- Restrict PowerShell (Constrained Language Mode where appropriate)
- Enable tamper protection / auditing for Defender changes
- Least privilege for admin accounts, remove standing local admin where possible
