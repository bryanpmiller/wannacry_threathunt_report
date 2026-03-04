# Investigation Timeline

> This timeline is constructed from queries in `/kql_queries/` 

## How to generate the timeline

1. Find the earliest occurrence of `.want_to_cry` artifacts
2. Identify burst windows (rename/write spikes)
3. Correlate to process executions around the same time
4. Check registry changes (Defender exclusions/tampering)
5. Check network activity around impact window
6. Validate lateral movement (authentication plus remote execution indicators)

## Recommended timeline queries

- [Identify Encryption Start Time](../kql_queries/02_encryption_start_time.kql)
- [Correlate File Activity by Process](../kql_queries/03_file_activity_by_process.kql)
- [Review PowerShell Activity](../kql_queries/04_powershell_activity.kql)
- [Analyze Registry Modifications](../kql_queries/05_registry_modifications.kql)
- [Validate Network Connections](../kql_queries/07_network_connections.kql)
- [Check Lateral Movement](../kql_queries/08_lateral_movement_check.kql)

## Timeline

| Time (UTC)                         | Signal                                | Evidence                                                      | Notes                                                                                                                                                 |
| ---------------------------------- | ------------------------------------- | ------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **2026-03-02 08:48:10**            | First `.want_to_cry` file observed    | `DeviceFileEvents`                                            | Earliest evidence of ransomware-like activity detected on `vm-final-lab-wo`. Establishes investigation start time.                                    |
| **2026-03-02 08:48:10 – 08:49:00** | Burst of file rename/write activity   | `DeviceFileEvents summarize`                                  | Multiple files renamed with `.want_to_cry`. This period represents the **impact window** where simulated encryption occurred.                         |
| **2026-03-02 08:48:xx**            | PowerShell execution detected         | `DeviceProcessEvents`                                         | `powershell.exe -NoProfile -ExecutionPolicy RemoteSigned` observed. Process analysis performed to determine parent/child relationship and legitimacy. |
| **2026-03-02 08:49:xx**            | Windows Defender configuration review | `DeviceRegistryEvents`                                        | Registry inspection performed to detect potential Defender exclusion modifications (defense evasion). No confirmed malicious exclusions identified.   |
| **2026-03-02 08:49 – 08:50**       | Network activity validation           | `DeviceNetworkEvents`                                         | Outbound connections analyzed to detect potential command-and-control communication. No suspicious connections observed.                              |
| **Post-activity analysis**         | Lateral movement investigation        | `SecurityEvent`, `DeviceNetworkEvents`, `DeviceProcessEvents` | No authentication anomalies or additional hosts with `.want_to_cry` artifacts identified. Activity confirmed **isolated to a single host**.           |
