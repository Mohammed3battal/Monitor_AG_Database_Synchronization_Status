## Script: Monitor Availability Group Database Synchronization State

**Description**:
Returns synchronization status for all databases in Availability Groups. You can optionally filter to show only databases in a "NOT SYNCHRONIZING" state.

**Usage**:
- Use as-is to show sync state of all AG databases
- Uncomment the last line to isolate problematic databases only

**Columns**:
- AGName
- ReplicaServerName
- DatabaseName
- SyncState (`SYNCHRONIZED`, `SYNCHRONIZING`, `NOT SYNCHRONIZING`, etc.)

**Requirements**:
- SQL Server 2012+
- VIEW SERVER STATE permission
