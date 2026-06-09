# CServiceRecord::GetMitigationFlags(void)

- ea: `0x140025ac4`
- end: `0x140025d02`
- name: `?GetMitigationFlags@CServiceRecord@@QEAAKXZ`
- size: `574`
- prototype: `__int64 __fastcall(CServiceRecord *this, __int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14003c510`
- `0x140082dd0`

## callees

- `0x140003e54`
- `0x14000bebc`
- `0x140019014`
- `0x14001f99c`
- `0x140025ac4`
- `0x14004317c`
- `0x14007de34`
- `0x140092420`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140025c31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140025c31`
- `ntdll!RtlNtStatusToDosError` at `0x140025bbb`
- `ntdll!RtlNtStatusToDosError` at `0x140025bbb`
- `ntdll!RtlInitUnicodeString` at `0x140025b1a`
- `ntdll!RtlInitUnicodeString` at `0x140025b1a`
- `ntdll!RtlFreeHeap` at `0x140025bb2`
- `ntdll!RtlFreeHeap` at `0x140025bb2`
- `ntdll!NtQueryValueKey` at `0x140025b74`
- `ntdll!NtQueryValueKey` at `0x140025b74`
- `ntdll!RtlAllocateHeap` at `0x140025b3d`
- `ntdll!RtlAllocateHeap` at `0x140025b3d`

## pseudocode

```c

```
