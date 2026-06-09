# IsPasswordOrComplexityEnabled(void *)

- ea: `0x18000f830`
- end: `0x18000fa6c`
- name: `?IsPasswordOrComplexityEnabled@@YAHPEAX@Z`
- size: `572`
- prototype: `__int64 __fastcall(CEasPolicySettings *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ed50`
- `0x180028370`
- `0x18005e5c0`

## callees

- `0x18000f830`
- `0x180010120`
- `0x180010230`
- `0x1800207a0`
- `0x1800372ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f9ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f9ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fa32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fa32`
- `ntdll!RtlInitializeResource` at `0x18000f9ec`
- `ntdll!RtlInitializeResource` at `0x18000f9ec`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000f9ca`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000f9ca`
- `ntdll!RtlReleaseResource` at `0x18000fa1b`
- `ntdll!RtlReleaseResource` at `0x18000fa1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f897`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f961`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f897`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f961`

## pseudocode

```c

```
