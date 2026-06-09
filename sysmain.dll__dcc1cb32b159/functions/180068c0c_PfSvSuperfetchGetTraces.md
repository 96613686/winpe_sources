# PfSvSuperfetchGetTraces

- ea: `0x180068c0c`
- end: `0x180068ef9`
- name: `PfSvSuperfetchGetTraces`
- size: `749`
- prototype: `DWORD __fastcall(__int64, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18006a020`

## callees

- `0x180023244`
- `0x180024b10`
- `0x180036818`
- `0x180039f94`
- `0x18004ceb8`
- `0x180050628`
- `0x180068c0c`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180068cec`
- `ntdll!NtQuerySystemInformation` at `0x180068cec`
- `ntdll!RtlNtStatusToDosError` at `0x180068eb3`
- `ntdll!RtlNtStatusToDosError` at `0x180068eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068e9e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180068d11`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180068d11`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180068d37`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180068d37`

## string_xrefs

- `0x180068dc4`: `PageAccess`

## pseudocode

```c

```
