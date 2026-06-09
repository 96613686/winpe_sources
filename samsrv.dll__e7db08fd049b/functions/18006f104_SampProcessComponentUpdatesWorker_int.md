# SampProcessComponentUpdatesWorker(int)

- ea: `0x18006f104`
- end: `0x18006f2ec`
- name: `?SampProcessComponentUpdatesWorker@@YAJH@Z`
- size: `488`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006d4f0`
- `0x18006d5c0`
- `0x1800730cc`

## callees

- `0x180027e24`
- `0x180037284`
- `0x1800372ac`
- `0x18006f104`
- `0x18006f42c`
- `0x1800b03d0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18006f285`
- `ntdll!RtlLeaveCriticalSection` at `0x18006f285`
- `ntdll!RtlEnterCriticalSection` at `0x18006f182`
- `ntdll!RtlEnterCriticalSection` at `0x18006f182`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18006f243`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18006f243`
- `LSASRV!LsaIRegisterNotification` at `0x18006f218`
- `LSASRV!LsaIRegisterNotification` at `0x18006f218`

## pseudocode

```c

```
