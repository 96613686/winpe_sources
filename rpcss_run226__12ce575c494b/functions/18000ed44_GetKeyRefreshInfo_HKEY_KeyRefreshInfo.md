# GetKeyRefreshInfo(HKEY__ *,KeyRefreshInfo *)

- ea: `0x18000ed44`
- end: `0x18000ee77`
- name: `?GetKeyRefreshInfo@@YAJPEAUHKEY__@@PEAUKeyRefreshInfo@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(HKEY KeyHandle, struct KeyRefreshInfo *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000dcf0`
- `0x180038d84`
- `0x180073bd4`

## callees

- `0x18000eab0`
- `0x18000ed44`

## import_xrefs

- `ntdll!NtQueryKey` at `0x18000ed7f`
- `ntdll!NtQueryKey` at `0x18000edc2`
- `ntdll!NtQueryKey` at `0x18000ee05`
- `ntdll!NtQueryKey` at `0x18000ee3f`
- `ntdll!NtQueryKey` at `0x18000ed7f`
- `ntdll!NtQueryKey` at `0x18000edc2`
- `ntdll!NtQueryKey` at `0x18000ee05`
- `ntdll!NtQueryKey` at `0x18000ee3f`
- `ntdll!RtlNtStatusToDosError` at `0x18000edce`
- `ntdll!RtlNtStatusToDosError` at `0x18000ee4b`
- `ntdll!RtlNtStatusToDosError` at `0x18000edce`
- `ntdll!RtlNtStatusToDosError` at `0x18000ee4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ed96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ee16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ed96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ee16`

## pseudocode

```c

```
