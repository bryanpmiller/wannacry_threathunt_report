# Findings

## 1) Impact Indicators (`want_to_cry`)
- Files containing `want_to_cry` were observed on `vm-final-lab-wo`.
- Primary goal: determine whether these represent real encryption or a simulation (rename-only).

**Evidence queries**
- `01_find_want_to_cry_files.kql`
- `02_encryption_start_time.kql`

## 2) Process Correlation
- Determine which process (and parent process) is responsible for creating/renaming impacted files.
- Pay attention to PowerShell usage and scripts (e.g., `Install.ps1.want_to_cry`).

**Evidence queries**
- `03_file_activity_by_process.kql`
- `04_powershell_activity.kql`
- `09_process_tree_helpers.kql`

## 3) Defense Evasion (Defender changes)
- Check for Windows Defender exclusion changes, particularly **Paths** exclusions.
- Any exclusions involving temp folders or suspicious directories should be treated as high risk.

**Evidence queries**
- `06_defender_exclusions_paths.kql`
- `05_registry_modifications.kql`

## 4) Network Validation
- Verify whether there are suspicious outbound connections during the impact window.
- Simulations often avoid real C2.

**Evidence queries**
- `07_network_connections.kql`

## 5) Lateral Movement
- Validate whether additional hosts show the same artifacts or whether authentication events indicate spread.
- Current investigation scope indicates **no lateral movement**.

**Evidence queries**
- `08_lateral_movement_check.kql`
