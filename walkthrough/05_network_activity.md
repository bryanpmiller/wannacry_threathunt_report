# 05 - Network Activity

Goal: determine whether the host made suspicious outbound connections during the impact window.

## What to look for
- Remote IPs not seen historically
- Connections to uncommon ports
- DNS lookups that correlate to suspicious IPs (if logs available)

## Queries
- [7 Validate Network Connections](../kql_queries/07_network_connections.kql)


