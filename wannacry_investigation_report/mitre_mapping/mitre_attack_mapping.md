# MITRE ATT&CK Mapping (Educational)

> This is a learning-oriented mapping of observed investigation themes.  
> Confirm techniques based on actual evidence in your environment.

| Tactic | Technique | Why it may apply | Evidence to cite |
|---|---|---|---|
| Impact | T1486 Data Encrypted for Impact | File rename/encryption-like activity | DeviceFileEvents rename/write bursts |
| Execution | T1059.001 PowerShell | PowerShell-based activity | DeviceProcessEvents (powershell.exe) |
| Defense Evasion | T1562.001 Impair Defenses | Defender exclusions/tampering | DeviceRegistryEvents under Defender keys |
| Discovery | T1083 File and Directory Discovery | Scripts enumerating files before rename | Process command line / script content |
| Lateral Movement | (various) | Checked and not proven | SecurityEvent + process/network pivots |
