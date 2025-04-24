## Script: Monitor Availability Group Database Synchronization State

**Description**:
This script monitors the synchronization status of databases within Always On Availability Groups. It shows which databases are part of which AG and replica, and their current synchronization state.

**Query 1**: Lists **all databases** in AGs (excluding system AGs named 'AlwaysOn%') and their sync state.

**Query 2**: Filters only the databases that are currently **NOT SYNCHRONIZING**, which could indicate:
- A disconnected replica
- A suspended database
- A seeding failure

**Columns**:
- `AGName`: The name of the Availability Group
- `ReplicaServerName`: The name of the server hosting the replica
- `DatabaseName`: The name of the database in the AG
- `SyncState`: Sync status (`SYNCHRONIZED`, `SYNCHRONIZING`, or `NOT SYNCHRONIZING`)

**Use Case**:
- Daily Always On AG health check
- Automated alert/report script for monitoring dashboard
- Pre-failover validation

**Requirements**:
- SQL Server 2012 or later
- Always On feature must be enabled
- `VIEW SERVER STATE` permission

**Tip**:
To automatically monitor AG sync issues, schedule the second query via SQL Agent or alerting tool like PowerShell, SCOM, or SolarWinds.
