# GetKeyRefreshInfo(HKEY__ *,KeyRefreshInfo *)

- ea: `0x180027a0c`
- end: `0x180027b77`
- name: `?GetKeyRefreshInfo@@YAJPEAUHKEY__@@PEAUKeyRefreshInfo@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(HKEY KeyHandle, struct KeyRefreshInfo *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180026cec`
- `0x180040264`
- `0x1800782dc`

## callees

- `0x180024ff4`
- `0x180027a0c`

## import_xrefs

- `ntdll!NtQueryKey` at `0x180027a47`
- `ntdll!NtQueryKey` at `0x180027a96`
- `ntdll!NtQueryKey` at `0x180027ae8`
- `ntdll!NtQueryKey` at `0x180027b2e`
- `ntdll!NtQueryKey` at `0x180027a47`
- `ntdll!NtQueryKey` at `0x180027a96`
- `ntdll!NtQueryKey` at `0x180027ae8`
- `ntdll!NtQueryKey` at `0x180027b2e`
- `ntdll!RtlNtStatusToDosError` at `0x180027aa8`
- `ntdll!RtlNtStatusToDosError` at `0x180027b40`
- `ntdll!RtlNtStatusToDosError` at `0x180027aa8`
- `ntdll!RtlNtStatusToDosError` at `0x180027b40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027a64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027aff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027a64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027aff`

## pseudocode

```c

```
