# Investigation Timeline

> This timeline is constructed from queries in `/kql_queries/` using **TimeGenerated**.

## How to generate the timeline
1. Find the earliest occurrence of `.want_to_cry` artifacts
2. Identify burst windows (rename/write spikes)
3. Correlate to process executions around the same time
4. Check registry changes (Defender exclusions/tampering)
5. Check network activity around impact window
6. Validate lateral movement (authentication + remote execution indicators)

## Recommended timeline queries
- `02_encryption_start_time.kql`
- `03_file_activity_by_process.kql`
- `04_powershell_activity.kql`
- `05_registry_modifications.kql`
- `07_network_connections.kql`
- `08_lateral_movement_check.kql`

## Fill-in timeline template (example)
| Time (UTC) | Signal | Evidence | Notes |
|---|---|---|---|
| (t0) | First `.want_to_cry` seen | DeviceFileEvents | Establish start |
| (t1) | Peak rename/write window | DeviceFileEvents summarize | “Impact window” |
| (t2) | Suspect process executed | DeviceProcessEvents | Parent/child chain |
| (t3) | Defender exclusion change | DeviceRegistryEvents | Defense evasion |
| (t4) | Outbound network spike | DeviceNetworkEvents | C2 validation |
| (t5) | Lateral movement indicators | SecurityEvent/DeviceProcessEvents | Usually none in sim |
