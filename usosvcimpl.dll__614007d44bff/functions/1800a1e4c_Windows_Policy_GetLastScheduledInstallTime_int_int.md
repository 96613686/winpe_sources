# Windows::Policy::GetLastScheduledInstallTime(int,int)

- ea: `0x1800a1e4c`
- end: `0x1800a1fde`
- name: `?GetLastScheduledInstallTime@Policy@Windows@@AEAA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@HH@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800a21e0`

## callees

- `0x180010890`
- `0x180068bc4`
- `0x1800a1e4c`
- `0x1800aada8`
- `0x1800dd67e`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800a1e8d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800a1e8d`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800a1ebc`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800a1ebc`

## pseudocode

```c

```
