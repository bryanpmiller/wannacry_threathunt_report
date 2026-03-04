# Incident Summary

## Overview

This investigation documents ransomware-like activity observed on a single Windows host (`vm-final-lab-wo`) in an Azure Log Analytics Workspace. The activity included file artifacts containing **`want_to_cry`** (for example, file names ending with `.want_to_cry`).

## Scope

- **Environment:** Azure Log Analytics Workspace (KQL)
- **Host:** `vm-final-lab-wo`
- **Data sources:** `DeviceFileEvents`, `DeviceProcessEvents`, `DeviceRegistryEvents`, `DeviceNetworkEvents`, `SecurityEvent` (as available)

## High-level Assessment

Evidence supports a **controlled simulation** rather than an uncontrolled ransomware outbreak:

- Artifacts are explicitly labeled with `want_to_cry`
- Activity appears bounded to a single host
- No validated lateral movement

## What this repo teaches


- How to correlate file activity to process lineage
- How to look for Defender tampering/exclusions
- How to validate (or disprove) lateral movement using log pivots
